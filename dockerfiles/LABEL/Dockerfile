FROM almalinux:9
RUN dnf install nginx -y
LABEL app="frontend" \
      maintainer="rajesh"
CMD ["nginx","-g","daemon off;"]
