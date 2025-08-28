# Use Node as base image
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy only package files first
COPY package.json yarn.lock* ./

# Install dependencies with extra timeout
RUN yarn install --frozen-lockfile --production=false



# Copy rest of the app
COPY . .

# Expose port
EXPOSE 3000

# Start dev server
CMD ["yarn", "dev", "--host", "0.0.0.0"]

