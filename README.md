# ansible-hash-merge-test
test hash merging for ansible

as soon as jinga2 statements are in use, the hash merging will not work as expected :exclamation:

you must use a interim var for the jinja2 construct and a explicit merge using combine filter:

```yaml
    - ansible.builtin.set_fact:
        dictmerge_two: "{{ dictmerge_two | combine(dictmerge_interim) }}"
```

