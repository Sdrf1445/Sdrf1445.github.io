---
layout: page
title: 
description: a project that redirects to another website
img: assets/img/7.jpg
redirect: https://unsplash.com
importance: 3
category: work
---

So this thing sort arrays , I think ?? Maybe not I don't know.
I'm just filling it with a bunch of nonesense to be honest...

```c
#include <stdio.h>
#include <stdlib.h>


int* defineArray(int length)
{
  return malloc(length * sizeof(int));
}
void getInputArray(int* array,int length)
{
  for(int i = 0; i < length;i++)
  {
    scanf("%d",(array + i));
  }
}
int findMinIndexArray(int* array,int length,int startIndex)
{
  int index = startIndex;
  int min = *(array + startIndex);
  for(int i = startIndex + 1; i < length;i++)
  {
    if(min > *(array + i ))
    {
      min = *(array + i);
      index = i;
    }
    
  }
  return index;

}
void swap(int* ptr1,int* ptr2)
{
  int temp = *(ptr1);
  *ptr1 = *ptr2;
  *ptr2 = temp;
}
void sortArray(int* array,int length)
{
  for(int i = 0; i < length;i++)
  {
    int index = findMinIndexArray(array, length, i);
    swap(array + i, array + index);
  }
}
void printArray(int* array,int length)
{
  for(int i = 0; i < length;i++)
  {
    printf("%d\n",*(array + i));
  }
}
int main()
{
  int length;
  scanf("%d",&length);

  int* array = defineArray(length);
  getInputArray(array, length);

  sortArray(array, length);
  printArray(array, length);
  return 0;
}
```

