Разметка страницы
=================

Описание CSS-классов для разметки страницы


col-SW-N
--------

Колонки

* SW - xs, sm, md, lg
* N - 1...12

.. code-block:: html

    <div class="col-xs-1"></div>


col-SW--pull-*
--------------

Смещение влево

* SW - xs, sm, md, lg

.. code-block:: html

    <div class="col-xs-pull-"></div>


col-SW--push-*
--------------

Смещение вправо

* SW - xs, sm, md, lg

.. code-block:: html

    <div class="col-xs-push-"></div>


container
---------

Фиксированный контйнер (940 px).

.. code-block:: html

    <div class="container"></div>


container-fluid
---------------

Резиновый контейнер.

.. code-block:: html

    <div class="container-fluid"></div>


row
---

Строка

.. code-block:: html

    <div class="container">
        <div class="row"></div>
    </div>


row-fluid
---------

Резиновый контейнер для колонок

::

    <div class="container-fluid">
        <div class="row-fluid"></div>
    </div>


spanX
-----

Контейнер для строк, где `Х` - число от 1-12, ширина строки.

::

    <div class="container">
        <div class="row">
            <div class="span3">Это колонка шириной 3</div>
            <div class="span9">Это колонка шириной 9</div>
        </div>
    </div>

well
----

Выделенный контейнер.

::

    <div class="container">
        <div class="row">
            <div class="span3">
                <p class="well">Это колонка шириной 3</p>
            </div>
            <div class="span9">
                <p class="well">Это колонка шириной 9</p>
            </div>
        </div>
    </div>


pull-right
----------

Выравнивает контейр по правому краю

::

    <blockquote class="pull-right">
        <p>message</p>
        <small>by ilnurgi</small>
    </blockquote>


hide
----

Скрывает элемент

::

    <table class="table hide">
    </table>