FROM jameslp/autograder-sandbox:3.1.2

RUN apt-get update --fix-missing && \
    apt-get install -y software-properties-common python3-software-properties \
                       python3-dev python3-pip python3-venv

RUN add-apt-repository ppa:webupd8team/java && apt-get update
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
    apt-get install -y oracle-java8-installer
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle
ENV JAVA_TOOL_OPTIONS -Xms512m -Xmx512m -XX:+UseSerialGC -XX:MaxMetaspaceSize=256m -XX:CompressedClassSpaceSize=128m

RUN apt-get install -y libz-dev cobertura maven
RUN apt-get install -y unzip

RUN pip3 install astor coverage
RUN pip3 install pycodestyle
RUN pip3 install codegen astpretty
