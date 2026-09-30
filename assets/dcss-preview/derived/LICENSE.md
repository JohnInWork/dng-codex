# Derived from the CC0 library

Everything here is made from the Dungeon Crawl Stone Soup tiles in the parent
directory, which are CC0 1.0 / public domain. The edits are ours and are placed
under the same dedication: **CC0 1.0**.

The parent `LICENSE.md` says the DCSS copy is unmodified, and it stays that way
— which is exactly why edited files live here instead.

## `books/`

Six book covers, recoloured to an absolute hue from six library covers:

| file | from | hue |
| --- | --- | --- |
| `rust.png` | `item/book/turquoise.png` | rust |
| `ink.png` | `item/book/tan.png` | ink blue |
| `rose.png` | `item/book/metal_green.png` | rose |
| `wine.png` | `item/book/light_blue.png` | wine red |
| `emerald.png` | `item/book/purple.png` | emerald |
| `gold.png` | `item/book/red.png` | gilded |

Two unidentified books that look the same are not a puzzle, they are a bug: the
game needs one distinct cover per book type. The library holds twenty-four and
the game now has thirty spellbooks, so six were painted.

## `tools/`

| file | from | change |
| --- | --- | --- |
| `bandage.png` | `item/food/bread_ration.png` | recoloured to linen |

The library ships no bandage of any kind, and a bandage drawn as a scroll reads
as a spell. The ration is the right shape — a wrapped bundle — so it was
repainted white and lost its bread.

## `hud/`

| file | what |
| --- | --- |
| `home.png` | Домик для значка этажа в городе: там `romanDepth` отдаёт слово «ГОРОД», а места в значке — на одну-две римские цифры. |
| `moon.png` | Месяц для шкалы сна. Нарисован с нуля в палитре игры (`--bone`), без сглаживания: ничего похожего на «сон» в библиотеке нет, а вектор со стороны рядом с тридцатидвойками читался бы чужим. |

## `icon/`

Двадцать восемь значков заклинаний, эффектов и расходников, собранных из
угловых накладок библиотеки (`item/*/i-*.png`).

В DCSS такой файл — не иконка, а метка: игра кладёт её на угол картинки
предмета, поэтому содержимое размером 9–15 пикселей лежит в правом нижнем углу
холста 32×32, а остальное прозрачно. Мы использовали эти файлы как
самостоятельные значки — и они честно рисовались в углу кнопки, смещённые на
6–9 пикселей из тридцати двух. Иван: «почему то многие иконки не по центру в
кнопках».

Каждый обрезан по содержимому, увеличен ровно вдвое (целый множитель — пиксели
остаются квадратными) и положен в центр холста 32×32. Имя файла — папка
источника и название без префикса `i-`: `item/wand/i-fire.png` →
`icon/wand-fire.png`.

## `item/`

| file | what |
| --- | --- |
| `belt.png` | Пояс для пустого слота. В библиотеке предмета-пояса нет вовсе — в слоте лежал слой бумажной куклы `player/legs/belt_gray.png`: полоска 10×5 пикселей, растянутая на 54×77 и вылезавшая за кнопку. Нарисован в той же палитре, что месяц и домик. |
| `legs/*.png` | Иконки штанов (слот `legs`): слои куклы `player/legs/<то же имя>.png`, обрезанные по содержимому, увеличенные ровно вдвое и положенные в центр холста 32×32 — тем же приёмом, что значки в `icon/`. Предметов-штанов в библиотеке нет, а слой куклы лежит в нижней трети холста и в клетке выглядел бы крошечным. `pants_brown.png` заодно служит картинкой пустого слота. |
| `body/`, `head/`, `boots/`, `gloves/`, `cloak/`, ещё десять `legs/` | Значки дополнительных видов брони (27.09.2026, `tools/dcss-rpg-armour-looks.js`): слой куклы `player/<слот>/<то же имя>.png` тем же приёмом — обрезать, увеличить в целое число раз (куртки и штаны ×2, мелкие шлемы и обмотки до ×3, мантии и плащи ×1), в центр 32×32. У перчаток и сапог левая и правая половина пары сдвинуты вплотную, иначе в клетке были бы две точки по краям. Собирает `tools/atlas/derive-icons.py`; он же воспроизводит девять прежних штанов пиксель в пиксель. |
| ещё 64 `body/`, 45 `head/`, 7 `legs/`, 4 `gloves/` | Значки новых вещей из свободных слоёв куклы (27.09.2026: рубахи, жилеты, куртки, рясы, мантии, халаты, кафтаны, кирасы; повязки, шапки, капюшоны, тюрбаны, колпаки, шляпы; юбки и набедренные повязки; перчатки и наручи). Тот же приём и тот же скрипт (`НОВЫЕ_ВЕЩИ` в `tools/atlas/derive-icons.py`). |
| `body/mail_shirt.png`, `body/apprentice_robe.png`, `body/scout_coat.png`, `head/apprentice_hat.png`, `head/archer_hood.png`, `head/scout_hood.png` | Значки стартовой одежды классов (30.09.2026) — из перекрашенных слоёв `derived/player/<слот>/<то же имя>.png` тем же приёмом (`ИЗ_ПЕРЕКРАСКИ` в `tools/atlas/derive-icons.py`). |

## `mon/`

| file | from | change |
| --- | --- | --- |
| `boar.png` | `mon/animals/hog.png` | почти чёрная щетина, красный глаз, клык |
| `wild_sheep.png` | `mon/animals/sheep.png` | тёмная шерсть, красный глаз |
| `death_yak.png` | `mon/animals/death_yak.png` | чёрная шерсть, красные глаза, рога остались костяными |
| `sea_serpent.png` | `mon/animals/sea_snake.png` | морской змей гротов: тёмно-зелёное тело, огненные полосы, красный глаз (`tools/atlas/derive-grotto.py`) |
| `kraken_head_sunk.png` | `mon/aquatic/kraken_head.png` | голова кракена под водой: притоплена в цвет воды гротов, глаза остались красными (`tools/atlas/derive-grotto.py`) |

Кабан и домашняя свинья делили и картинку, и имя: обоих звали «Кабан» и обоих
рисовали одним спрайтом. Кабаньих спрайтов в библиотеке ровно два, и второй —
адский, так что выбирать было не из чего.

29.09.2026 Иван разобрал лист «одна картинка — два смысла»: бурый кабан всё ещё
читался свиньёй, дикая овца, которая нападает, была мирной овцой, а мёртвый як —
яком в серой масти. Теперь у враждебных зверей одно правило — тёмная шерсть и
горящие красные глаза, у кабана ещё клык. Все три собирает
`tools/atlas/derive-beasts.py`; мирные остаются библиотечными.

## `food/`

| file | from | change |
| --- | --- | --- |
| `roast.png` | `item/food/meat_ration.png` | темнее и румянее: кусок, снятый с огня |
| `stew.png` | — | нарисована с нуля |

Жаркое и варёное мясо делили одну картинку, хлеб и сытная похлёбка — другую.
Мясо разошлось перекраской, а с похлёбкой выбирать было не из чего: миски с
едой в библиотеке нет вовсе, а котелки трактира уже стоят у очага. Чаша
нарисована в тех же правилах, что месяц, домик и ремень: целые координаты,
обводка по контуру, одна ступень тени — и пар двумя завитками, чтобы горячее
читалось горячим.

## `books/` — добавлено

Ещё шесть обложек: неопознанных книг стало больше, чем разных переплётов, и
шесть пар снова смотрели одинаково.

| file | from |
| --- | --- |
| `amber.png` | `item/book/light_green.png` |
| `violet.png` | `item/book/metal_blue.png` |
| `jade.png` | `item/book/metal_cyan.png` |
| `brick.png` | `item/book/dark_blue.png` |
| `slate.png` | `item/book/parchment.png` |
| `moss.png` | `item/book/book_of_the_dead.png` |

## `item/hand1/`, `item/hand2/`

Значки видов оружия и щитов (`looks`, 27.09.2026): слой куклы
`player/hand1/<имя>.png` или `player/hand2/<путь>.png`, обрезанный по
содержимому, увеличенный в целое число раз (не больше чем вдвое, чтобы баклер
не вырос крупнее башенного щита) и положенный в центр холста 32×32. Путь значка
повторяет путь слоя. Собираются скриптом `tools/atlas/derive-hand-icons.py`.

## `intro/`

| file | from | change |
| --- | --- | --- |
| `carpet-left.png`, `carpet-mid.png`, `carpet-right.png` | `dngn/floor/demonic_red1.png` | ворс чуть темнее и ровнее, золотая кайма по краю (левый/правый) и золотой ромб по оси (середина) |

Ковровая дорожка тронного зала (`?intro=1`, `tools/dcss-rpg-intro.js`). Ковра
в библиотеке нет ни одного; красный пол без глаз и трещин читается ворсом.
Собирает `tools/atlas/derive-intro-carpet.py`.

## `dngn/lava/`

| file | from | change |
| --- | --- | --- |
| `lava0.png` … `lava5.png` | `dngn/water/shoals_deep_water0.png` … `shoals_deep_water5.png` | яркость воды легла на градиент лавы: тёмное — корка, гребни — раскалённые трещины |
| `lava_bed.png` | `dngn/water/shoals_deep_water0.png` | то же, на две ступени темнее — ложе под мерцанием |

Лава «Магмового уступа» и «Инфернального ядра» (генератор v20,
`docs/2D-LAVA.md`). Своей лавы в библиотеке нет; сетка гребней отмели
читается трещинами в остывающей корке. Собирает `tools/atlas/derive-lava.py`.

## `player/`

Слои бумажной куклы, которых в библиотеке нет, — стартовая одежда классов
(30.09.2026). Иван выбрал силуэты по листу вариантов и поставил условие:
стартовая вещь не повторяет картинку вещи, которая встречается в игре. Все
выбранные силуэты уже носили вещи лута, поэтому каждый перекрашен в свой тон:
цвета исходника встают на те же ступени новой лестницы «тёмный → светлый»,
контур не меняется. Собирает `tools/atlas/derive-outfits.py`.

| file | from | change |
| --- | --- | --- |
| `body/mail_shirt.png` | `player/body/leather_metal.png` | серая сталь вместо чёрного, ячейки узора светлеют до тёмной стали |
| `body/apprentice_robe.png` | `player/body/robe_blue_white.png` | приглушённая синь, кремовая оторочка |
| `head/apprentice_hat.png` | `player/head/wizard_blue.png` | та же синь, что у робы |
| `head/archer_hood.png` | `player/head/hood_green.png` | светлая листовая зелень |
| `body/scout_coat.png` | `player/body/slit_black.png` | тёмно-бурая кожа вместо серого сукна |
| `head/scout_hood.png` | `player/head/hood_gray.png` | бурый, на ступень светлее кафтана |
| `hand1/rusty_sword.png` | `player/hand1/sword_three.png` | ржавый клинок: серая сталь встала на бурую лестницу той же яркости, рукоять и контур прежние |
| `hand2/rusty_sword.png` | `player/hand2/misc/short_sword_slant.png` | то же для меча в левой руке |

Ржавый меч воина (30.09.2026): Иван выбрал по листу вариант 7 — простой прямой
меч с ржавым клинком. Собирает `tools/atlas/derive-rusty-sword.py`, он же
делает значок `item/weapon/rusty_sword.png` (обрезка, поворот на 45°, центр
холста 32×32 — тем же приёмом, что `derive-hand-icons.py`).
