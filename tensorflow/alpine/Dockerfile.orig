ADD file:e97fe9bddafcfac4ca966c9cc2bab9526cc3f722df71710f4b7c6349de2db82b in /
RUN echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
CMD ["/bin/bash"]
MAINTAINER Craig Citro <craigcitro@google.com>
RUN apt-get update && apt-get install -y curl libfreetype6-dev libpng12-dev libzmq3-dev pkg-config python-numpy python-pip python-scipy && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN pip install jupyter matplotlib
RUN pip install https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.5.0-cp27-none-linux_x86_64.whl
RUN curl -O https://bootstrap.pypa.io/get-pip.py && python get-pip.py && rm get-pip.py && pip --no-cache-dir install requests[security]
RUN pip --no-cache-dir install ipykernel && python -m ipykernel.kernelspec
COPY file:617470c4514ec5022696f3b3ed341947c185999efb40634fc8555b5effc0e61e in /root/.jupyter/
COPY file:a7af486c3e6a1a7cf9f24056708dfab1a3c93d165b4e14073db6247869229f54 in /
EXPOSE 6006/tcp
EXPOSE 8888/tcp
CMD ["/bin/bash"]
