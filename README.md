# evil_ansible
Ansible playbooks for evil 

Replace <my*> values, then load into ansible via git download

ansible_remote_shell.yml is for a shell from a box that ansible can talk to but is not the ansible box itself

ansible_local_shell.yml is for a shell from the ansible box itself (this will likely be the amx user and probably not have su privs)

Both of these /\ use tcp sockets to avoid a dependency on netcat, so the shell maybe a bit flaky for some things, esp those commands that have muti-line output.

ansible_rce.yml is for executing commands with su on a system remote from ansible. Multi-line command output will often result in the job thinking it errored, but the output should generally be there between stdout and stderr.
