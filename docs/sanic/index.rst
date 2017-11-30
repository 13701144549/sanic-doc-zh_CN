Sanic
=================================

Sanic是一个适用于Python3.5+的类Flask web服务器，有着更快的速度。她基于magicstack那帮神奇的伙计们完成的uvloop,受启发于 `这篇文章 <https://magic.io/blog/uvloop-blazing-fast-python-networking/>`_。

在Flask简洁基础之上, Sanic支持async异步请求处理。  这意味着你可以使用从Python3.5开始的新async/await语法来构建更快的非阻塞代码。

Sanic在`GitHub <https://github.com/channelcat/sanic/>`_上开发，欢迎参与贡献!

Sanic追求简洁
---------------------------

.. code:: python

    from sanic import Sanic
    from sanic.response import json

    app = Sanic()

    @app.route("/")
    async def test(request):
        return json({"hello": "world"})

    if __name__ == "__main__":
        app.run(host="0.0.0.0", port=8000)