# Kibana

Windows Server Core image for [Kibana](https://www.elastic.co/products/kibana).

# Usage

Assumes you're running Elasticsearch in a container called `elasticsearch`.

Run in the background to start a containerized Kibana node:

```PowerShell
docker run -d -p 5601:5601 --name kibana dockersamples/kibana:windowsservercore
```

And open the homepage:

```PowerShell
$ip = docker inspect -f '{{ .NetworkSettings.Networks.nat.IPAddress }}' kibana
start "http://$($ip):5601"
```

