# Command overview

justq - Just Queue
==================

### Synopsis

    justq [push|pull|] [SUBCOMMAND-OPTIONS]

### Examples (bash)

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

### Options

#### Shared by subcommands peek, push, pull:

    -n, --lines NUM
    -A, --all
    -s, --silent
    -v, --verbose
    -vv
    -a, --alternative, --alt
    -q, --queue JUSTQ_QUEUE_NAME
    -Q, --existing-queue
            like queue but crash if queue doesn't exist
            
#### Global

    -V, --version

    
### Aliases

Alias              | For                             
-------------------|------------------------
clear              | pull --all --silent             
    
-------------------------------------------------------------------------------
    
justmail - Just Mail
====================

### Synopsis

    justmail [OPTIONS] [DATA_TO_SEND]

### Examples (bash)

```bash
justmail --self "Some data"
justmail --self --subject "This is cool" "Some data"
justmail --to "someone@gmail.com" --cc "someone.else@gmail.com"
```

### Options

    -t --to         Email address/es of the recipient/s
       --self       Like `--to SELF` where SELF is found in configuration or by the environment variable
                    JUSTMAIL_SELF_EMAIL
    -s --subject    Email subject
    -c -cc          Carbon copy
    -b -bcc         Blind Carbon copy
    -V --version    Show version info
