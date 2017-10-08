# NodeRed- IoT Starter Kit
### For editing go to yours URL/admin

- Eaxample if port mapping is set to 80:1880   [http://192.168.1.1/admin]
- Eaxample if port mapping is set to 1880:1880 [http://192.168.1.1:1880/admin]

### For login to admin
- username: admin
- password: iqrf

```Bash
sudo docker run -d -p 1880:1880 --restart=always --network=isolated_nw --ip=172.25.4.1 --name redgw jotio/iqrf_nr_iot:latest  
```

