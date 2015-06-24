# 3-node kubernetes cluster running on CoreOS

## Get it up and running

Note: every time you run `vagrant up`, discovery token in `user-data` will be
replaced.

```
git clone https://github.com/vaijab/kubernetes-coreos.git
cd kubernetes-coreos
vagrant up
```

Wait for all the nodes to come up and then `vagrant ssh core-01`. You need to
clone this repo again on one of the coreos nodes to start fleet units:

```
fleetctl start kubernetes-coreos/units/*.service
```

## Talking to kubernetes

There is a `kubectl` tool on each node in `/opt/bin/kubectl`. API server is
always available on http://localhost:8080.

```
kubectl get nodes
```

