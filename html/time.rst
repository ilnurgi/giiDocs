.. title:: html time

.. meta::
    :description: html time
    :keywords: html time

time
====

* Разметка времени и даты

* Элемент, позволяющий однозначно кодировать дату и время и отображать их на экране в привычном для нас виде.

    Содержит либо время по 24-часовой шкале, либо точную дату по григорианскому календарю с возможным указанием времени и смещения часового пояса.

* нельзя указать дату до Рождества Христова.

* нельзя использовать неполные даты

.. code-block:: html

    <time datetime=YYYY-MM-DD>
    <time datetime=2012-11-13T20:00>11 ноября 2012, 8 вечера</time>

    <!-- время с секундами и миллисекундами в часовом поясе UTC+4 -->
    <time datetime=2012-11-13T20:00:00.001+04:00>