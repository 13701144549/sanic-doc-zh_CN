Sanic
=====

|Join the chat at https://gitter.im/sanic-python/Lobby| |Build Status| |PyPI| |PyPI version|

Sanic是一个适用于Python3.5+，类似于Flask般简洁的web服务器，有着更快的速度。她基于magicstack那帮神奇的伙计们完成的工作,受启发于 `这篇文章 <https://magic.io/blog/uvloop-blazing-fast-python-networking/>`_。

在类似于Flask那般简洁的基础之上, Sanic支持async异步请求处理。  这意味着你可以使用从Python3.5开始的新async/await语法来构建更快的非阻塞代码。

Sanic在 `GitHub <https://github.com/channelcat/sanic/>`_上开发，欢迎参与贡献!

如果你的一个项目中用到了Sanic请确保提交 `issue <https://github.com/channelcat/sanic/issues/396>`_，以便我们追踪这些项目!

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

使用bash命令可以安装不包括uvloop与json的Sanic, 你可以设置任一或全部的SANIC_NO_X
变量为确定性字符串，例如 `'y', 'yes', 't', 'true', 'on', '1'`，那样就不会安装相应属性的包。

- ``SANIC_NO_UVLOOP=true SANIC_NO_UJSON=true pip install sanic``


文档
-------------

`在readthedocs网站上阅读中文文档 <http://sanic-doc-zh-cn.readthedocs.io>`_.
`在readthedocs网站上阅读英文文档 <http://sanic.readthedocs.io>`_.

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
`非典型性扩展例子 <https://github.com/channelcat/sanic/wiki/Examples/>`_. 超出Sanic范畴的示例与扩展.

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
