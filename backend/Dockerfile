# Stage 1
FROM node:21 AS backend-builder

# Setup working dir
WORKDIR /app

# Copy the code
COPY . .

# Install all the required dependencies
RUN npm i

# Stage 2
FROM node:21-slim 

# Setup the working dir
WORKDIR /app

# Copy the above stage as compressed
COPY --from=backend-builder /app .

COPY .env.sample .env

# Expose
EXPOSE 5000

# App
CMD ["npm", "start"]

