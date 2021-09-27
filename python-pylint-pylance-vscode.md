# Python

## pylint

include local modules paths for pylint

<https://stackoverflow.com/questions/1899436/pylint-unable-to-import-error-how-to-set-pythonpath/3065082#3065082>

```shell
$ touch .pylint.rc
```

```python
[MASTER]
init-hook="from pylint.config import find_pylintrc; import os, sys; sys.path.append(os.path.dirname(find_pylintrc()))"
```
