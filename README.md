# `kubectl-halloween` - kubectl plugin halloween mode

[![Twitter](https://img.shields.io/badge/twitter-@scraly-blue.svg)](http://twitter.com/scraly)
[![GitHub release](https://img.shields.io/github/release/scraly/kubectl-halloween.svg)](https://github.com/scraly/kubectl-halloween/releases)

<p align="center">
    <img src="assets/logo.jpg" alt="kubectl-halloween" width=96>
</p>

## General

`halloween` is a kubectl plugin that add a random halloween emoji before your Kubernetes resources.
It is written in BASH.

## Install

### Krew

This plugin is available through [krew](https://krew.dev).

1. [Install Krew](https://github.com/GoogleContainerTools/krew) plugin manager for kubectl.
2. Add scraly's custom index `kubectl krew index add scraly https://github.com/scraly/krew-index`
3. Install the plugin `kubectl krew install scraly/halloween`
4. Run `kubectl krew install halloween`
5. Update plugin with `kubectl krew upgrade scraly/halloween`

### Binary

You can find the latest binaries in the [releases](https://github.com/scraly/kubectl-halloween/releases) section.  
To install it, place it somewhere in your `$PATH` for `kubectl` to pick it up.

**Note**: If you build from source or download the binary, you'll have to change the name of the binary to `kubectl-halloween` (`-` to `_` in `halloween`)
due to the enforced naming convention for plugins by `kubectl`. More on this [here](https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/#naming-a-plugin).

## Usage

`kubectl halloween <resource_type>`

```
$ kubectl halloween deploy                                                                                                                        
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
🧟 httpbin    1/1     1            1           26h
🧟 my-nginx   3/3     3            3           44h
🧟 traefik    3/3     3            3           6d
```

```
$ kubectl halloween po, deploy 
NAME                            READY   STATUS    RESTARTS   AGE
🎃 pod/httpbin-c9cb9cbf6-r2gnc     1/1     Running   0          2d2h
🎃 pod/my-nginx-75897978cd-f28j9   1/1     Running   0          2d21h
🎃 pod/my-nginx-75897978cd-pt2dx   1/1     Running   0          44h
🎃 pod/my-nginx-75897978cd-w2bcg   1/1     Running   0          43h
🎃 pod/traefik-85854f965f-pb6j2    1/1     Running   1          174m

NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
🎃 deployment.apps/httpbin    1/1     1            1           2d2h
🎃 deployment.apps/my-nginx   3/3     3            3           2d21h
🎃 deployment.apps/traefik    1/1     1            1           7d
```

## TODO

* Afficher des emojis differents selon le type de ressource en random

## Changelog

See the [CHANGELOG](CHANGELOG.md) file for details.