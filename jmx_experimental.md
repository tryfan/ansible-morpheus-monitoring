# JVM Monitoring

In /opt/morpheus/sv/morpheus-ui/run
```
export JAVA_OPTS="-Xms3988m -Xmx3988m -XX:+UseG1GC -javaagent:/var/opt/morpheus/morpheus-monitoring/jmx_prometheus_javaagent-0.19.0.jar=9222:/var/opt/morpheus/morpheus-monitoring/jmx-agent-config.yaml"
```

Get Agent
``` 
wget https://repo1.maven.org/maven2/io/prometheus/jmx/jmx_prometheus_javaagent/0.19.0/jmx_prometheus_javaagent-0.19.0.jar
```

Config in /var/opt/morpheus/morpheus-monitoring/jmx-agent-config.yaml
```
rules:
- pattern: ".*"
```


