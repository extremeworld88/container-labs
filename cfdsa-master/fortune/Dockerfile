FROM node:latest

# Docker build portion
# define environment variables
ENV APP_PORT=5000 APP_DIR=/fortune

# create APP_DIR, and cd inside
WORKDIR ${APP_DIR}

# copy file to APP_DIR
ADD main.js .
ADD package.json .
# directories must have a target name
ADD public public
ADD views views

# install libraries from package.json
RUN npm install

## docker run portion
EXPOSE ${APP_PORT}

HEALTHCHECK --interval=60s --timeout=5s --retries=1 \
 CMD curl -f -s http://localhost:${APP_PORT}/health || exit 1

# execute the image
ENTRYPOINT [ "node", "main.js" ]

# if you want to pass in parameters
 CMD [""]  


