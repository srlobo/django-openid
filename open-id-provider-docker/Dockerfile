FROM python:3.6-alpine3.7

RUN apk update
RUN apk add gcc binutils-libs binutils gmp isl libgomp libatomic pkgconf \
		libgcc mpfr3 mpc1 libstdc++ gcc musl dev86 musl-utils musl-dev \
		linux-headers

RUN pip install uwsgi django django-oidc-provider
RUN pip install django django-oidc-provider

RUN apk del gcc binutils-libs binutils gmp isl libgomp libatomic pkgconf \
		libgcc mpfr3 mpc1 libstdc++ gcc musl dev86 musl-utils musl-dev \
		linux-headers

CMD ["sh"]
