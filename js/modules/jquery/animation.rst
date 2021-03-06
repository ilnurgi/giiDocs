Методы анимации
===============

Ме­то­ды вос­про­из­во­дят ви­зу­аль­ные и не­стан­дарт­ные ани­ма­ци­он­ные эф­фек­ты.

Боль­шин­ст­во из них воз­вра­ща­ют тот же объ­ект jQuery, от­но­си­тель­но
ко­то­ро­го они вы­зы­ва­лись. 


.. py:attribute:: jQuery.fx.off
    
    Ус­та­но­ви­те это свой­ст­во в зна­че­ние true,
    что­бы за­пре­тить все ви­зу­аль­ные и ани­ма ци­он­ные эф­фек­ты.


.. py:module:: jQuery()

.. py:method:: animate(props, opts)
    
    Вос­про­из­во­дит эф­фект, ма­ни­пу­ли­руя CSS-свой­ст­ва­ми,
    оп­ре­де­ляе­мы­ми объ­ек­том props, в ка­ж­дом вы­бран­ном эле­мен­те,
    ис­поль­зуя па­ра­мет­ры, оп­ре­де­ляе­мые объ­ек­том opts.


.. py:method:: animate(props [, duration [, easing [, f()]]])
    
    Вос­про­из­во­дит эф­фект, ма­ни­пу­ли­руя CSS-свой­ст­ва­ми,
    оп­ре­де­ляе­мы­ми объ­ек­том props, в  ка­ж­дом вы­бран­ном эле­мен­те,
    ис­поль­зуя ука­зан­ную про­дол­жи­тель­ность duration и функ­цию пе­ре­хо­да easing.

    По за­вер­ше­нии вы­зы­ва­ет f как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.

    * `props`

        * `backgroundColor` - Устанавливает цвет фона элемента

        * `borderTopColor` - Устанавливает цвет отдельных границ элемента
        
        * `borderBottomCo1or`
        
        * `borderLeftColor`
        
        * `borderRightColor`
        
        * `color` - Устанавливает цвет текста для элемента
        
        * `outlineColor` - Устанавливает цвет обводки;
          используется для визуального выделения элемента


.. py:method:: clearQueue([qname="fx"])
    
    Очи­ща­ет оче­редь эф­фек­тов по умол­ча­нию или
    ука­зан­ную оче­редь для ка­ж­до­го вы­бран­но­го эле­мен­та.

 
.. py:method:: delay(duration, [qname="fx"])
    
    До­бав­ля­ет за­держ­ку с ука­зан­ной про­дол­жи­тель­но­стью duration
    в оче­редь эф­фек­тов по умол­ча­нию или в ука­зан­ную оче­редь.


.. py:method:: dequeue([qname="fx"])
    
    Уда­ля­ет и вы­зы­ва­ет сле­дую­щую функ­цию из оче­ре­ди эф­фек­тов по умол­ча­нию или
    из ука­зан­ной оче­ре­ди.

    Обыч­но нет не­об­хо­ди­мо­сти вруч­ную уда­лять функ­ции из оче­ре­ди эф­фек­тов.


.. py:method:: fadeIn([duration=400],[f()])
.. py:method:: fadeOut([duration=400],[f()])
    
    Вос­про­из­во­дит в те­че­ние duration мил­ли­се­кунд эф­фект про­яв­ле­ния или
    рас­тво­ре­ния эле­мен­та, ма­ни­пу­ли­руя его про­зрач­но­стью.

    По за­вер­ше­нии вы­зы­ва­ет функ­цию f, ес­ли ука­за­на,
    как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.


.. py:method:: fadeTo(duration, opacity, [f()])
    
    Из­ме­ня­ет CSS-свой­ст­во opacity в вы­бран­ных эле­мен­тах до зна­че­ния opacity
    в те­че­ние ука­зан­ной про­дол­жи­тель­но­сти duration.

    По за­вер­ше­нии вы­зы­ва­ет функ­цию f, ес­ли ука­за­на,
    как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.


.. py:method:: hide()
.. py:method:: hide(duration, [f()])
    
    При вы­зо­ве без ар­гу­мен­тов не­мед­лен­но скры­ва­ет вы­бран­ные эле­мен­ты.

    Ина­че вос­про­из­во­дит эф­фект, умень­шая раз­ме­ры и
    не­про­зрач­ность всех вы­бран­ных эле­мен­тов так,
    что они пол­но­стью ис­че­за­ют че­рез duration мил­ли­се­кунд.

    По за­вер­ше­нии вы­зы­ва­ет функ­цию f, ес­ли ука­за­на,
    как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.



.. py:method:: queue(<имя>)
.. py:method:: queue(<имя>[, функция])

    Возврашает указанную очередь функции,
    которые должны быть выполнены для элементов,
    содержащихся в объекте или добавляет указанную функцию ув конец очереди


.. py:method:: slideDown([duration=400],[f()])
.. py:method:: slideUp([duration=400],[f()])
.. py:method:: slideToggle([duration=400],[f()])
    
    Ото­бра­жа­ет, скры­ва­ет или
    пе­ре­клю­ча­ет со­стоя­ние ви­ди­мо­сти ка­ж­до­го вы­бран­но­го эле­мен­та,
    из­ме­няя вы­со­ту в те­че­ние ука­зан­ной про­дол­жи­тель­но­сти duration.

    По за­вер­ше­нии вы­зы­ва­ет функ­цию f, ес­ли ука­за­на,
    как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.

    .. code-block:: js

        jq_elem.slideToggle(2000);


.. py:method:: show()
.. py:method:: show(duration, [f()])
    
    При вы­зо­ве без ар­гу­мен­тов не­мед­лен­но ото­бра­жа­ет вы­бран­ные эле­мен­ты.
    Ина­че вос­про­из­во­дит эф­фект, уве­ли­чи­вая раз­ме­ры и
    не­про­зрач­ность всех вы­бран­ных эле­мен­тов так,
    что они ста­но­вят­ся пол­но­стью ви­ди­мы­ми че­рез duration мил­ли­се­кунд.

    По за­вер­ше­нии вы­зы­ва­ет функ­цию f, ес­ли ука­за­на,
    как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.


.. py:method:: stop([clear=false], [jump=false])
    
    Ос­та­нав­ли­ва­ет вос­про­из­ве­де­ние те­ку­ще­го ани­ма­ци­он­но­го эф­фек­та
    (ес­ли та­ко­вой име­ет­ся) во всех вы­бран­ных эле­мен­тах.

    Ес­ли ар­гу­мент clear име­ет зна­че­ние true,
    так­же очи­ща­ет оче­редь эф­фек­тов для ка­ж­до­го эле­мен­та.

    Ес­ли ар­гу­мент jump име­ет зна­че­ние true,
    пе­ред ос­та­нов­кой при­сваи­ва­ет эле­мен­там ко­неч­ные зна­че­ния,
    ко­то­рые долж­ны быть дос­тиг­ну­ты в хо­де вос­про­из­ве­де­ния эф­фек­та.


.. py:method:: switchClass(class1, class2, speed)

    Удаляет один класс и добавляет новый с определенной скоростью

    
.. py:method:: toggle([show])
.. py:method:: toggle(duration, [f()])
    
    Ес­ли ар­гу­мент show име­ет зна­че­ние true,
    вы­зы­ва­ет ме­тод show() для не­мед­лен­но­го ото­бра­же­ния вы­бран­ных эле­мен­тов.

    Ес­ли ар­гу­мент show име­ет зна­че­ние false,
    вызы­ва­ет ме­тод hide() для не­мед­лен­но­го скры­тия вы­бран­ных эле­мен­тов.

    Ес­ли ар­гу­мент show опу­щен, пе­ре­клю­ча­ет со­стоя­ние ви­ди­мо­сти эле­мен­тов.

    Ес­ли ука­зан ар­гу­мент duration,
    пе­ре­клю­ча­ет со­стоя­ние ви­ди­мо­сти вы­бран­ных эле­мен­тов,
    ма­ни­пу­ли­руя раз­ме­ром и про­зрач­но­стью в те­че­ние duration мил­ли­се­кунд.

    По за­вер­ше­нии вы­зы­ва­ет функ­цию f, ес­ли ука­за­на,
    как ме­тод для ка­ж­до­го вы­бран­но­го эле­мен­та.

    .. code-block:: js

        jq_elem.toggle(function(){
            //
        }, function(){
            //
        });


.. py:method:: queue([qname="fx"])
.. py:method:: queue([qname="fx"], f(next))
.. py:method:: queue([qname="fx"], newq)
    
    При вы­зо­ве без ар­гу­мен­тов или толь­ко с име­нем оче­ре­ди
    воз­вра­ща­ет ука­зан­ную оче­редь для пер­во­го вы­бран­но­го эле­мен­та.

    При вы­зо­ве с ар­гу­мен­том-функ­ци­ей до­бав­ля­ет f в ука­зан­ную оче­редь
    для всех вы­бран­ных эле­мен­тов.

    При вы­зо­ве с ар­гу­мен­том-мас­си­вом за­ме­ща­ет ука­зан­ную оче­редь
    для всех вы­бран­ных эле­мен­тов мас­си­вом функ­ций newq.