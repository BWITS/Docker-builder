FROM alpine:3.2

# Installs Android SDK
ENV ANDROID_SDK_FILENAME android-sdk_r23.0.2-linux.tgz
ENV ANDROID_SDK_URL http://dl.google.com/android/${ANDROID_SDK_FILENAME}
ENV ANDROID_API_LEVELS android-15,android-16,android-17,android-18,android-19,android-20,android-21 
ENV ANDROID_BUILD_TOOLS_VERSION 21.1.0
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools
WORKDIR /opt
RUN wget -q ${ANDROID_SDK_URL}
RUN tar -xzf ${ANDROID_SDK_FILENAME}
RUN rm ${ANDROID_SDK_FILENAME}
RUN apk update && apk add openjdk7
RUN echo y | android update sdk --no-ui -a --filter tools,platform-tools,${ANDROID_API_LEVELS},build-tools-${ANDROID_BUILD_TOOLS_VERSION} --no-https

