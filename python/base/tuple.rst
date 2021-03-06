.. title:: python tuple

.. meta::
    :description: 
        Справочная информация по python, tuple.
    :keywords: 
        python tuple

tuple
=====

.. py:class:: tuple(iter_obj)

    Кортеж

    Кортежи часто используются для представления простых структур данных

    Типичный недостаток кортежей состоит в том,
    что к отдельным элементам приходится обращаться с помощью числовых индексов

    Существует разновидность именного кортежа :py:func:`collections.namedtuple`
    
    .. code-block:: py
        
        (1, 2, 3)
        
        (1, 2, 3) + (4, 5)
        # (1, 2, 3, 4, 5, 6)

        tuple('qwe')
        # ('q', 'w', 'e')


    .. py:method:: count(obj)

        Возвращает :py:class:`int`, количество указанных элементов в последовательности


    .. py:method::  index(obj [, start_pos [ , end_pos]])

        Возвращает :py:class:`int`, индекс указанного элемента


.. code-block:: py

    # пустой кортеж, синглтон
    a = ()
    b = ()
    a is b
    # True

    # кортежи не копируются
    a = (1, 2)
    b = tuple(a)
    a is b
    # True
