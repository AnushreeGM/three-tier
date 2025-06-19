FROM public.ecr.aws/docker/library/node:18-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm config set registry https://registry.npmjs.org/ && npm install
COPY . .
RUN npm run build

FROM public.ecr.aws/nginx/nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
