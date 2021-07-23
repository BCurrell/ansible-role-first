# ansible-role-first

Ansible role used for first-time setup of an endpoint, in preparation for future Ansible use.

---

### What does this role do?

This role has 3 main responsibilites:

1. Set up an Ansible user, and optionally an unprivileged user for you.
	- This includes SSH keys for passwordless authentication.
2. Install any packages required by the Ansible package modules.
	- Also, install any packages we need for this role (like `sudo`).
3. Optionally set up sudo for the Ansible and unprivileged users.

### Why is this role separate from another common / bootstrap role / playbook?

Since this role is used to set up the Ansible user, it will most likely be run with the `root` user, and/or run manually as a one-off rather than part of standard configuration state management. Once the Ansible user is set up, it can be used for all future roles and playbooks.
