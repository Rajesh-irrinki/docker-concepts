ARG version
FROM almalinux:${version:-8}

ARG AUTHOR="Rajesh"
ARG OS="RHEL"
ARG version

RUN echo "Docker file written by ${AUTHOR}, almalinux version is ${version}"
ENV AUTHOR=${AUTHOR}

CMD ["sleep","100"]