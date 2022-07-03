### This projects aim is to understand pod security policies.

- It allows you to controll what volumes can be mounted, deny using privileged modes while creating pods, make sure containers run within a UID(user ID)/GID(group ID) range.
- Also can be used as extra layer of protection to make sure non of your containers can run as a root.
- Can be enabled at startup of cluster. Can be invoked with pod creation or modification.
- 2 types can be used;
    - For system processes, to run privileged/ as root
    - For pods users want to schedule tighter