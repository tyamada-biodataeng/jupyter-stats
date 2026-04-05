FROM python:3.13

ARG DIR_WORK
WORKDIR ${DIR_WORK}

ARG REQ_TXT
COPY ${REQ_TXT} .
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r ${REQ_TXT} && \
    pip cache purge

RUN useradd -m app && \
    chown -R app:app ${DIR_WORK}

USER app
CMD ["/bin/bash"]
