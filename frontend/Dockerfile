FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Build Iles site
RUN npm run build

# Expose the port your preview server uses
EXPOSE 3000

# Start the production preview server
CMD ["npm", "run", "preview"]
