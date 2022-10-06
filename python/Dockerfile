FROM python:TAG as run

WORKDIR /app

ENV TINI_VERSION vX.XX.X
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini-static /tini
RUN chmod +x /tini

RUN adduser app

COPY --chown=app:app requirements.txt /app

USER app
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools
RUN pip install -r requirements.txt

ENTRYPOINT ["/tini", "--"]
