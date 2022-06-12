### This projects aim is to understand Taints and Tolerations.

* Tolerations are the opposite of Affinty

* Taints are not hard requirements.(unless ths taint is NoSchedule)

* Master node is always tainted automatically for not to be scheduled unless toleration specified so.

Key specifications are;
    key:
    operator:
    value:
    effect:
    

---

* First create a tainted node or taint an existing node before creating tolerations.yaml