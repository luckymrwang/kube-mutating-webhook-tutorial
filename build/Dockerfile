FROM alpine:latest

# set labels for metadata
LABEL maintainer="Morven Cao" \
  name="sidecar-injector" \
  description="A Kubernetes mutating webhook server that implements sidecar injection" \
  summary="A Kubernetes mutating webhook server that implements sidecar injection"

# set environment variables
ENV SIDECAR_INJECTOR=/usr/local/bin/sidecar-injector \
  USER_UID=1001 \
  USER_NAME=sidecar-injector

# install sidecar-injector binary
COPY build/_output/bin/sidecar-injector ${SIDECAR_INJECTOR}

# set entrypoint
ENTRYPOINT ["/usr/local/bin/sidecar-injector"]

# switch to non-root user
USER ${USER_UID}
