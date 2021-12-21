FROM ubuntu:14.04
LABEL maintainer="Michael Buluma"

VOLUME ["/sys/fs/cgroup"]
CMD ["/sbin/init"]

HEALTHCHECK --interval=5m --timeout=3s \
  CMD curl -f http://localhost/ || exit 1
