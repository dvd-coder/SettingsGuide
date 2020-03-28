Компенсация перекрытия стен
====
При печати тонких деталей, противоположенные стены могут перекрывать друг друга из-за слишком близкого расстояния друг к другу. Если печать стен будет идти с нормальной шириной линий, то получится переэкструзия. Включенный параметр предотвращает избыточное выдавливания материала, уменьшая ширину одной из линий.  При таком подходе улучшается точность размера деталей.

![Демонстрация того, как стенки перекрывают друг друга из за неподходящей ширины экструзии](../../../articles/images/travel_compensate_overlapping_walls_enabled_schematic.svg)
![Все линии широкие, и деталь получилась такой же широкой](../../../articles/images/travel_compensate_overlapping_walls_enabled_disabled.png)
![Часть линий имеют маленькую ширину. В этом случае печать становится точнее](../../../articles/images/travel_compensate_overlapping_walls_enabled_enabled.png)

Ширина линии стены, перекрывающая соседнюю уменьшается на площадь перекрытия, компенсируя переэкструзию.

Как описано выше, этот параметр имеет тенденцию улучшать точность деталей, но не без недостатков. Одним из таких является изменение скорости потока материала, что в следствии приводит к неравномерной экструзии в целом. В некоторых частях может быть недоэкструзия, а в некоторых может быть даже избыток материала. Кроме этого скорость потока может быть снижена настолько, что может привезти к полной остановке подачи материала даже там где он должна быть. Чтобы уменьшить эффект недоэкструзии, воспользуйтесь параметром  [Минимальный поток стенки](../shell/wall_min_flow.md) для ограничения минимальной скорости за счет точности изготовления детали.

**Включенный параметр может сделать модель не слишком эстетичным. Визуально программа не показывает компенсацию перекрытия стен, а вид стоя основан на сгенерированном G-code. В реальности слои ведут себя иначе и способны вытеснять друг друга из своих мест, особенно в тех, где идет их перекрытие. Более того, перепады потока материала очень сильно сказываются на качестве печати, поскольку экструдер хоть и способен изменить свою скорость быстро, материал этого сделать не позволит из-за его упругости. Все эти особенности делаю результат печати более непредсказуемой, чем его визуализация в программе.** 