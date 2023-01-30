FROM python:3.9.13-slim-buster as builder

# The enviroment variable ensures that the python output is set straight
# to the terminal with out buffering it first
ENV PYTHONBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1


RUN pip install --upgrade pip
COPY . /backend

COPY ./requirements.txt .
RUN pip wheel --no-cache-dir --no-deps --wheel-dir /backend/wheels -r requirements.txt


FROM python:3.9.13-slim-buster

ENV APP_DIR=/backend

RUN mkdir -p $APP_DIR


WORKDIR $APP_DIR

COPY --from=builder $APP_DIR/wheels /wheels
COPY --from=builder $APP_DIR/requirements.txt .

RUN pip install --upgrade pip
RUN pip install --no-cache /wheels/*

COPY . $APP_DIR
