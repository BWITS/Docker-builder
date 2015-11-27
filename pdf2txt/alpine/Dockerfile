# Convert pdf to plain text file
# Suppose you have a pdf file named `sample.pdf` in your current folder.

# $ docker pull bwits/pdf2txt
# $ docker run -ti --rm -v $(pwd):/app pdf2txt /app/sample.pdf > sample.txt

# You will get the txt file named `sample.txt` in your current folder.

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
CMD ["-h"]
