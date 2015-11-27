## convert pdf to plain text file

Suppose you have a pdf file named `sample.pdf` in your current folder.
```
docker pull bwits/pdf2txt
docker run -ti --rm -v $(pwd):/app pdf2txt /app/sample.pdf > sample.txt
```
You will get the txt file named `sample.txt` in your current folder.
