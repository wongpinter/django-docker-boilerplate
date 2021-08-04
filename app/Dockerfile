FROM python:3.9-slim

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHINUNBUFFERED 1

# install psycopg2 dependencies
RUN apt-get update && apt-get install -y netcat

RUN pip install --upgrade pip

COPY ./requirements.txt .

RUN pip install -r requirements.txt

# copy entrypoint.sh
COPY ./entrypoint.sh .

COPY . .

# run entrypoint.sh
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
