---
layout: page
title: Pi estimater
description: Estimate pi with random numbers
importance: 1
category: work
tags: PI random
related_publications: true
---

Nothing much to say here.
Here's the full code btw:

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>


int isitInsideCircle(int x, int y, int a) {
    if( x*x + y*y <= a*a) {
        return 1;
    }
    return 0;
}

int main() {
    srand(time(NULL));
    int total = 0;
    int inside = 0;
    int a = RAND_MAX / 2;



    for (int i = 0; i < 10000; i++) {
        int x = rand() - RAND_MAX / 2;
        int y = rand() - RAND_MAX / 2;
        total++;

        if(isitInsideCircle(x, y, a)) {
            inside++;
        }
    }
    printf("%f",(float)4*inside/total);

    return 0;
}
```

