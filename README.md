# Playbook-k8s

This is a [Ansible Playbook](https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html) to create a [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) cluster.

---

## How to use:

In hosts file insert the IPs of master and workers. In the workers:vars set MASTER_IP with the same IP of master.


Example:

```toml
[master]
172.17.3.30

[workers]
172.17.3.45
172.17.3.80

[workers:vars]
MASTER_IP=172.17.3.30
MASTER_SECURE_PORT=6443 
```

Execute the command:

```bash
$ ansible-playbook -i hosts main.yml
```

If you're use a key file to connect in the instances use:

```bash
$ ansible-playbook -i hosts main.yml --key-file=example-key.pem
```



---

## Tips:

You can use the variable `ANSIBLE_HOST_KEY_CHECKING=False` to skip the confirmation when first connection with instances.
