# Dukpy

[![Build Status](https://travis-ci.org/akheron/dukpy.svg?branch=master)](https://travis-ci.org/akheron/dukpy) [![Coverage Status](https://coveralls.io/repos/akheron/dukpy/badge.svg?branch=master)](https://coveralls.io/r/akheron/dukpy?branch=master)

Dukpy is a JavaScript runtime environment for Python using the
[duktape](http://duktape.org/) embeddable JavaScript engine. With
dukpy, you can run JavaScript in Python.

Example:

    import dukpy

    ctx = dukpy.Context()
    ctx.eval('str = "Hello, World!";');

    print(ctx.g.str)
    # ==> Hello, World!

    def add(x, y):
        return x + y

    ctx.g.add = add
    ctx.eval('result = add(10, 32);')

    print(ctx.g.result)
    # ==> 42
