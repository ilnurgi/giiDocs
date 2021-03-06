.. py:module:: gc

gc - интерфейс управления сборщиком мусора
==========================================

.. py:attribute:: garbage

    Переменная, содержащая доступный только для чтения список экземпляров пользовательских классов, которые больше не используются, но которые не могут быть удалены, потому что они связаны циклическими ссылками и имеют метод __del__(). Такие объекты не могут быть удалены сборщиком мусора, так как, чтобы разорвать циклическую связь, интерпретатор должен сначала произвольно удалить один из объектов. При этом не существует надежного способа определить, должен ли метод __del__() остающегося объекта, вовлеченного в циклическую ссылку, выполнить какие-то важные операции над объектом, который только что был удален.

.. py:method:: collect([generation])
    
    :param generation: 0-2, номер поколения
    
    Запускает полную сборку мусора

.. py:method:: disable()

    Отключает механизм сборки мусора.

.. py:method:: enable()

    Включает механизм сборки мусора.

.. py:method:: get_count()

    Возвращает кортеж (count0, count1, count2) с текущим количеством объектов в каждом поколении

.. py:method:: get_debug()

    Возвращает текущие состояния флагов отладки.

.. py:method:: get_objects()

    Возвращает список всех объектов, находящихся под контролем сборщика мусора. За исключением возвращаемого списка.

.. py:method:: get_referrers(obj1, obj2, ...)

    Возвращает список всех объектов, которые непосредственно ссылаются на объекты obj1, obj2 и так далее. Возвращаемый список может содержать объекты, которые еще не были утилизированы сборщиком мусора, а также объекты, находящиеся в стадии создания.

.. py:method:: get_referents(obj1, obj2, ...)

    Возвращает список объектов, на которые ссылаются объекты obj1, obj2 и так далее. Например, если obj1 является контейнером, для него будет возвращен список объектов, содержащихся в нем.

.. py:method:: get_threshold()

    Возвращает кортеж с текущими пороговыми значениями запуска сборщика мусора.

.. py:method:: isenabled()

    Возвращает True, если механизм сборки мусора включен.

.. py:method:: set_debug(flags)

    Устанавливает отладочные флаги сборщика мусора, которые могут использоваться для отладки поведения сборщика мусора. В аргументе flags передается целое число, составленное с помощью битовой операции ИЛИ из констант DEBUG_STATS, DEBUG_COLLECTABLE, DEBUG_UNCOLLECTABLE, DEBUG_INSTANCES, DEBUG_OBJECTS, DEBUG_SAVEALL и DEBUG_LEAK. Флаг DEBUG_LEAK является, пожалуй, наиболее полезным, потому что он вынуждает механизм сборщика мусора выводить информацию, которая может пригодиться при отладке программ с утечками памяти.

.. py:method:: set_threshold(threshold0 [, threshold1[, threshold2]])

    Устанавливает частоту запуска сборщика мусора. Объекты распределяются по трем поколениям, где поколение 0 содержит самые молодые объекты, а поколение 2 – самые старые. Объекты, пережившие этап сборки мусора, перемещаются в следующее, более старшее поколение. Достигнув поколения 2, объект остается в нем. В аргументе threshold0 передается число, разность между количеством операций создания новых объектов и количеством операций удаления объектов, по достижении которого запускается сборка мусора среди объектов поколения 0. В аргументе threshold1 передается число, определяющее количество запусков процедуры сборки мусора среди объектов поколения 0, по достижении которого запускается сборка мусора среди объектов поколения 1. В аргументе threshold2 передается число, определяющее количество запусков процедуры сборки мусора среди объектов поколения 1, по достижении которого запускается сборка мусора среди объектов поколения 2. По умолчанию используются пороговые значения (700,10,10). Если в аргументе threshold0 передать значение 0, сборка мусора будет отключена.