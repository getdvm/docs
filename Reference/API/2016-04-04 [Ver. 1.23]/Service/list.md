# List services

`GET /services`

List all services Hyper knows about.

**Example request**:

```
GET /services HTTP/1.1
Content-Type: application/json
```

**Example response**:

```
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "Name": "http",
    "Image": "nginx",
    "WorkingDir": "",
    "ServiceSize": "s4",
    "ContainerSize": "s4",
    "SSLCert": "",
    "NetMode": "bridge",
    "StopSignal": "SIGTERM",
    "ServicePort": 80,
    "ContainerPort": 80,
    "Replicas": 3,
    "HealthCheckInterval": 3,
    "HealthCheckFall": 3,
    "HealthCheckRise": 2,
    "Algorithm": "roundrobin",
    "Protocol": "tcp",
    "Stdin": false,
    "Tty": false,
    "SessionAffinity": false,
    "Entrypoint": [],
    "Cmd": [],
    "Env": [],
    "Volumes": {},
    "Labels": {
      "app": "nginx"
    },
    "SecurityGroups": {},
    "IP": "172.16.55.36",
    "Tenant": "b8dc36865f4b480683dabb25598d61c4",
    "FIP": "",
    "Message": "Scaling complete",
    "Created": "2016-10-08T12:08:33.934Z",
    "Status": "active",
    "Containers": [
      "33cd52f7af63391c9b9eb578130bd46f65f3e2c00ccbe80b9ee882cf40c6043b",
      "54e3d0724f1d2b4429b08e3192c9ba13c93bd8d9077b391e6129e976eb713b7e",
      "a35a66d91e0c0740e36f9f2e43db406fefe964f5a483a8137d9c08472860a53e"
    ]
  }
]
```

**Status Codes**:

* 200 – no error
* 500 – server error
