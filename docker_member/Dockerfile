ARG PARITY_VERSION=${PARITY_VERSION}
FROM parity/parity:${PARITY_VERSION}
ARG NETWORK_NAME=${NETWORK_NAME}
USER root
RUN mkdir -p /parity/config
RUN chown -R parity: /parity/config
COPY --chown=parity ./parity/keys /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}.
RUN mkdir -p /home/parity/.local/share/io.parity.ethereum/chains/${NETWORK_NAME}/db
RUN chown -R parity: /home/parity/.local/share/io.parity.ethereum
USER parity
