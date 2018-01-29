JavaScript
==========

JavaScript - язык программирования сценариев (script)
со слабой типизацией и динамическим приведением
типов.

Интерпретируемый язык.

Для выполнения, программа не переводится в машинный код,
а выполняется по мере прочтения интерпретатором.


.. code-block:: html

    <script type="text/javascript">
        alert("Hello World!");
    </script>

.. code-block:: html

    <script type="text/javascript" src="app.js"></script>

    <script src="app.js"></script>

    <!-- асинхронное подключение -->
    <script src="app.js" async></script>
    <script src="app.js" defer></script>


.. toctree::
    :maxdepth: 2

    base/index
    dom/index
    bom/index
    frameworks/index
   