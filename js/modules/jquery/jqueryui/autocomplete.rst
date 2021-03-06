autocomplete - автозаполнение текстовых полей
=============================================


.. py:function:: autocomplete([methodName, option, value])
.. py:function:: autocomplete([methodName, param_obj])
.. py:function:: autocomplete([param_obj])

    
    * `methodName` - методы виджета

        * `close` - Закрывает раскрывающийся список элементов автозаполнения

        * `destroy` - Полностью удаляет функциональность автозаполнения из элемента input
        
    * `disable` - Приостанавливает работу виджета Autocomplete для базового элемента

    * `enable` - Возобновляет работу ранее приостановленного виджета Autocomplete
    
    * `option` - Устанавливает значения одного или нескольких свойств
    
    * `search` - Запускает процедуру поиска элементов автозаполнения, соответствующих указанному значению. Если аргумент значение не предос­тавлен, используется содержимое элемента input    


    * `param_obj` - объект с параметрами

        * `appendTo` - элемент, к которому должен быть присоединен раскрывающийся список элементов

        * `autoFocus` - автоматическое установление на первом элементе списка

        * `change` - обработчик, когда фокус ввода выходит за пределы текстового поля после изменения содер­жащегося в нем значения

        * `close` - обработчик, при закрытии раскрывающегося списка элементов автозаполнения

        * `create` - обработчик, при инициализации экземпляра виджета Autocomplete для данного элемента

        * `delay` - длительность периода задержки после нажатия клавиши, по истечении которого будет срабатывать автозаполнение. По умолчанию 300

        * `disabled` - отключение элемента

        * `focus` - обработчик, когда элемент автозаполнения получает фокус в раскрывающемся списке

        * `minLength` - минимальное число символов, после которого появится список для автозаполнения. По умолчанию 1

        * `open` обработчик, при открытии раскрывающегося списка элементов автозаполнения

        * `search` - обработчик, перед генерацией раскрывающегося списка элементов автозаполнения или пе­ред поиском в нем подходящих элементов

        * `select` - обработчик, при выборе элемента списка автозаполнения

        * `source` - данные, массив строк, массив объектов, урл получения данных

            .. code-block:: js

                $('acInput').autocomplete({
                    source: ['Розы', 'Фиалки']
                })

            .. code-block:: js

                $('acInput').autocomplete({
                    source: [
                        {
                            label: 'Розы (розовые)', 
                            value: 'Розы'
                        }, {
                            label: 'Розы (розовые)2', 
                            value: 'Розы2'
                        }
                    ]
                })
            
            