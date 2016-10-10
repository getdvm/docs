## service create

    Usage:	hyper service create [OPTIONS] NAME

    Create a new service

    --algorithm=roundrobin       Algorithm for load balance
    --container-port             Container publish port for container
    -e, --env=[]                 Set environment variables
    --entrypoint                 Overwrite the default ENTRYPOINT of the image
    --env-file=[]                Read in a file of environment variables
    --health-check-fall=3        Health check fall for container
    --health-check-interval=3    Health check interval for the container
    --health-check-rise=2        Health check rise for container
    --help                       Print usage
    -i, --interactive            Keep STDIN open even if not attached
    --image                      Image name
    -l, --label=[]               Set meta data on a container
    --label-file=[]              Read in a line delimited file of labels
    --protocol=tcp               Protocol for load balance
    --replicas=-1                Replicas number for container
    --service-port               Service publish port for service container
    --service-size=s4            Service size for service container
    --session-affinity           Session Affinity
    --sg=[]                      Security group for each container
    --size=s4                    The type for each instance (e.g. s1, s2, s3, s4, m1, m2, m3, l1, l2, l3)
    --ssl-cert                   SSL cert file for service load balance
    --stop-signal=SIGTERM        Signal to stop a container, SIGTERM by default
    -t, --tty                    Allocate a pseudo-TTY
    -v, ---volume=[]             Volume for each container
    -w, --workdir                Working directory inside the container

Creates a new service based on the image and options.

### Examples

**Create a http service:**

    $ hyper service create --service-port=80 --label=app=nginx --image=nginx --replicas=3 http
    http

**Create a https termination service:**

First gets a https certificate from certificate:

    $ certificate certonly --standalone -d yourdomain.com
    $ cat fullchain.pem privkey.pem > cert.pem

Then create a service with protocol `httpsTerm`:

    $ hyper service create --service-port=443 --container-port=80 --label=app=nginx --image=nginx --replicas=3 --ssl-cert=cert.pem --protocol=httpsTerm https
    https
