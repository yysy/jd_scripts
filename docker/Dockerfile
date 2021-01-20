FROM alpine
LABEL AUTHOR="none" \
        VERSION=0.1.3

ENV DEFAULT_LIST_FILE=crontab_list.sh \
        CUSTOM_LIST_MERGE_TYPE=append \
        REPO_URL=https://gitee.com/lxk0301/jd_scripts.git

RUN set -ex \
        && apk update && apk upgrade\
        && apk add --no-cache tzdata  git  nodejs  moreutils  npm curl jq \
        && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
        && echo "Asia/Shanghai" > /etc/timezone

<<<<<<< Updated upstream
<<<<<<< HEAD
RUN git clone https://gitee.com/lxk0301/jd_scripts.git /scripts \
=======
RUN git clone ${REPO_URL} /scripts \
>>>>>>> 2ac25fae16812dbebface05f026723652f88ec96
=======
RUN git clone ${REPO_URL} /scripts \
>>>>>>> Stashed changes
        && cd /scripts \
        && git checkout master \
        && mkdir logs \
        && npm install

RUN cp /scripts/docker/docker_entrypoint.sh /usr/local/bin \
        && chmod +x /usr/local/bin/docker_entrypoint.sh

WORKDIR /scripts

ENTRYPOINT ["docker_entrypoint.sh"]

CMD [ "crond" ]
