
FROM demisto/python3:3.10.8.35482

RUN mkdir /opt/scripts

COPY scripts /opt/scripts

COPY requirements.txt .

RUN apk --update add --no-cache nmap nmap-scripts

RUN apk --update add --no-cache --virtual .build-dependencies python3-dev build-base wget git \
  && pip install --no-cache-dir -r requirements.txt \
  && apk del .build-dependencies
