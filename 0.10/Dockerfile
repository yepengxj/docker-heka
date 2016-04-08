FROM ianneub/go:1.4

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y cmake python-sphinx protobuf-compiler debhelper && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && \
    mkdir /heka && \
    wget https://github.com/mozilla-services/heka/releases/download/v0.10.0/heka_0.10.0_amd64.deb -O /heka/heka_0.10.0_amd64.deb && \
    dpkg -i /heka/heka_0.10.0_amd64.deb

EXPOSE 4881

CMD ["hekad", "--config", "/app/config.toml"]
