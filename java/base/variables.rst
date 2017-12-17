Типы данных
===========

Примитивные типы данных
-----------------------

* `byte` - число, 1 байт
* `short` - число, 2 байта
* `int` - число, 4 байта
* `long` - число, 8 байт
* `double` - число с точкой, 4 байта
* `float` - число с точкой, 8 байт
* `char` - символ, 2 байта
* `boolean` - true/false, 1 байт

::

    int age;
    age = 29;
    age = 0xff;
    age = 0b1010;
    age = 123_345;
    age = 0b0101_1010;

::

    char st;

    // код переменной Х
    st = 88;

    st = 'X'

    // st  = 'Y'
    st++;

(void)
------

Бесконечность (Infinity)
------------------------

::

    double d = 1.0 / 0
    // Infinity

Не число (Nan)
--------------

::

    0 / 0
    // NaN

Массивы (array)
---------------

::
   
    int month_days[];
    month_days = new int[12];
    month_days[0] = 31;
    ...
    month_days[11 ] = 31;

    int month_days[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    int ar1[][] = new int[2][2];

    int ar2[][] = {
        {0, 1},
        {2, 3}
    }

    int ar3[][];
    ar3 = new int{
        {0, 1},
        {2, 3}
    }

    int[] a = {1, 2, 3};
    a.length;
    // 3
 
Преобразования
--------------

Правила повышения типа

1. тип всех значений byte, short и char повышается до int
2. если один операнд имеет тип long, тип всего выражения повышается до long. 
3. если один операнд имеет тип float, тип всего выражения повышается до float

::

    class Conversion {
        
        public static void main(String args[]) {
        
            byte b;
            int i = 257;
            double d = 323.142;
            
            System.out.println("Преобразование int в byte.");
            b = (byte) i;
            System.out.println("i и b " + i + " " + b);
            // 257 и 1, остаток от деления 257/256

            System.out.println("Преобразование double в int.");
            i = (int) d;
            System.out.println("d и i " + d + " " + i);
            // 323.142 и 323, дробь отбрасывается

            System.out.println("Преобразование double в byte.");
            b = (byte) d;
            System.out.println("d и b " + d + " " + b );
            // 323.142 и 67, остаток от деления 323/256
        }
    }


::
  
    byte b = 50;
    b = b * 2; 
    // Ошибка! Значение типа int не может быть присвоено переменной типа byte!, ява повышает тип переменных до int
    b = (byte) (b * 2)