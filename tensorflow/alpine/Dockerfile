FROM alpine:3.2

RUN echo "@testing http://dl-4.alpinelinux.org/alpine/edge/testing" >>/etc/apk/repositories
RUN apk update
RUN apk add alpine-sdk freetype-dev libzmq python-dev musl-dev py-pip py-numpy@testing
RUN apk add py-numpy-dev@testing libffi-dev openssl-dev swig py-scipy@testing
RUN pip install --upgrade pip
RUN pip install jupyter matplotlib
RUN pip install https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.5.0-cp27-none-linux_x86_64.whl
RUN curl -O https://bootstrap.pypa.io/get-pip.py && python get-pip.py && rm get-pip.py && pip --no-cache-dir install requests[security]
RUN pip --no-cache-dir install ipykernel && python -m ipykernel.kernelspec
ADD jupyter_notebook_config.py /root/.jupyter/
ADD run_jupyter.sh  /
EXPOSE 6006/tcp
EXPOSE 8888/tcp
CMD ["/bin/bash"]
