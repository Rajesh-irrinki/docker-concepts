FROM almalinux:9

RUN dnf install nginx -y

LABEL app="frontend" \
      AUTHOR="Rajesh"

EXPOSE 80

CMD ["nginx","-g","daemon off;"]