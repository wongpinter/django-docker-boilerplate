FROM python:3.9-alpine

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHINUNBUFFERED 1

# install psycopg2 dependencies
RUN apk add --update --no-cache --virtual .tmp-build-deps \
	gcc libc-dev linux-headers postgresql-dev

RUN pip install --upgrade pip

COPY ./requirements.txt .

RUN pip install -r requirements.txt

RUN apk del .tmp-build-deps

# copy entrypoint.sh
COPY ./entrypoint.sh .

COPY . .

# run entrypoint.sh
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
