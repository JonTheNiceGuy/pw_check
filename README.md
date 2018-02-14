Role Name
=========

This role takes a supplied password (via the checked_password variable) and checks it meets minimum (configurable) complexity rules (length, at least 3 of 4 character types)

Requirements
------------

None

Role Variables
--------------

* REQUIRED: checked_password: The password to *actually* check. Only a single password can be checked each time through.
* Optional: min_length: The minimum length of the string to "pass" - set to 8
* Optional: max_length: The maximum length of the string to "pass" - set to 128
* Optional: minimum_complexity: How many character groups must it have (Numbers, Symbols, Upper-case and Lower-case letters) - set to 3
* Optional: error_if_complexity_is_not_met: Should we throw an error if we do not meet minimum complexity? - Default True

Dependencies
------------

None

Example Playbook
----------------

    - hosts: localhost
      tasks:
      - include_role:
          name: pw_check
        vars:
          checked_password: abcd1234-
    - hosts: localhost
      tasks:
      - include_role:
          name: pw_check
        vars:
          checked_password: abc
          error_if_complexity_is_not_met: False

License
-------

The Unlicense

Author Information
------------------

Jon "The Nice Guy" Spriggs - https://jon.sprig.gs - https://twitter.com/jontheniceguy - jon@sprig.gs
