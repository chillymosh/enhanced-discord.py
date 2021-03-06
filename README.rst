Enhanced-dpy (custom discord.py)
=================================

.. image:: https://img.shields.io/pypi/pyversions/discord.py.svg
   :target: https://pypi.python.org/pypi/discord.py
   :alt: PyPI supported Python versions

A modern, easy to use, feature-rich, and async ready API wrapper for Discord written in Python.
Credits to the `original lib by Rapptz <https://github.com/Rapptz/discord.py>`_

**WARNING: This is not the official discord.py library! As of 8/27/2021 Danny (Rapptz) has stopped development due to breaking changes. You are still able to read the official library at https://github.com/Rapptz/discord.py!**

Custom Features
----------------

**Moved to:** `Custom Features <https://enhanced-dpy.readthedocs.io/en/latest/custom_features.html>`_

Key Features
-------------

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limit handling.
- 100% coverage of the supported Discord API.
- Optimised in both speed and memory.

Installing
----------

**Python 3.5.3 or higher is required**

To install the library without full voice support, you can just run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U enhanced-dpy

    # Windows
    py -3 -m pip install -U enhanced-dpy

To install the development version, do the following:

.. code:: sh

    $ git clone https://github.com/iDevision/enhanced-discord.py
    $ cd enhanced-discord.py
    $ python3 -m pip install -U .[voice]


Optional Packages
~~~~~~~~~~~~~~~~~~

* PyNaCl (for voice support)

Please note that on Linux installing voice you must install the following packages via your favourite package manager (e.g. ``apt``, ``dnf``, etc) before running the above commands:

* libffi-dev (or ``libffi-devel`` on some systems)
* python-dev (e.g. ``python3.6-dev`` for Python 3.6)

Quick Example
--------------

.. code:: py

    import discord

    class MyClient(discord.Client):
        async def on_ready(self):
            print('Logged on as', self.user)

        async def on_message(self, message):
            # don't respond to ourselves
            if message.author == self.user:
                return

            if message.content == 'ping':
                await message.channel.send('pong')

    client = MyClient()
    client.run('token')

Bot Example
~~~~~~~~~~~~~

.. code:: py

    import discord
    from discord.ext import commands

    bot = commands.Bot(command_prefix='>')

    @bot.command()
    async def ping(ctx):
        await ctx.send('pong')

    bot.run('token')

You can find more examples in the examples directory.

Links
------

- `Documentation <https://enhanced-dpy.readthedocs.io/en/latest/index.html>`_
- `Official Discord Server <https://discord.gg/wZSH7pz>`_
- `Discord API <https://discord.gg/discord-api>`_
