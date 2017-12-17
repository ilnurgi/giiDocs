.. py:module:: xlwt

xlwt - интсурмент для создания xls файлов
=========================================

`Страничка проекта`_

`Скачать`_

`Официальная документация`_

`Примеры`_

`GitHub`_

.. _Страничка проекта: http://www.python-excel.org/
.. _Скачать: http://pypi.python.org/pypi/xlwt
.. _Официальная документация: https://secure.simplistix.co.uk/svn/xlwt/trunk/xlwt/doc/xlwt.html?p=4966
.. _Примеры: https://github.com/python-excel/xlwt/tree/master/xlwt/examples
.. _GitHub: https://github.com/python-excel/xlwt

Модуль для создания Excel документов


Функции модуля
------------------------------

.. py:method:: easyxf (strg_to_parse)
    
    Данная функция используется для создания и настройки XFStyle объекта для использования (например) :py:meth:`xlwt.Worksheet.write` методом, возвращает XFstyle.

    :param strg_to_parse:    
        
        A string to be parsed to obtain attribute values for Alignment, Borders, Font, Pattern and Protection objects. Refer to the examples in the file .../examples/xlwt_easyxf_simple_demo.py and to the xf_dict dictionary in Style.py. Various synonyms including color/colour, center/centre and gray/grey are allowed. Case is irrelevant (except maybe in font names). '-' may be used instead of '_'.
        Example: "font: bold on; align: wrap on, vert centre, horiz center"

        .. code-block:: py
            
            _style = xlwt.easyxf(
                'pattern: pattern solid, fore_colour black;'
                'font: colour white, bold True;')

            bold = 'font: bold 1'
            italic = 'font: italic 1'

            # Wrap text in the cell
            wrap_bold = 'font: bold 1; align: wrap 1;'

            # White text on a blue background
            reversed = 'pattern: pattern solid, fore_color blue; font: color white;'

            # Light orange checkered background
            light_orange_bg = 'pattern: pattern fine_dots, fore_color white, back_color orange;'

            # Heavy borders
            bordered = 'border: top thick, right thick, bottom thick, left thick;'

            # 16 pt red text
            big_red = 'font: height 320, color red;'

    :param num_format_str:
    
        To get the "number format string" of an existing cell whose format you want to reproduce, select the cell and click on Format/Cells/Number/Custom. Otherwise, refer to Excel help.
        Examples: "#,##0.00", "dd/mm/yyyy"

Workbook
--------

.. py:class:: Workbook(encoding='ascii',style_compression=0)
    
    Объект "Книга"

    .. py:method:: add_sheet(sheetname)
        
        Добалвяет лист в книгу, возвращает объект лист :py:class:`xlwt.Worksheet`

        :param sheetname:

    .. py:method:: save(filename_or_stream)
        
        Сохраняет книгу

        :param filename_or_stream: путь к файлу или потоку вывода в который можно писать

Worksheet
---------

.. py:class:: Worksheet
    
    Объект "Лист". Данный объект нельзя создать самому, он получается в методе :py:meth:`xlwt.Workbook.add_sheet`

    .. py:method:: write(r, c, label="", style=Style.default_style)
    
        Записывает ячейку в лист

        :param int r: строка листа
        :param int c: колонка листа
        :param str label: значение ячейки (The data value to be written. An int, long, or decimal.Decimal instance is converted to float. A unicode instance is written as is. A str instance is converted to unicode using the encoding (default: 'ascii') specified when the Workbook instance was created. A datetime.datetime, datetime.date, or datetime.time instance is converted into Excel date format (a float representing the number of days since (typically) 1899-12-31T00:00:00, under the pretence that 1900 was a leap year). A bool instance will show up as TRUE or FALSE in Excel. None causes the cell to be blank -- no data, only formatting. An xlwt.Formula instance causes an Excel formula to be written.)
        :param style: стиль ячейки
        :type style: XF object