FROM debian:8
MAINTAINER Sverrir A. Berg <sab@keilir.com>

RUN apt-get update &&                               \
    apt-get install -y --no-install-recommends      \
        iperf

EXPOSE 33001

ENTRYPOINT ["iperf"]

CMD ["-s", "-p", "33001", "-u"]
