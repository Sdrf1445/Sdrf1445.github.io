---
layout: page
title: Affine Cipher in C
description: A code for affine cipher in c 
importance: 2
category: work
---

Ok so , this is just a little project done in c for affien cipher
Here's the code:

```c
#include <stdlib.h>
#include <string.h>
char* EncryptString(char* input)
{
  int length = strlen(input);

  char* result = malloc((length + 1) * sizeof(char));
  result[length] = '\0';

  for(int i = 0; i < length;i++)
  {
    result[i] = (5 * input[i] + 1445) % 128;
  }
  return result;

}
char* DecryptString(char* input)
{
  int length = strlen(input);

  char* result = malloc((length + 1) * sizeof(char));
  result[length] = '\0';

  for(int i = 0; i < length;i++)
  {
    int test = (77*(input[i] - 1445)) % 128;
    while (test < 0){
      test+= 128;
    }
    result[i] = test;
  }
  return result;



}
```

