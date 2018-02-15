# ScaleIT App Meta Skeleton 

Technology Stack Agnostic Industry 4.0 Ready App Skeleton.

Apps that follow this template are considered "Industrie 4.0 Ready" and can be successfully installed and run on any instance of the ScaleIT Platform.

More information on app readiness can be found here:
http://scaleit-platform-documentation.readthedocs.io/en/latest/app_readiness.html

## Usage

    git clone https://github.com/ScaleIT-Org/sapp-i40-app-skeleton.git My_New_ScaleiT_App
    
### With Git Submodule Composition

Add Node.js Domain Software:
    
    cd My_New_ScaleiT_App
    git submodule add https://github.com/ScaleIT-Org/nodejs-app-skeleton.git "Domain Software/MyNodejsApp"

Add a platform sidecar:

### File Based Composition/Copying

    mkdir MyNodejsApp
    git clone https://github.com/ScaleIT-Org/nodejs-app-skeleton.git MyNodejsApp
    
    # move or copy the Node.js skeleton to the Industry 4.0 Ready App Skeleton
    mv MyNodejsApp "My_New_ScaleiT_App/Domain Software"

    # optionally but recommended, remove the git version control from the Node.js skeleton
    cd "My_New_ScaleiT_App/Domain Software/MyNodejsApp"
    rm -rf .git

## Additional Information 

The `.gitkeep` files are just placeholders and can be deleted. This is due to the fact that git only checks in folders with files inside them.