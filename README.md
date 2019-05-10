# ci-cd-gitlab
Gitlab CI/CD configuration with AWS Ec2 instance
## Preconditions for Gitlab

step : 1 (Generate public key for your ec2 instance to connect with gitlab

Check if you have a public key already that you could reuse:

```ls -a ~/.ssh```
If there is NO public key file id_rsa.pub then generate one:
```ssh-keygen```
Accept defaults. I don't enter password because I prefer to keep my hard drive encrypted whenever the repository contents are critical.

Copy your public key to clipboard:

```pbcopy < ~/.ssh/id_rsa.pub```
## Paste the Copied SSH file to Gitlab SSH Keys(which will be available under settings->SSH Keys).

Step 2: After coping your public key from you ec2 instance->paste it in ssh key section and assign a name for it.

## Copy the private key as well from the Step 1.

Step3: Now copy the private key from your ec2 instance which you have generated via ssh-keygen method and paste it in your personal project CI/CD settings.

1. Go to your project->make sure you are the admin for the project->setting->CI/CD->and save it as an variable.

https://snag.gy/5mlRNO.jpg

## now push some change pipeline will get triggered and file will be updated in your instance.

### PS: Make sure you have assigned Elastic IP to your instance,GIT installed
