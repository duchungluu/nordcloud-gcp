****************
Notejam: Express
****************

Notejam application implemented using `Express.js <http://expressjs.com/>`_ microframework.

Express version: 4.2

Middlewares/extentions used:

* `Passport.js <http://passportjs.org/>`_ for authentication
* `Node ORM 2 <https://github.com/dresende/node-orm2>`_ for database
* `Mocha <http://mochajs.org/>`_ and `Superagent <http://visionmedia.github.io/superagent/>`_ for testing
* ... and `others <https://github.com/komarserjio/notejam/blob/express/express/notejam/package.json>`_

==========================
Installation and launching
==========================

-------
Cloning
-------

Clone the repo:

.. code-block:: bash

    $ git clone git@github.com:komarserjio/notejam.git YOUR_PROJECT_DIR/

-------------------
Install environment
-------------------
Use `npm <https://www.npmjs.org/>`_ to manage dependencies.

Install dependencies

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ npm install

Create database schema

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ node db.js

------
Launch
------

Start built-in web server:

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ DEBUG=* ./bin/www

Go to http://127.0.0.1:3000/ in your browser

------------------
Running unit tests
------------------

Run unit tests:

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ ./node_modules/mocha/bin/mocha tests

============
Contribution
============

Please send your pull requests in the ``master`` branch.

Always prepend your commits with a framework name:

.. code-block:: bash

    Express: Implemented sign in functionality

*******
Notejam
*******

**The easy way to learn web frameworks**

Do you know framework X and want to try framework Y?
The easy way to start with a new framework is to compare it with frameworks you already know.
The goal of the project is to help developers easily learn new frameworks by examples.

Notejam is a unified sample web application (more than just "Hello World") implemented using different server-side frameworks.
Currently python, php, ruby and javascript frameworks are supported.


====================
Supported frameworks
====================

**Python**


* `Django <https://github.com/komarserjio/notejam/tree/master/django>`_
* `Flask <https://github.com/komarserjio/notejam/tree/master/flask>`_
* `Pyramid <https://github.com/komarserjio/notejam/tree/master/pyramid>`_

**PHP**

* `Laravel <https://github.com/komarserjio/notejam/tree/master/laravel>`_
* `Yii <https://github.com/komarserjio/notejam/tree/master/yii>`_
* `CakePHP <https://github.com/komarserjio/notejam/tree/master/cakephp>`_
* `Nette <https://github.com/komarserjio/notejam/tree/master/nette/native_db>`_ / `Nette + Doctrine <https://github.com/komarserjio/notejam/tree/master/nette/doctrine>`_
* `Symfony <https://github.com/komarserjio/notejam/tree/master/symfony>`_

**Ruby**

* `Padrino <https://github.com/komarserjio/notejam/tree/master/padrino>`_
* `Ruby on Rails <https://github.com/komarserjio/notejam/tree/master/rubyonrails>`_

**Java**

* `Spring <https://github.com/komarserjio/notejam/tree/master/spring>`_

**Javascript (node.js)**

* `Express <https://github.com/komarserjio/notejam/tree/master/express>`_


In progress
-----------

**Scala**

* Play

**Clojure**

* Compojure

... and more frameworks are coming soon.

====================
Application overview
====================

Notejam is a web application which offers user to sign up/in/out and create/view/edit/delete notes.
Notes are grouped in pads.

**Screenshots**

.. image:: https://github.com/komarserjio/notejam/blob/master/html/screenshots/1p.png
    :alt: Sign in
    :width: 400
    :align: center
    :target: https://github.com/komarserjio/notejam/tree/master/screenshots.rst

.. image:: https://github.com/komarserjio/notejam/blob/master/html/screenshots/2p.png
    :alt: All notes
    :width: 400
    :align: center
    :target: https://github.com/komarserjio/notejam/tree/master/screenshots.rst

.. image:: https://github.com/komarserjio/notejam/blob/master/html/screenshots/3p.png
    :alt: New note
    :width: 400
    :align: center
    :target: https://github.com/komarserjio/notejam/tree/master/screenshots.rst

See `more screenshots <https://github.com/komarserjio/notejam/tree/master/screenshots.rst>`_
for look and feel.

See `detailed overview <https://github.com/komarserjio/notejam/blob/master/contribute.rst#application-requirements>`_.

Typical application covers following topics:

* Request/Response handling
* Routing
* Templates
* Configuration
* Authentication
* Forms
* Error handling
* Database/ORM
* Mailing
* Functional/unit testing

=============
How to launch
=============

All implementations are SQLite based and quickly launchable by built-in web servers.
Each implementation has instruction describing easy steps to install environment, launch and run tests.

============
Contribution
============

Contribution is more than welcome!
Contribute improvements to existing applications to help them follow best practices
or provide new implementation for unsupported framework.


**Do you want to improve one of the existing implementations?**

Each implementation has its own README with contribution details.

**Do you want to add new framework?**

Read `contribution guide <https://github.com/komarserjio/notejam/blob/master/contribute.rst>`_ for details.

========
Contacts
========

* Twitter: `@komarserjio <https://twitter.com/komarserjio>`_
* Email: komarserjio <at> gmail.com

=======
License
=======

MIT © Serhii Komar.

See `license <https://github.com/komarserjio/notejam/blob/master/license.rst>`_.
