FROM openjdk:11-jre-slim
ENV SPARK_VERSION=3.4.0 \
    HADOOP_VERSION=3.3

RUN wget https://archive.apache.org/dist/spark/spark-${SPARK_VERSION}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz \
    && tar xzf spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz \
    && mv spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION} /opt/spark \
    && rm spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz

ENV SPARK_HOME=/opt/spark \
    PATH=$PATH:/opt/spark/bin

# 라이브러리 커넥터 명시
# COPY jars/mysql-connector-java.jar $SPARK_HOME/jars/
ENTRYPOINT ["/opt/spark/bin/spark-class"]
