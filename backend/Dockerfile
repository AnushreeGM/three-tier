FROM public.ecr.aws/docker/library/node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm config set registry https://registry.npmjs.org/ && npm install
COPY . .
EXPOSE 5000
CMD ["node", "app.js"]
