#########################
### Build environment ###
#########################

# Base image
FROM node:8.11.2 as builder

# Set working directory
RUN mkdir /usr/src/app
WORKDIR /usr/src/app

# Add `/usr/src/app/node_modules/.bin` to $PATH
ENV PATH /usr/src/app/node_modules/.bin:$PATH

# Install and cache app dependencies
COPY package.json /usr/src/app/package.json
RUN npm install
RUN npm install -g @angular/cli@latest --unsafe

# Add app
COPY . /usr/src/app

# Generate build
RUN npm run build

##################
### Production ###
##################

# Base image
FROM nginx:1.13.9-alpine

## Copy our default nginx config
COPY nginx/default.conf /etc/nginx/conf.d/

## Remove default nginx website
RUN rm -rf /usr/share/nginx/html/*

# Copy artifact build from the 'build environment'.
# In angular 6 with cli 6.0.8, we need to use angular app name after dist.
# In later versions, remove angular app name.
COPY --from=builder /usr/src/app/dist/angular6-latest-example-app /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Run nginx
CMD ["nginx", "-g", "daemon off;"]
