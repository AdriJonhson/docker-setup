FROM nginx:alpine

RUN apk add --no-cache openssl

RUN mkdir /etc/nginx/ssl 2> /dev/null

RUN openssl genrsa -out "/etc/nginx/ssl/elo-leads.test.key" 2048 \
    && openssl req -new -key "/etc/nginx/ssl/elo-leads.test.key" -out "/etc/nginx/ssl/elo-leads.test.csr" -subj "/CN=elo-leads.test/O=elo-leads.test/C=UK" \
    && openssl x509 -req -days 365 -in "/etc/nginx/ssl/elo-leads.test.csr" -signkey "/etc/nginx/ssl/elo-leads.test.key" -out "/etc/nginx/ssl/elo-leads.test.crt"

EXPOSE 80 443