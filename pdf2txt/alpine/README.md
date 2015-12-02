## convert pdf to plain text file

[![](https://badge.imagelayers.io/bwits/pdf2txt:latest.svg)](https://imagelayers.io/?images=bwits/pdf2txt:latest 'Get your own badge on imagelayers.io')

1, Suppose you have a pdf file named `sample.pdf` in ~/app folder.
```
$ docker pull bwits/pdf2txt
$ alias pdf2txt="docker run -ti --rm -v ~/app:/app pdf2txt"
$ pdf2txt sample.pdf > sample.txt
```
You will get the txt file named `sample.txt` in ~/app folder.

2, You can directly run below command to convert the pdf file in current foler.
```
$ docker run -ti --rm -v $(pwd):/app pdf2txt sample.pdf > sample.txt
```
You will get the txt file named `sample.txt` in your current folder.
