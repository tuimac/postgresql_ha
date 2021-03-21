FROM alpine:latest

WORKDIR /root

ADD entrypoint.sh /root/entrypoint.sh

RUN wget -O /etc/apk/keys/amazoncorretto.rsa.pub  https://apk.corretto.aws/amazoncorretto.rsa.pub && \
    echo "https://apk.corretto.aws/" >> /etc/apk/repositories && \
    apk update && \
    apk upgrade && \
    apk add --no-cache git bash tzdata vim curl ncurses tree amazon-corretto-11 maven && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk del tzdata && \
    mkdir /etc/vim/backup && \
    mkdir /etc/vim/undo && \
    rm /etc/vim/vimrc && \
    curl -L https://raw.githubusercontent.com/tuimac/tools/master/vim/vimrc -o /etc/vim/vimrc && \
    curl -L https://raw.githubusercontent.com/tuimac/tools/master/linux/bashrc/.bashrc_node_docker -o /root/.bashrc && \
    git clone https://github.com/tuimac/postgresql_ha && \
    cd /root/postgresql_ha && \
    mvn clean install

ENTRYPOINT ["/root/entrypoint.sh"]
