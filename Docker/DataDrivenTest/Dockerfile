# Use the official Node.js 20 image as the base image
FROM node:20

# Set the working directory in the container
WORKDIR /app

# Install Newman and required reporters
RUN npm install -g newman newman-reporter-html newman-reporter-htmlextra


# Copy your Postman collection, environment, and data files
COPY DataDrivenAPIsCollection.json .
COPY GoRestEnv.json .
COPY myuser.csv .

# Set the command to run Newman with data-driven testing
CMD ["newman", "run", "/app/DataDrivenAPIsCollection.json", "-e", "/app/GoRestEnv.json", "-d", "/app/myuser.csv", "-r", "cli,json,html,htmlextra", "--reporter-htmlextra-export", "/app/results/gorest.html"]
