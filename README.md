# AnsibleProject
A project to deploy a static HTML website using an Ansible playbook.

# Running locally
If you want to run this locally, you would need to create two AWS EC2 Instances.
On one instance, install Ansible by typing the following commands:

```
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible

```

Now, move to the `/etc/ansible` directory, and edit the `hosts` file. Add the following:
```
[prodserver]
server ansible_host=<Public IP of the second EC2 instance>
```

Ping the server to check if it runs properly or not

```
ansible prodserver -m ping
```

On successful connection,
Copy the contents of `index.html` and  `deployWebsite.yml` into your first EC2 instance, and run the command
```
ansible-playbook deployWebsite.yml
```

Your website is up and running!
