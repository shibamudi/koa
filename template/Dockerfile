FROM node:7.10-alpine
ENV NODE_ENR=production HOST="0.0.0.0" PROT=3000 PROJECT_DIR=/app
WORKDIR $PROJECT_DIR
COPY package.json yarn.lock $PROJECT_DIR/
RUN yarn install && yarn cache clean
COPY . $PROJECT_DIR
EXPOSE $PROT
HEALTHCHECK CMD curl -f http://0.0.0.0:3000 || exit 1
ENTRYPOINT ["yarn", "run", "build", "&&", "yarn", "run", "start"]
