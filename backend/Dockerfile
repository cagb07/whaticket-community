FROM node:16

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

# Diagnóstico
RUN node --version
RUN npm --version
RUN npx tsc --version
RUN ls -la
RUN cat package.json
RUN cat tsconfig.json
RUN npm run build || (echo "Build failed" && npm run build --verbose && npx tsc --listFiles && exit 1)

ENV NODE_ENV=production

EXPOSE 8080

CMD ["npm", "start"]