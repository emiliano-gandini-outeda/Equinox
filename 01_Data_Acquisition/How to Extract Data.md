---
tags:
  - data-acquisition
  - zipfile
  - python
  - how-to
created: 2026-04-16
---

### .zip files
To extract data from .zip files, we use the `io` and `zipfile` libraries.

```python
import zipfile
import io

## Lets assume the zipfile is stored in the variable my_zip

z = zipfile.ZipFile(io.BytesIO(my_zip))
z.extractall()
```


