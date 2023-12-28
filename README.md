# Hugo + AWS Amplify Example
This repository contains everything that one (should) need to deploy a static hugo website to AWS amplify.

## Pulling in new themes
The theme is currently pulled in by a git submodule. To switch themes, add the theme as a git submodule, delete the old theme (if desired), and update theme attribute in the hugo.yaml file.

Alternatively, you can do one of the following:
  * Use hugo mods
  * Clone the theme into the themes folder