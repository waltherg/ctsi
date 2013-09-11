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
