# T

##T
![Block schema](../schema/workshop-schema-docker.png "Schema for IQRF GWs in Docker")

- IQRF  (configuration in [iqrf-daemon-config1](iqrf-daemon-config1) folder)

```Bash
docker network create --subnet 10.1.0.0/16 --gateway 10.1.0.1 --ip-range=10.1.1.0/24 -driver=bridge --label=host1network bridge01
```

