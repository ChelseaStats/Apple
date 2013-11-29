some code to try and find incorrect permissions

    find ~ $TMPDIR.. \( -flags +sappnd,schg,uappnd,uchg -o ! -user $UID -o ! -perm -600 -o -acl \) 2> /dev/null | wc -l
