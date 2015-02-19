.. Flask-DebugToolbar documentation master file, created by
   sphinx-quickstart on Wed Feb 15 18:08:39 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Flask-DebugToolbar
==================

这是移植了完美的 `django-debug-toolbar <https://github.com/django-debug-toolbar/django-debug-toolbar>`_ ，是 Flask 的一个扩展。

安装
------------

简单地使用 pip 安装::

    $ pip install flask-debugtoolbar


用法
-----

建立调试工具栏是简单的::

    from flask import Flask
    from flask_debugtoolbar import DebugToolbarExtension

    app = Flask(__name__)

    # the toolbar is only enabled in debug mode:
    app.debug = True

    # set a 'SECRET_KEY' to enable the Flask session cookies
    app.config['SECRET_KEY'] = '<replace with a secret key>'

    toolbar = DebugToolbarExtension(app)


当调试模式开启的时候，工具栏会自动地给添加到 Jinja 模板中。在生产环境中，设置 ``app.debug = False`` 将会禁用工具栏。


配置
-------------

工具栏支持多个配置选项:

====================================  =====================================   ==========================
名称                                   描述                                    默认值
====================================  =====================================   ==========================
``DEBUG_TB_ENABLED``                  启用工具栏？                              ``app.debug``
``DEBUG_TB_HOSTS``                    显示工具栏的 hosts 白名单                  任意 host
``DEBUG_TB_INTERCEPT_REDIRECTS``      要拦截重定向？                             ``True``
``DEBUG_TB_PANELS``                   面板的模板/类名的清单                       允许所有内置的面板
``DEBUG_TB_PROFILER_ENABLED``         启用所有请求的分析工具                      ``False``，用户自行开启
``DEBUG_TB_TEMPLATE_EDITOR_ENABLED``  启用模板编辑器                             ``False``
====================================  =====================================   ==========================

要更改配置选项之一，在 Flask 应用程序配置中像这样设置它::

    app.config['DEBUG_TB_INTERCEPT_REDIRECTS'] = False


贡献
------------

Fork 我们 `在 GitHub 上 <https://github.com/mgood/flask-debugtoolbar>`_


索引和表格
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

