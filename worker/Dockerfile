FROM node:16-alpine as builder
# need to modify directories for use in wsl2
WORKDIR '/home/node/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx
# for EBS may need EXPOSE: 80
COPY --from=builder /home/node/app/build /usr/share/nginx/html

