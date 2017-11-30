Sanic
=====

|Join the chat at https://gitter.im/sanic-python/Lobby| |Build Status| |PyPI| |PyPI version|

Sanic是一个适用于Python3.5+的类Flask web服务器，有着更快的速度。她基于magicstack那帮神奇的伙计们完成的uvloop,受启发于`这篇文章 <https://magic.io/blog/uvloop-blazing-fast-python-networking/>`_。

在类似于Flask那种简洁基础之上, Sanic支持async异步请求处理。  这意味着你可以使用从Python3.5开始的新async/await语法来构建更快的非阻塞代码。

Sanic在`GitHub <https://github.com/channelcat/sanic/>`_上开发，欢迎参与贡献!

若过你的一个项目中用到了Sanic请确保提交`issue <https://github.com/channelcat/sanic/issues/396>`_ 以便我们追踪这些项目!

Hello World 示例
-------------------

.. code:: python

    from sanic import Sanic
    from sanic.response import json

    app = Sanic()

    @app.route("/")
    async def test(request):
        return json({"hello": "world"})

    if __name__ == "__main__":
        app.run(host="0.0.0.0", port=8000)

安装
------------

-  ``pip install sanic``

To install sanic without uvloop or json using bash, you can provide either or both of these environmental variables
using any truthy string like `'y', 'yes', 't', 'true', 'on', '1'` and setting the NO_X to true will stop that features
installation.

- ``SANIC_NO_UVLOOP=true SANIC_NO_UJSON=true pip install sanic``


文档
-------------

`在readthedocs网站上阅读中文文档 <http://sanic-doc-zh-cn.readthedocs.io>`_.

.. |Join the chat at https://gitter.im/sanic-python/Lobby| image:: https://badges.gitter.im/sanic-python/Lobby.svg
   :target: https://gitter.im/sanic-python/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge
.. |Build Status| image:: https://travis-ci.org/channelcat/sanic.svg?branch=master
   :target: https://travis-ci.org/channelcat/sanic
.. |Documentation| image:: https://readthedocs.org/projects/sanic/badge/?version=latest
   :target: http://sanic.readthedocs.io/en/latest/?badge=latest
.. |PyPI| image:: https://img.shields.io/pypi/v/sanic.svg
   :target: https://pypi.python.org/pypi/sanic/
.. |PyPI version| image:: https://img.shields.io/pypi/pyversions/sanic.svg
   :target: https://pypi.python.org/pypi/sanic/
   

示例
--------
`Non-Core examples <https://github.com/channelcat/sanic/wiki/Examples/>`_. 扩展例子 and Sanic that are outside the scope of Sanic core.

`扩展 <https://github.com/channelcat/sanic/wiki/Extensions/>`_. 社区创建的Sanic扩展。

`项目 <https://github.com/channelcat/sanic/wiki/Projects/>`_. Sanic在实际项目中的应用.


TODO
----
 * http2

不足
-----------
* Windows平台没有uvloop和httptools这样的工具 :(

终极思想
--------------

::

                     ▄▄▄▄▄
            ▀▀▀██████▄▄▄       _______________
          ▄▄▄▄▄  █████████▄  /                 \
         ▀▀▀▀█████▌ ▀▐▄ ▀▐█ |   Gotta go fast!  |
       ▀▀█████▄▄ ▀██████▄██ | _________________/
       ▀▄▄▄▄▄  ▀▀█▄▀█════█▀ |/
            ▀▀▀▄  ▀▀███ ▀       ▄▄
         ▄███▀▀██▄████████▄ ▄▀▀▀▀▀▀█▌
       ██▀▄▄▄██▀▄███▀ ▀▀████      ▄██
    ▄▀▀▀▄██▄▀▀▌████▒▒▒▒▒▒███     ▌▄▄▀
    ▌    ▐▀████▐███▒▒▒▒▒▐██▌
    ▀▄▄▄▄▀   ▀▀████▒▒▒▒▄██▀
              ▀▀█████████▀
            ▄▄██▀██████▀█
          ▄██▀     ▀▀▀  █
         ▄█             ▐▌
     ▄▄▄▄█▌              ▀█▄▄▄▄▀▀▄
    ▌     ▐                ▀▀▄▄▄▀
     ▀▀▄▄▀
