---
tags:
  - approach time
  - AR
  - reading
  - читалка
  - чтение
  - АР
outdated_translation: true
outdated_since: d45afabf155d19c4b9d8bd0f7b68e73bc1f4af16
---

# Approach rate

*Подробнее о рекомендуемых значениях AR: см. [Критерии ранкинга](/wiki/Ranking_Criteria)*

**Approach rate** (сокр. *AR*, рус. *скорость появления нот*, жарг. *аппроач*) — один из параметров сложности [карты](/wiki/Beatmap), определяющий, насколько заранее [объекты](/wiki/Hit_object) появляются перед тем, как игрок должен с ними провзаимодействовать. Этот параметр существует только в [osu!](/wiki/Game_mode/osu!) и [osu!catch](/wiki/Game_mode/osu!catch).

Значения AR варьируются от 0 до 10. Более высокий AR означает, что объекты будут видны в течение более короткого периода времени, что оставляет игроку меньше времени на реакцию. С другой стороны, более низкий AR оставляет больше времени на реакцию, но может привести к переизбытку объектов, одновременно находящихся на экране.

## Время анимации

Длительность пребывания объекта на экране (без каких-либо модов) варьируется от 1800 мс при AR 0 до 450 мс при AR 10. Соседние значения AR ниже 5 отличаются друг от друга на 120 мс, а выше 5 — на 150 мс.

Ниже — наглядное объяснение с формулами:

```
                                       X = нажатие/поимка
             p r e e m p t             ↓
├───────────────────────┬──────────────┤
0%       fade_in         100% видимости
```

Объект начинает появляться в момент `X - preempt`, при этом:

- AR < 5: `preempt = 1200ms + 600ms * (5 - AR) / 5`
- AR = 5: `preempt = 1200ms`
- AR > 5: `preempt = 1200ms - 750ms * (AR - 5) / 5`

Количество времени, необходимое для полного появления объекта, также зависит от AR:

- AR < 5: `fade_in = 800ms + 400ms * (5 - AR) / 5`
- AR = 5: `fade_in = 800ms`
- AR > 5: `fade_in = 800ms - 500ms * (AR - 5) / 5`

## Моды

На AR влияют четыре мода:

- [Easy](/wiki/Game_modifier/Easy): уменьшает значение AR вдвое.
- [Hard Rock](/wiki/Game_modifier/Hard_Rock): умножает значение AR на 1,4, максимум до 10.
- [Double Time](/wiki/Game_modifier/Double_Time): значение AR не меняется, но из-за ускорения карты на 50% время видимости объектов сокращается на 33%.
- [Half Time](/wiki/Game_modifier/Half_Time): значение AR не меняется, но из-за замедления карты на 25% время видимости объектов увеличивается на 33%.

Хотя моды Half Time и Double Time не меняют скорость появления нот, она объективно изменяется за счёт разницы в скорости карты. В таких случаях часто говорят об AR с точки зрения восприятия, а не его фактического значения: например, вместо «AR 8 + DT» можно сказать «AR 9,6».

## osu!taiko и osu!mania

Скорость появления нот отображается в информации о картах [osu!taiko](/wiki/Game_mode/osu!taiko) и [osu!mania](/wiki/Game_mode/osu!mania), но она никак не влияет на игровой процесс. Скорость прокрутки в этих режимах зависит от других факторов.
