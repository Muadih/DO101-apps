FROM registry.access.redhat.com/rhscl/httpd-24-rhel7

CMD ab -dSrk -c 20 -n 50000000 http://${SCALE2_SERVICE_HOST}:${SCALE2_SERVICE_PORT}/index.php
