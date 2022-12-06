# devspace-double-flag
A reproduction for double flag value issue

Run:
```
devspace deploy
```

Actual output:
```
local local
false
```

Expected output:
```
local
false
```

Run with 2 profiles:
```
devspace deploy --profile local --profile test
```

Actual:
```
local test local test
false
```


Expected:
```
local test
false
```

Caused by
```
vars:
  DEVSPACE_FLAGS: --namespace double-flag
```

If the `DEVSPACE_FLAGS` is removed the outputs change to expected one.
