# Convert pdf to plain text file
# Suppose you have a pdf file named `sample.pdf` in ~/app folder.

# $ docker pull bwits/pdf2txt
# $ alias pdf2txt="docker run -ti --rm -v ~/app:/app pdf2txt"
# $pdf2txt sample.pdf > sample.txt

# You will get the txt file named `sample.txt` in ~/app folder.

# You can directly run below command to convert the pdf file in current foler.
# $ docker run -ti --rm -v $(pwd):/app pdf2txt sample.pdf > sample.txt

FROM alpine:3.2

RUN apk update && apk add python git && \
    git clone https://github.com/euske/pdfminer.git && \
    cd /pdfminer && \
    python setup.py install && \
    cd / && \
    apk del git && \
    rm -rf /var/cache/apk/* && \
    rm -rf /pdfminer

WORKDIR /app

ENTRYPOINT ["pdf2txt.py"]
CMD ["-h"]
