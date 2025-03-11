
FROM node:18 AS builder

WORKDIR /app

COPY reactApp /app

RUN npm install && npm run build

FROM nginx:1.25

COPY default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]




# FROM nginx:1.25

# COPY default.conf /etc/nginx/conf.d/default.conf

# COPY /reactApp /usr/share/nginx/reactApp

# EXPOSE 80