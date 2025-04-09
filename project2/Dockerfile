# use an offical node.js runtime as a parent image


FROM node:22-alpine

#ste thr working directory in the container
WORKDIR /app

# copy the package.json and package-lock.json files in the container 

COPY package*.json .

# Install the dependencies

RUN npm install


# Copy the rest of the application

COPY . .

# Expose the port that the app runs on
EXPOSE 5000


#Define your command to run the application
CMD ["node", "./src/server.js"]