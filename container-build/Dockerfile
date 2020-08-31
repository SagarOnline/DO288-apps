# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
LABEL io.openshift.expose-services="8080:80" \
      io.k8s.description="Apache Http Server" \
      io.k8s.name="Apache Http"
EXPOSE 8080
RUN sed "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN chgrp -R 0 /var/log/http /var/run/httpd && \
    chmod -R g=u /var/log/http /var/run/httpd
USER 1001
