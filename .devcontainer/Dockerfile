#update the required node version in the below line
FROM node:18.19.0

EXPOSE 4321 35729 5432

ENV NPM_CONFIG_PREFIX=/usr/app/.npm-global \
  PATH=$PATH:/usr/app/.npm-global/bin

VOLUME /usr/app/spfx
WORKDIR /usr/app/spfx
RUN useradd --create-home --shell /bin/bash spfx && \
    usermod -aG sudo spfx && \
    chown -R spfx:spfx /usr/app

USER spfx

#update the required gulp yo and spfx generator version in the below line
RUN npm i --location=global gulp-cli@2 yo @microsoft/generator-sharepoint@1.19.0-beta.0

CMD /bin/bash
