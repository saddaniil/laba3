#!/bin/bash

laba2() {
    if [ $1 -eq 10 ]; then
        echo $3
        return
    fi

    next=$(expr $1 + 1)
    cur=${arr[$1]}

    if [ $cur -gt $2 ]; then
        laba2 $next $cur $2
    elif [ $cur -gt $3 ]; then
        laba2 $next $2 $cur
    else
        laba2 $next $2 $3
    fi
}

echo "vvedite 10 chisel:"
read -a arr

if [ ${arr[0]} -gt ${arr[1]} ]; then
    laba2 2 ${arr[0]} ${arr[1]}
else
    laba2 2 ${arr[1]} ${arr[0]}
fi

