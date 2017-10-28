FROM pottava/groovy
MAINTAINER Rao version:0.1
LABEL java.version=1.8 groovy.version=2.4 soapui.version=5.3.0 ant.version=1.9.4 hermes.version=1.14
COPY . /opt
RUN mv /opt/soapui-settings.xml /root \
    && chmod +x /opt/*sh \
    && mv /opt/*sh /app \
    && mv /opt/demo*xml /app \
    && mv /opt/build.xml /app
ENV SOAPUI_HOME=/opt/SoapUI-5.3.0 \
    ANT_HOME=/opt/apache-ant-1.9.4 \
    HERMES_HOME=/opt/HermesJMS \
    CLASSPATH=/opt/apache-ant-1.9.4/lib \
    RESULTS=/tmp/Results
ENV PATH="${SOAPUI_HOME}/bin:${ANT_HOME}/bin:${HERMES_HOME}/bin:${PATH}"
ENTRYPOINT ["/app/entry-point.sh"]
CMD ["/opt/SoapUI-5.3.0/HelloWS-soapui-project.xml"]
