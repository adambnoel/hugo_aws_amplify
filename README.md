# Hugo + AWS Amplify Example
This repository contains everything that one (should) need to deploy a static hugo website to AWS amplify, although one will need to manually setup the AWS Amplify application in AWS.

To note, one **could** automate this process fully, but it didn't seem worth going through the hassle of having to manual setup GitHub access tokens (effectively moving the manual effort into two places, instead of one).

## Pulling in new themes
The theme is currently pulled in by a git submodule. To switch themes, add the theme as a git submodule, delete the old theme (if desired), and update theme attribute in the hugo.yaml file.

Alternatively, you can do one of the following:
  * Use hugo mods
  * Clone the theme into the themes folder

## Setting up AWS Amplify
Once you have a hugo site ready to be deployed, go to the aws amplify console in AWS ([or click here](https://console.aws.amazon.com/amplify/home)). You should find yourself at the landing page for AWS amplify. If you haven't created an app before, it should look like this:

![Landing page](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/landing.png)

Click "Get Started" and you will be presented with two options, choose static hosting:
![Static hosting](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/static_hosting.png)

You will then be asked to select your code provider. AWS will handle the authentication/authorization workflow for you, click through and grant the level of permission you think appropriate.

![Connect](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/static_hosting.png)

If successful, you should see the following screen. Select the github repository you want to deploy and then select the branch you want deployed. Click next.

![Auth success](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/auth_successful.png)

On the next page, you will need to specify the build specification (note: the build specification is not set in the below image) and set the correct image.

![Build](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/build.png)

The build specification should be as follows:
```yaml
version: 1
frontend:
  phases:
    build:
      commands:
        - hugo
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
  cache:
    paths:[]
```

To use the latest hugo image (the default doesn't work), click advanced settings, click live package updates, and select hugo.

![Updates](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/updates.png)

Review the application and click "Save and Deploy". You will need to wait a bit for the application to save and deploy.

![Review](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/review.png)

Once deployed, you will be redirected to a status screen.

![Deploying](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/deploying.png)

After a few minutes, your application should be deployed. To see your newly deployed hugo app, click the link located below main.

![Complete](https://raw.githubusercontent.com/adambnoel/hugo_aws_amplify/main/content/tutorial/complete.png)

You should see your hugo site.