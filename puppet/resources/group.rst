group - управление группами пользователей
=========================================

* `ensure` - состояние

    * `absent` - не должен существовать
    
    * `present` - должен существовать


.. code-block:: puppet

    group {
        'web':
            ensure => present
    }