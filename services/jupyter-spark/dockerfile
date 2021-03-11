ARG BASE_CONTAINER=abxda/geobigdata:0.19
FROM $BASE_CONTAINER

# Switch to user root so we can add additional jars, packages and configuration files.
USER root

RUN apt-get -y update && apt-get install -y coreutils

RUN rm -rf $SPARK_HOME/jars/httpclient-4.5.6.jar

# Add dependency for hadoop-aws
ADD https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk/1.11.883/aws-java-sdk-1.11.883.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/aws-java-sdk-1.11.883.jar

ADD https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-core/1.11.883/aws-java-sdk-core-1.11.883.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/aws-java-sdk-core-1.11.883.jar

ADD https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-dynamodb/1.11.883/aws-java-sdk-dynamodb-1.11.883.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/aws-java-sdk-dynamodb-1.11.883.jar

ADD https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-s3/1.11.883/aws-java-sdk-s3-1.11.883.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/aws-java-sdk-s3-1.11.883.jar

ADD https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.2.0/hadoop-aws-3.2.0.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/hadoop-aws-3.2.0.jar

ADD https://repo1.maven.org/maven2/org/apache/httpcomponents/httpclient/4.5.9/httpclient-4.5.9.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/httpclient-4.5.9.jar 

ADD https://jdbc.postgresql.org/download/postgresql-42.2.19.jar $SPARK_HOME/jars
RUN chmod -R 644 $SPARK_HOME/jars/postgresql-42.2.19.jar


#Required for minIO service discovery by name.
ADD /config/spark-defaults.conf /opt/spark/conf/


#ENTRYPOINT ["/opt/entrypoint.sh"]

