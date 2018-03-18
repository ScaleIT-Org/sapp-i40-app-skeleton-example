# ScaleIT App Meta Skeleton Example

Technology Stack Agnostic Industry 4.0 Ready App Skeleton.

Apps that follow this template are considered "Industrie 4.0 Ready" and can be successfully installed and run on any instance of the ScaleIT Platform.

More information on app readiness can be found here:
http://scaleit-platform-documentation.readthedocs.io/en/latest/app_readiness.html


This is an example repo on how to use the ScaleIT App Meta Skeleton with ionic-frontend and app-registration-sidecar.

## HowTo:

#### 1) Clone Main App Skeleton

- Clone the main ScaleIT App Meta skeleton

      git clone https://github.com/ScaleIT-Org/sapp-i40-app-skeleton.git My_New_ScaleiT_App

#### 2) Add your domain software

- Use git submodules to add a domain software (ionic frontend)

      cd sapp-i40-app-skeleton
      git submodule add https://github.com/ScaleIT-Org/ionic-app-skeleton.git "Domain Software/IonicFrontend"

- Add service to docker-compose.yml.
  Your docker-compose.yml should now look like this:

      version: '2'
      services:
        ionicfrontend:
        build: ./Domain Software/IonicFrontend
        ports:
        - "8100:80"    

#### 3) Add Platform Sidecar

- Add a platform sidecar (app-registration-sidecar):
    hint: to use the app-registration-sidecar you need a running etcd-store.
    Refer to this repo: https://github.com/ScaleIT-Org/spe-app-registry-etcd

      git submodule add https://github.com/ScaleIT-Org/spsc-app-registration.git "Platform Sidecars/sidecar-registration"  

- Add service to main docker-compose.yml.

      sidecarregistration:
        build: ./Platform Sidecars/sidecar-registration/
        env_file:
          - ./Platform Sidecars/sidecar-registration/config.env

- Configure environment variables to specify app details for the registration-service

      Modify the file config.env in ./Platform Sidecars/sidecar-registration/

#### 4) Build and Run

        docker-compose build
        docker-compose up

#### 5) Results

You should now have a running application with ionic frontend on localhost:8100 which is registrated on the specified etcd-store. 
