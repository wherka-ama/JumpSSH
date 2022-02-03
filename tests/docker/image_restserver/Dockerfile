FROM jumpssh/image_sshd:latest

ADD app.py /restserver/app.py

RUN apk add --update \
    python3 \
    py3-pip \
  && pip install --upgrade pip \
  && pip install flask -U \
  && rm -rf /var/cache/apk/* \
  && adduser -D app \
  && mkdir -p /restserver \
  && chown -R app:app /restserver \
  && chmod a+rx /restserver/app.py

USER app

CMD python3 /restserver/app.py

EXPOSE 5000
