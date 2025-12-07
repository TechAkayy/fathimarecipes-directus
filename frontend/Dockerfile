FROM node:18-alpine AS build
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

FROM node:18-alpine AS runtime
WORKDIR /app

COPY --from=build /app /app

EXPOSE 3000

CMD ["npm", "run", "preview", "--", "--port", "3000", "--host", "0.0.0.0"]
