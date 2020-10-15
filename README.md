# `kubectl-halloween` - kubectl plugin halloween mode

[![Twitter](https://img.shields.io/badge/twitter-@scraly-blue.svg)](http://twitter.com/scraly)
[![GitHub release](https://img.shields.io/github/release/scraly/kubectl-halloween.svg)](https://github.com/scraly/kubectl-halloween/releases)

TODO: create a logo
<p align="center">
    <img src="static/logo.png" alt="kubectl-halloween" width=96>
</p>

## General

`halloween` is a kubectl plugin that add a random halloween emoji before your Kubernetes resources.
It is written in BASH.

## Install

### Krew

This plugin is available through [krew](https://krew.dev).

1. [Install Krew](https://github.com/GoogleContainerTools/krew) plugin manager for kubectl.
2. Run `kubectl krew install halloween`.
3. Update plugin with `kubectl krew upgrade halloween`

### Binary

You can find the latest binaries in the [releases](https://github.com/scraly/kubectl-halloween/releases) section.  
To install it, place it somewhere in your `$PATH` for `kubectl` to pick it up.

**Note**: If you build from source or download the binary, you'll have to change the name of the binary to `kubectl-halloween` (`-` to `_` in `halloween`)
due to the enforced naming convention for plugins by `kubectl`. More on this [here](https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/#naming-a-plugin).

## Usage

`kubectl halloween get <resource_type>`

```
$ kubectl halloween get deploy                                                                                                                        
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
🧟 httpbin    1/1     1            1           26h
🧟 my-nginx   3/3     3            3           44h
🧟 traefik    3/3     3            3           6d
```

```
$ kubectl halloween get po  
NAME                        READY   STATUS    RESTARTS   AGE
🎃 httpbin-c9cb9cbf6-r2gnc     1/1     Running   0          26h
🎃 my-nginx-75897978cd-f28j9   1/1     Running   0          44h
🎃 my-nginx-75897978cd-pt2dx   1/1     Running   0          20h
🎃 my-nginx-75897978cd-w2bcg   1/1     Running   0          19h
🎃 traefik-6c5c6d77c9-5w455    1/1     Running   1          20h
🎃 traefik-6c5c6d77c9-64mtw    1/1     Running   1          19h
🎃 traefik-6c5c6d77c9-k5kqm    1/1     Running   1          20h
```

## TODO

* To fix:
* 
```
$ ./kubectl-halloween get deploy,po                                                                                                                                                                                      <aws:1110><aws:1110>
NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
🕷️ deployment.apps/httpbin    1/1     1            1           26h
🕷️ deployment.apps/my-nginx   3/3     3            3           44h
🕷️ deployment.apps/traefik    3/3     3            3           6d
🕷️
🕷️ NAME                            READY   STATUS    RESTARTS   AGE
🕷️ pod/httpbin-c9cb9cbf6-r2gnc     1/1     Running   0          26h
🕷️ pod/my-nginx-75897978cd-f28j9   1/1     Running   0          44h
🕷️ pod/my-nginx-75897978cd-pt2dx   1/1     Running   0          20h
🕷️ pod/my-nginx-75897978cd-w2bcg   1/1     Running   0          19h
🕷️ pod/traefik-6c5c6d77c9-5w455    1/1     Running   1          20h
🕷️ pod/traefik-6c5c6d77c9-64mtw    1/1     Running   1          19h
🕷️ pod/traefik-6c5c6d77c9-k5kqm    1/1     Running   1          20h
```


## Changelog

See the [CHANGELOG](CHANGELOG.md) file for details.