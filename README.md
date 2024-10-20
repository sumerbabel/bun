# Crear el proyecto host
ng new host-app --create-application=false
cd host-app
ng generate application host --routing --style=scss
ng add @angular-architects/module-federation --project host --port 4200 --type host

# Crear el proyecto microfrontend
cd ..
ng new mfe-app --create-application=false
cd mfe-app
ng generate application mfe --routing --style=scss
ng add @angular-architects/module-federation --project mfe --port 4201 --type remote

# Crear el proyecto librería
cd ..
ng new shared-lib --create-application=false
cd shared-lib
ng generate library shared-lib
ng build shared-lib
