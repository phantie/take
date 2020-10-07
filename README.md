# one-line_methods
Run methods in one line even if they do not return 'self'.

Say, we have:

    a = {1: 'x', 2: 'y'}
    b = {2: 'z', 3: 'y'}


You can't do this to merge them because 'update' returns None and not self:

    c = a.copy().update(b)
    # c = None

Using 'take':

    c = take(a.copy()).update(b).update({42: 'k'}).unwrap()

    # c = {1: 'x', 2: 'z', 3: 'y', 42: 'k'}
    # a = {1: 'x', 2: 'y'}
    # b = {2: 'z', 3: 'y'}

Dicts are taken for the purpose of example.
There are obviously better ways to merge dicts.
