FROM node:14-alpine as builder
COPY . .
WORKDIR /app
RUN npm install
RUN npm run-script build

FROM nginx:stable-alpine3.17-slim
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]