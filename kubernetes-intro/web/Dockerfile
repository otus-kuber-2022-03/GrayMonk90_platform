FROM nginx:1.21.6-alpine

WORKDIR /app

RUN addgroup -g 1001 -S app_user && \
    adduser -u 1001 -S app_user -G app_user && \
    touch /var/run/nginx.pid && \
    chown -R app_user: /var/cache/nginx /var/log/nginx /var/run/nginx.pid /app

RUN sed -i 's/user  nginx/user app_user/' /etc/nginx/nginx.conf

COPY default.conf /etc/nginx/conf.d/default.conf

USER app_user

EXPOSE 8000
CMD ["nginx", "-g", "daemon off;"]
