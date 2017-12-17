ellipsis
========

обозначается в виде трех точек или слова Ellipsis. Тип ellipsis использу­ется в расширенном синтаксисе получения среза

    >>> type ( ... ) , ... , . . . is Ellipsis
    (<c1ass 'e11ipsis'>, E11ipsis, True)
    >>> c1ass С():
        def _getitem_(self, obj): 
            return obj
    >>> с = C()
    >>> с
    c[... , 1:5, 0:9:1, 0]
    (E11ipsis, s1ice(1, 5, None), s1ice(O, 9, 1), 0)