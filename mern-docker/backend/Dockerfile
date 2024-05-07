# set the base image to create the image for react app (just a version of node)
FROM node:20-alpine

# create a user with permissions to run the app
# -S -> create a system user
# -G -> add the user to a group
# This is done to avoid running the app as root
# If the app is run as root, any vulnerability in the app can be exploited to gain access to the host system
# It's a good practice to run the app as a non-root user
RUN addgroup app && adduser -S -G app app

# USER app
WORKDIR /app
COPY package*.json ./
# USER root
# RUN chown -R app:app .
# # change the user back to the app user
# USER app

RUN npm install
COPY . .
EXPOSE 8000
# command to run the app
CMD npm start