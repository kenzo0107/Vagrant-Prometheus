# setup simple Prometheus Monitoring architecture in Vagrant by Ansible >= 1.9.

download Prometheus server & client source, and run it via supervisor.

#### Sample playbook:

- CentOS 6.5
- Prometheus Server 0.20.0
- Supervisor 3.3.0
- Go 1.6.2
- Ansibl 2.1.0.0
- Vagrant 1.8.1
- MacOSX 10.11.5

## Prerequisite

Installed bellow tools

* VirtualBox
* Vagrant
* Ansible


## Usage

#### 1. git clone this repository

```
$ git clone https://github.com/kenzo0107/Vagrant-Prometheus
```

#### 2. VagrantVM Build

```
$ cd Vagrant-Prometheus
$ vagrant up
```

3 node running !  

- 1 node: Prometheus Server
- - 192.168.11.30
- other 2 nodes: Prometheus Client Server
- - 192.168.33.31
- - 192.168.33.32

#### 3. add ssh.config

```
$ vagrant ssh-config > ssh.config
```

#### 4. ping

```
$ ansible default -m ping

server | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
client1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
client2 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

ok, success.

#### 6. set PrometheusClient

```
$ ansible-playbook set_clients_prometheus.yml
```

#### 7. confirm PrometheusClient.

access to the below:

- <http://192.168.11.31:8080>  
- <http://192.168.11.32:8080>

<img src="http://i.imgur.com/igPci2Z.png" width="400px" />


#### 8. set PrometheusServer

```
$ ansible-playbook set_server_prometheus.yml
```

#### 9. confirm PrometheusServer.

access to <http://192.168.33.30:9090>

<img src="http://i.imgur.com/XDTarz3.png" width="400px" />

OK !
