FROM alpine:3.23.3

# renovate: datasource=repology depName=alpine_3_23/openvpn versioning=loose
ENV OPENVPN_VERSION="2.6.16-r0"

RUN apk add --no-cache openvpn=${OPENVPN_VERSION} easy-rsa iptables bash
RUN ln -s /usr/share/easy-rsa/easyrsa /usr/bin/easyrsa

USER openvpn

ENV EASYRSA_BATCH="1"
ENV EASYRSA_CRL_DAYS="3650"
ENV EASYRSA="/usr/share/easy-rsa"
ENV EASYRSA_PKI="/etc/openvpn/pki"
ENV EASYRSA_ALGO="ec"
ENV EASYRSA_DIGEST="sha512"

CMD ["openvpn", "--config", "/etc/openvpn/openvpn.conf"]
