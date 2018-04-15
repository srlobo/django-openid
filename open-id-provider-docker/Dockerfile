FROM python:3.6-alpine3.7

RUN apk update
RUN apk add \
		binutils \
		binutils-libs \
		dev86 \
		gcc \
		gcc \
		gmp \
		isl \
		libatomic \
		libgcc \
		libgomp \
		libstdc++ \
		linux-headers \
		mpc1 \
		mpfr3 \
		musl \
		musl-dev \
		musl-utils \
		openldap-dev \
		pkgconf \
		&& true

RUN pip install uwsgi

COPY requirements.txt /
RUN pip install -r /requirements.txt && rm -f requirements.txt

RUN apk del gcc binutils-libs binutils gmp isl libgomp libatomic pkgconf \
		libgcc mpfr3 mpc1 libstdc++ gcc musl dev86 musl-utils musl-dev \
		linux-headers && rm -f requirements.txt

RUN mkdir /app /data
WORKDIR /app
COPY open_id_provider /app/

VOLUME /data
EXPOSE 8000

CMD ["/app/manage.py", "runserver", "0.0.0.0:8000"]
