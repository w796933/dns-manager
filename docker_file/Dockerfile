FROM python:3.6-alpine
WORKDIR /code
VOLUME /code
COPY peb-dns/docs/install/requirements.txt /code
RUN pip install -r requirements.txt
ADD https://cdn.mysql.com//Downloads/Connector-Python/mysql-connector-python-2.1.7.tar.gz /tmp/
RUN tar -xvf /tmp/mysql-connector-python-2.1.7.tar.gz -C /tmp/
WORKDIR /tmp/mysql-connector-python-2.1.7/
RUN python setup.py install
ENV FLASK_APP=/peb-dns/app.py
EXPOSE 8080
