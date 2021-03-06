mcrio-stdlib
============

mcr.io standard library with optional monkey-patching.


Installation
------------

    npm install mcrio-stdlib


Optional monkey-patching
------------------------

Without monkey-patching, you use the form `stdlib.fn(obj, args...)`:

    var stdlib = require('mcrio-stdlib');
    stdlib.endsWith('file.md', '.md') === true;

With monkey-patching, you use the form `obj.fn(args...)`:

    require('mcrio-stdlib').monkey();
    'file.md'.endsWith('.md') === true;

Individual methods can be "monkey-ed" by calling `stdlib.fn.monkey()`:

    var stdlib = require('mcrio-stdlib');
    stdlib.endsWith('foo bar', 'bar') === true;
    stdlib.startsWith.monkey();
    'foo bar'.startsWith('foo') === true;


All provided methods
--------------------

### String.prototype.endsWith(other)

### String.prototype.startsWith(other)

### String.prototype.replacePrefix(oldPrefix, newPrefix)

### String.prototype.replaceSuffix(oldSuffix, newSuffix)

### String.prototype.splitOnce(separator)

### Array.prototype.withoutOne(element)


License
-------

The MIT License (MIT)

Copyright (c) 2014 Felix Rabe

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
