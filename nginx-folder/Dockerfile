FROM nginx:latest

WORKDIR /usr/local/appian

ENV APPIAN_HOME /usr/local/appian/ae
ENV APPIAN_INSTALLER_LINUX setupLinux64_appian-*.bin
ENV HOTFIX_PACKAGE *_Hotfix_Package_*.zip

RUN apt-get update \
  && apt-get install -y vim \
  && apt-get install -y nano

COPY index.html /usr/share/nginx/html/index.html
COPY background.png /usr/share/nginx/html/background.png

USER appian

HEALTHCHECK --interval=3s --timeout=2s --retries=300 \
  CMD ncat --recv-only localhost $READY_PORT | grep -q $READY_TEXT || exit 1

ENTRYPOINT [ "/usr/local/appian/ae/dockerize.sh" ]
