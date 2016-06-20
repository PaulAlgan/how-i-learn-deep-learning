#### Cannot import tensorflow
If you found error like this
```
Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "/usr/local/lib/python2.7/site-packages/tensorflow/__init__.py", line 23, in <module>
    from tensorflow.python import *
  ...
  ...
  ...
TypeError: __init__() got an unexpected keyword argument 'syntax'

```
you can try this
```
pip uninstall protobuf
pip uninstall tensorflow
brew uninstall protobuf
```
[Source](http://stackoverflow.com/questions/33622842/error-in-python-after-import-tensorflow-typeerror-init-got-an-unexpect)
