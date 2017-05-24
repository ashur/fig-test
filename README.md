# fig-test

A repository for testing supported features and previous known issues in [Fig][fig].


## Setup

1. [Install Fig][fig-install]
1. Add this repository as a Fig app:

~~~
$ fig add fig-test --url=https://github.com/ashur/fig-test.git
~~~

[fig]: https://github.com/ashur/fig
[fig-install]: https://github.com/ashur/fig/wiki/getting-started


## Usage

Deploy a test profile and verify that actual output matches the definition file.

**vars.yml**
~~~
# vars
---

- vars:
    greetings: hello
    who: world

- name: hello
  command: echo '{{ greetings }}, {{ who }}.'

# EXPECTED OUTPUT ----------------------------------------------------------------

# COMMAND: hello *****************************************************************
# hello, world.

# --------------------------------------------------------------------------------
~~~

**Actual output**
~~~
$ fig deploy fig-test/vars

COMMAND: hello *****************************************************************
hello, world.
~~~
