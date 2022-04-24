# Objective

This blog post describes the steps required to setup a multi node Kubernetes cluster for development purposes. This setup provides a production-like cluster that can be setup on your local machine. Multi node clusters in development environment can help solve problems or bugs that are related to application design and architecture and thats the reason a, a setup like this interests me.

The setup can be slightly modified without problems (only Vabrant installation) for linux, but I have done it  on MAC.


# Why use Vagrant and Ansible? 

Vagrant is a tool that will allow us to create a virtual environment easily and it eliminates pitfalls that cause the works-on-my-machine phenomenon. It can be used with multiple providers such as Oracle VirtualBox, VMware, Docker, and so on. It allows us to create a disposable environment by making use of configuration files.

Ansible is an infrastructure automation engine that automates software configuration management. It is agentless and allows us to use SSH keys for connecting to remote machines. Ansible playbooks are written in yaml and offer inventory management in simple text files.

# Installation

On macbook/dev machine, install vagrant

    brew install vagrant #for mac

Create `Vagrantfile` to configure number of nodes and respective OS installation

Create `kubernetes-setup` directory in same location where `Vagrantfile` is created and create ansible playbooks both for master and slave nodes.

Finish the installation with executing below command where `Vagrantfile` is placed

    vagrant up