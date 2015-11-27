## convert html file to plain text file

support the html file `test.html` is at your current folder

```
docker pull bwits/html2txt
alias html2text="docker run -ti --rm -v $(pwd):/app bwits/html2txt"
html2txt /app/test.html /app/test.txt
```

Now you should have the test.txt file generated in current folder