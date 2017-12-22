justmail - Just Mail
--------------------

justmail --self "Some data"
justmail --self --subject "This is cool" "Some data"
justmail --to someone@gmail.com --cc someone.else@gmail.com


--to		-t	Email address/es of the recipient/s
--self			Like `--to SELF` where SELF is found in configuration or by the env var JUSTMAIL_SELF_EMAIL
--subject	-s	Email subject
-cc		-c	Carbon copy
-bcc		-b	Blind Carbon copy
--version	-V	Show version info


justq - Just Queue
------------------

# Examples (bash)

```bash
    cat "banana\norange\napple\npear" > fruits.txt
    justq push "banana"                          # queue now holds "banana"
    justq pull                                   # -> "banana"
    justq peek -n 3                              # -> "banana1\norange\napple"
    justq peek -n 3 -D "-"                       # -> "banana1-orange-apple"
    justq pull -n 3 | sed "s/a/u" | justq push   # queue now has "bunana", "orunge", "upple", "peur"
    justq peek --all | head -n 10
    justq push -q "badfruits" "pineapple"
```

# Commands shared by peek, push, pull:

    -n --lines NUM
    -A --all
    -s --silent
    -v --verbose
    -vv
    -a --alternative --alt
    -q --queue JUSTQ_QUEUE_NAME
    -Q --existing-queue (like queue but crash if queue doesn't exist)
    
# Aliases:

    clear -> pull --all --silent
