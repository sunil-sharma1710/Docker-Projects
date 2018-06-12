# Angular6LatestExampleApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.0.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## Docker

You can build the image and run the container with Docker. The configuration is in the nginx folder if you want to change it.

`docker build -f Dockerfile -t angular-latest-example-app .`

`docker run -d -p 4200:80 angular-latest-example-app`

Once you done with our app then destroy the container and the image we have created.

## Docker-compose
You can build the image and run the container with Docker-compose as well.

`docker-compose build`

`docker-compose up -d`

Once you done with our app then destroy the container with the below command.

`docker-compose down`

Cheers!!


