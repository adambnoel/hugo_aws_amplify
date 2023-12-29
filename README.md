# Hugo + AWS Amplify Example
This repository contains everything that one (should) need to deploy a static hugo website to AWS amplify, although one will need to manually setup the AWS Amplify application in AWS.

To note, one **could** automate this process fully, but it didn't seem worth going through the hassle of having to manual setup GitHub access tokens (effectively moving the manual effort into two places, instead of one).

## Pulling in new themes
The theme is currently pulled in by a git submodule. To switch themes, add the theme as a git submodule, delete the old theme (if desired), and update theme attribute in the hugo.yaml file.

Alternatively, you can do one of the following:
  * Use hugo mods
  * Clone the theme into the themes folder

## Setting up AWS Amplify
Once you have a hugo site ready to be deployed, go to the aws amplify console in AWS ([or click here](https://console.aws.amazon.com/amplify/home)). You should find yourself at the landing page for AWS amplify. If you haven't created an app before, it should look like this.

![Landing page](./content/tutoral/landing.png)
