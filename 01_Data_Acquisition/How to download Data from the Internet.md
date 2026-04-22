---
tags:
  - data-acquisition
  - requests
  - python
  - how-to
created: 2026-04-16
---

To get the data, we use the `requests` library.

```python
import requests

# First, we set a URL
url = 'https://github.com/Hernan4444/MyAnimeList-Database/archive/refs/heads/master.zip'

# Then we get the data
r = requests.get(url, stream=True)
```

`stream=True` allows for big files to be broken down in smaller chunks, but the stream needs to be closed. You can either close it manually or use a [[04_Python/Concepts/Context Managers]].

```python
# To close manually
r.close()

# Using a context manager

with requests.get(url, stream=True) as r:
	# Your code...
	
# This closes the stream automatically when the job ends.
```

