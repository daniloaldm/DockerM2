FROM elasticsearch:6.8.11

ARG USER_NAME=elasticsearch
ARG USER_ID=1000
ARG GROUP_ID=1000
RUN userdel -f ${USER_NAME} && \
    if getent group ${GROUP_ID} ; then groupdel ${GROUP_ID}; fi && \
    groupadd -g ${GROUP_ID} ${USER_NAME}  && \
    useradd -l -u ${USER_ID} -g ${USER_NAME} ${USER_NAME} -s /bin/bash && \
    usermod -a -G ${USER_NAME} root && \
    install -d -m 0755 -o ${USER_NAME} -g ${USER_NAME} /home/${USER_NAME}

RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install analysis-icu
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install analysis-phonetic
#RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install x-pack
