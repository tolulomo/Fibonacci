FROM node:alpine as builder

WORKDIR "/app"

COPY ./package.json ./

RUN npm install

COPY ./ ./

RUN npm run build

FROM nginx
EXPOSE 3000
COPY --from=builder /app/build /usr/share/nginx/html

# Setting up this special rule to run a seperate nginx since react app will serve static file
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

# Line already added above. If it fails, comment above line
# and enable this line below
# COPY --from=builder /app/build /usr/share/nginx/html
