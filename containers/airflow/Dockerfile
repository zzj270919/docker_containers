FROM base

RUN yum -y update
RUN yum -y install python-setuptools
RUN yum -y update python-setuptools
RUN yum -y install gcc gcc-c++ libffi-devel python-devel python-pip python-wheel openssl-devel libsasl2-devel openldap-devel

RUN mkdir ~/airflow
RUN export AIRFLOW_HOME=~/airflow

RUN curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
RUN python get-pip.py

RUN pip install --upgrade setuptools pip
RUN pip install airflow

RUN airflow initdb

RUN airflow webserver -p 8080

ADD assets /assets


#CMD source /root/.bashrc; cd /spark; /zeppelin/bin/zeppelin.sh run
