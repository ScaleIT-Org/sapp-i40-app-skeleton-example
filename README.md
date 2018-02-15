# ScaleIT App Meta Skeleton 

Technology Stack Agnostic Industry 4.0 Ready App Skeleton.

## Usage

    git clone https://github.com/ScaleIT-Org/sapp-i40-app-skeleton.git My_New_ScaleiT_App
    
### With Git Submodule Composition

Add Node.js Domain Software:
    
    cd My_New_ScaleiT_App
    git submodule add https://github.com/ScaleIT-Org/nodejs-app-skeleton.git "Domain Software/MyNodejsApp"

Add a platform sidecar:

## File Based Composition/Copying

    mkdir MyNodejsApp
    git clone https://github.com/ScaleIT-Org/nodejs-app-skeleton.git MyNodejsApp
    
    # move or copy the Node.js skeleton to the Industry 4.0 Ready App Skeleton
    mv MyNodejsApp "My_New_ScaleiT_App/Domain Software"

    # optionally but recommended, remove the git version control from the Node.js skeleton
    cd "My_New_ScaleiT_App/Domain Software/MyNodejsApp"
    rm -rf .git
