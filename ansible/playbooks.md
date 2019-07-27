## Playbooks

Execute playbook: ```ansible-playbook playbook.yml -f 10```   #Parallelism 10

Task: A call to an ansible module.
Plays: single play- orchestrate single group deployment like [webserver]
multiple plays- orchestrate multi-machine deployments, running certain steps on all machines in the webservers group, then certain steps on the database server group, then more commands back on the webservers group, etc.
Idepotency of module and playbook
The `command` and `shell` modules are the only modules that just take a list of arguments and don’t use the key=value form.
host, task, handlers

Handler:Handlers are just like regular tasks in an Ansible playbook (see Tasks), but are only run if the Task contains a “notify” directive and also indicates that it changed something.
A task that can be reused multiple times whilst the Playbook runs when some condition encounters. Handlers are called using the notify syntax.
Defined globally outside a play and can be called by the notify property in case of state change during task execution.
**listen**  in handlers

>list
1. host
2. name
3. service
4. all handlers



ansible-playbook with the --syntax-check
ansible-playbook playbook.yml --list-hosts

## Reusable Playbooks

#### There are 3 ways do this: **includes, imports, and roles.**

Ansible has two modes of operation for reusable content: dynamic and static.
If you use any import* Task (import_playbook, import_tasks, etc.), it will be static. If you use any include* Task (include_tasks, include_role, etc.), it will be dynamic.
Ansible pre-processes all static imports during Playbook parsing time.
Dynamic includes are processed during runtime at the point in which that task is encountered.


