ARG PARITY_VERSION=${PARITY_VERSION}
FROM parity/parity:${PARITY_VERSION}
ARG NETWORK_NAME=${NETWORK_NAME}
ARG ID=${ID}
USER root
RUN mkdir -p /parity/config
RUN chown -R parity: /parity/config
#COPY --chown=parity ./parity/config /parity/config
#RUN mkdir -p ./parity/keys /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}
#RUN chown -R parity: ./parity/keys /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}
#RUN mkdir -p ./parity/authorities/authority${ID}.json /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}/authority.json
#RUN chown -R parity: ./parity/authorities/authority${ID}.json /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}/authority.json
#RUN mkdir -p ./parity/authorities/authority${ID}.pwd /parity/authority.pwd
#RUN chown -R parity: ./parity/authorities/authority${ID}.pwd /parity/authority.pwd
COPY --chown=parity ./parity/keys /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}
COPY --chown=parity ./parity/authorities/authority${ID}.json /home/parity/.local/share/io.parity.ethereum/keys/${NETWORK_NAME}/authority.json
COPY --chown=parity ./parity/authorities/authority${ID}.pwd /parity/authority.pwd
#RUN mkdir -p ./parity/node${ID}.network.key /home/parity/.local/share/io.parity.ethereum/network/key
#RUN chown -R parity: ./parity/node${ID}.network.key /home/parity/.local/share/io.parity.ethereum/network/key
COPY --chown=parity ./parity/node${ID}.network.key /home/parity/.local/share/io.parity.ethereum/network/key
RUN mkdir -p /home/parity/.local/share/io.parity.ethereum/chains/${NETWORK_NAME}/db
RUN chown -R parity: /home/parity/.local/share/io.parity.ethereum
USER parity

