# Notes

## C

### String literals
Don't compare `char` to string literal:
```C
char str[10];
if(str[0] == "0")
    // gcc throws warning
```

Use single quotes instead:
```C
char str[10];
if(str[0] == '0')
    // gcc is happy
```

### Character Arrays
Character arrays are initialized with random characters.
The null character `(int)0` likely occurs randomly as well -- cannot
use the null character as termination condition if you have not written
characters to all its elements.

```C
char empty[20];
int i;
  for(i=0; i<20; i++)
  printf("empty[%d] = %d\n", i, empty[i]);
```

```bash
empty[0] = 8
empty[1] = -113
empty[2] = 18
empty[3] = 103
empty[4] = -1
empty[5] = 127
empty[6] = 0
empty[7] = 0
empty[8] = 48
empty[9] = 23
empty[10] = -71
empty[11] = 89
empty[12] = 58
empty[13] = 0
empty[14] = 0
empty[15] = 0
empty[16] = 0
empty[17] = -128
empty[18] = 0
empty[19] = 0
```

### For Loops
`for` loops can have multiple ''initialization statements'' (is this the correct
term?) but not multiple termination conditions.

This works as expected:

```C
for(i=0, j=0; i < length; i++)
```

Here, the left-hand termination condition is ignroed:
```C
for(i=0; i<10, i<3; i++)
    printf("i = %d\n", i);
```
prints
```bash
i = 0
i = 1
i = 2
```
