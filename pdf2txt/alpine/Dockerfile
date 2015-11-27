FROM alpine:3.2

RUN apk update && apk add python git && \
    git clone https://github.com/euske/pdfminer.git && \
    cd /pdfminer && \
    python setup.py install && \
    cd / && \
    apk del git && \
    rm -rf /var/cache/apk/* && \
    rm -rf /pdfminer

ENTRYPOINT ["pdf2txt.py"]
