# Run BKCI's learning environment with One-Docker
We provide a single container [BKCI](https://hub.docker.com/r/blueking/bk-ci) deployment plan, only for demonstration.
Create a container named bkci-demo and pass port 80 of the host to port 80 in the container:

```text
docker run -p 80:80 --name bkci-demo -dit blueking/bk-ci
```

Observe the container startup log output:
```text
docker logs -f bkci-demo
```

When all services are successfully started, the following information is displayed:
> The service starts successfully. You can input [http://devops.bktencent.com](http://devops.bktencent.com/) in your browser to access bkci. \(please configure DNS or hosts in advance\)

