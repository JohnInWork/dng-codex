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

04.10.2026 тем же приёмом — ещё три, чьи накладки проскочили сторожа (в имени
дефис). Собирает `tools/atlas/derive-badges.py`, ничего не скачивая.

| file | from | для чего |
| --- | --- | --- |
| `icon/potion-heal-wounds.png` | `item/potion/i-heal-wounds.png` | зелье исцеления ран |
| `icon/ring-r-cold.png` | `item/ring/i-r-cold.png` | заклинание «Ледяной доспех» (с 04.10.2026 — «Ледяное благословение») |
| `icon/ring-magical-power.png` | `item/ring/i-magical-power.png` | заклинание «Грозовая вспышка» (до 04.10.2026) |

04.10.2026 — ещё два, картинки заклинаний, которые Иван выбрал в редакторе
«Книга заклинаний». Тот же приём и тот же скрипт.

| file | from | для чего |
| --- | --- | --- |
| `icon/ring-stealth.png` | `item/ring/i-stealth.png` | заклинание «Ускорение» |
| `icon/staff-death.png` | `item/staff/i-staff_death.png` | заклинание «Лич» |

04.10.2026 — значки характеристик для строк интерфейса (Иван выбрал накладки
зелий прибавки). Без масштаба: обрезка по содержимому, 15×15 — в строке рядом с
текстом 12 px буквы толщиной в пиксель иначе пропадают. Тот же скрипт.

| file | from | для чего |
| --- | --- | --- |
| `attr/strength.png` | `item/potion/i-gain-strength.png` | сила |
| `attr/agility.png` | `item/potion/i-gain-dexterity.png` | ловкость |
| `attr/intelligence.png` | `item/potion/i-gain-intelligence.png` | интеллект |

## `item/`

| file | what |
| --- | --- |
| `belt.png` | Пояс для пустого слота. В библиотеке предмета-пояса нет вовсе — в слоте лежал слой бумажной куклы `player/legs/belt_gray.png`: полоска 10×5 пикселей, растянутая на 54×77 и вылезавшая за кнопку. Нарисован в той же палитре, что месяц и домик. |
| `legs/*.png` | Иконки штанов (слот `legs`): слои куклы `player/legs/<то же имя>.png`, обрезанные по содержимому, увеличенные ровно вдвое и положенные в центр холста 32×32 — тем же приёмом, что значки в `icon/`. Предметов-штанов в библиотеке нет, а слой куклы лежит в нижней трети холста и в клетке выглядел бы крошечным. `pants_brown.png` заодно служит картинкой пустого слота. |
| `body/`, `head/`, `boots/`, `gloves/`, `cloak/`, ещё десять `legs/` | Значки дополнительных видов брони (27.09.2026, `tools/dcss-rpg-armour-looks.js`): слой куклы `player/<слот>/<то же имя>.png` тем же приёмом — обрезать, увеличить в целое число раз (куртки и штаны ×2, мелкие шлемы и обмотки до ×3, мантии и плащи ×1), в центр 32×32. У перчаток и сапог левая и правая половина пары сдвинуты вплотную, иначе в клетке были бы две точки по краям. Собирает `tools/atlas/derive-icons.py`; он же воспроизводит девять прежних штанов пиксель в пиксель. |
| ещё 64 `body/`, 45 `head/`, 7 `legs/`, 4 `gloves/` | Значки новых вещей из свободных слоёв куклы (27.09.2026: рубахи, жилеты, куртки, рясы, мантии, халаты, кафтаны, кирасы; повязки, шапки, капюшоны, тюрбаны, колпаки, шляпы; юбки и набедренные повязки; перчатки и наручи). Тот же приём и тот же скрипт (`НОВЫЕ_ВЕЩИ` в `tools/atlas/derive-icons.py`). |
| `body/mail_shirt.png`, `body/apprentice_robe.png`, `body/scout_coat.png`, `head/apprentice_hat.png`, `head/archer_hood.png`, `head/scout_hood.png` | Значки стартовой одежды классов (30.09.2026) — из перекрашенных слоёв `derived/player/<слот>/<то же имя>.png` тем же приёмом (`ИЗ_ПЕРЕКРАСКИ` в `tools/atlas/derive-icons.py`). |
| `boots/mesh_black.png`, `boots/middle_purple.png`, `boots/spider.png`, `boots/blue_gold.png`, `boots/hooves.png`, `gloves/glove_short_gray.png`, `gloves/gauntlet_blue.png`, `gloves/glove_grayfist.png`, `gloves/glove_red.png`, `gloves/glove_white.png`, `cloak/gray.png`, `cloak/red.png`, `cloak/white.png`, `cloak/yellow.png`, `cloak/magenta.png` | Значки основного вида вещей второй половины дороги (02.10.2026). Значком у них служил сам слой куклы `player/<слот>/<то же имя>.png`: сапоги у нижнего края клетки, перчатки — две точки по краям, плащ сдвинут вниз. Тот же приём, что у остальных видов этих слотов (`ИЗ_СЛОЯ_КУКЛЫ` в `tools/atlas/derive-icons.py`). |
| `head/crown_gold2.png` | Значок «Древней короны» (02.10.2026): слой куклы `player/head/crown_gold2.png` тем же приёмом (×3). Раньше значком был бронзовый шлем с плюмажем `item/armour/headgear/helmet_art3.png` — не корона и не то, что у героя на голове. |
| `belt/belt_gray.png`, `belt/belt_redbrown.png`, `belt/belt1.png`, `belt/belt2.png` | Значки поясов (02.10.2026): слой куклы `player/legs/belt_gray.png`, `player/legs/belt_redbrown.png`, `player/body/belt1.png`, `player/body/belt2.png`, обрезанный, увеличенный вдвое и положенный в центр 32×32 (`ПОЯСА` в `tools/atlas/derive-icons.py`). Раньше значком была сама полоска на талии куклы, ниже центра клетки. |

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

### Составные существа генератора v23 (01.10.2026)

В библиотеке дракониане и повелители ада лежат частями — DCSS кладёт слои
друг на друга сама. У нас существо — одна картинка, поэтому части собраны
заранее: слои библиотеки положены друг на друга без единого изменения цвета,
снизу вверх. Высокие картинки (части повелителей 32×48 и `sprint/unspeakable`)
положены на квадрат 48×48 — по центру по ширине и по низу, лишнее прозрачно:
мир рисует спрайт квадратом, и высокий файл сплющился бы. Собирает
`tools/atlas/derive-road-fauna.py` по таблице `ROAD_FAUNA_COMPOSITES`
(`tools/dcss-rpg-road-fauna.js`).

| file | from (снизу вверх, пути от `mon/`) |
| --- | --- |
| `brown_draconian.png` | `draco/draco-base-brown` + `draco/draco-job-knight` |
| `yellow_draconian.png` | `draco/draco-base-yellow` + `draco/draco-job-caller` |
| `white_draconian.png` | `draco/draco-base-white` + `draco/draco-job-monk` |
| `purple_draconian.png` | `draco/draco-base-purple` + `draco/draco-job-shifter` |
| `black_draconian.png` | `draco/draco-base-black` + `draco/draco-job-zealot` |
| `red_draconian.png` | `draco/draco-base-red` + `draco/draco-job-scorcher` |
| `green_draconian.png` | `draco/draco-base-green` + `draco/draco-job-annihilator` |
| `mantis_fiend.png` | `panlord/demon_wings_dragonfly` + `demon_body_mantis` + `demon_head_bird`, на 48×48 |
| `skull_fiend.png` | `panlord/demon_wings_bat` + `demon_body_fat` + `demon_head_cow_skull`, на 48×48 |
| `squid_fiend.png` | `panlord/demon_body_tentacley` + `demon_head_cthulhu`, на 48×48 |
| `plated_fiend.png` | `panlord/demon_wings_hooked` + `demon_body_armour` + `demon_head_helmet`, на 48×48 |
| `trunk_fiend.png` | `panlord/demon_body_crouch` + `demon_head_elephant`, на 48×48 |
| `unspeakable.png` | `sprint/unspeakable` (32×48), на 48×48 |

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

02.10.2026: у слоя правой руки под кулаком героя дыра в рукояти (слой лежит
поверх пальцев) — значок выходил разорванным: голова, щель, кусок рукояти.
Перед обрезкой дыра закрывается сечением той же рукояти, сдвинутым по прямой
древка (`tools/atlas/grip.py`); цвета и ширина — от рукояти рядом, слой на
герое не меняется. У двух цепов, рапиры и двух кнутов, где рукоять идёт
наискось или петля висит сбоку, несколько пикселей поставлены руками
(`РУЧНЫЕ` в том же файле): цвет каждого взят у пикселя той же картинки. Так
пересобраны 45 значков оружия, и так же сделаны десять новых — основные виды
вещей второй половины дороги, у которых значком был сам слой куклы у края
клетки: `hand1/axe_small.png`, `axe_short.png`, `axe_double.png`,
`battleaxe.png`, `axe_blood.png`, `knife.png`, `enchantress_dagger.png`,
`bow.png`, `great_bow.png`, `black_whip.png`.

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
холста 32×32 — тем же приёмом, что `derive-hand-icons.py`; с 02.10.2026 —
с рукоятью, дорисованной под кулаком, `tools/atlas/grip.py`).

## Слой на герое — того же цвета, что значок (02.10.2026)

Иван: «иконка топора одна, а когда я его надел, то топор был другого цвета».
Аудит всех вещей и видов (`node scripts/item-visual-audit.mjs`) нашёл полсотни
пар, где значок рюкзака и слой на герое взяты из разных наборов библиотеки:
бурый кожаный плащ в рюкзаке — чёрный на спине, синий меч — серый в руке,
золотой посох — бурая палка. Силуэт и тени слоя остаются; пиксели «чужого»
материала встают на цвета, которыми нарисован значок, по ступеням светлоты
(тёмное к тёмному, светлое к светлому); контур и остальные материалы не
меняются. Где значок противоречил имени вещи («Золотые сапоги» с бурым
значком, «Кровавая мантия» с фиолетовым), наоборот перекрашен значок — по
цветам слоя. Собирает `tools/atlas/derive-agree.py`; семейства цвета — в
`tools/atlas/colour_family.py`. Пути — от `derived/`.

| file | from | colours of | change |
| --- | --- | --- | --- |
| `player/hand1/morg_copper.png` | `player/hand1/artefact/morg.png` | `item/weapon/artefact/urand_morg.png` | золото → бронза/кожа (short-blade 3) |
| `player/hand1/falchion2_bronze.png` | `player/hand1/falchion2.png` | `item/weapon/falchion3.png` | синий → бронза/кожа (iron-falchion 3) |
| `player/hand1/axe_executioner2_steel.png` | `player/hand1/axe_executioner2.png` | `item/weapon/hand_axe1.png` | синий → серый металл (executioner-axe 1) |
| `player/hand1/quarterstaff_gold.png` | `player/hand1/quarterstaff.png` | `item/staff/staff01.png` | бронза/кожа → золото (apprentice-staff 1-2) |
| `player/hand1/quarterstaff_red.png` | `player/hand1/quarterstaff.png` | `item/staff/staff03.png` | бронза/кожа → красный (apprentice-staff 3) |
| `player/hand1/staff_skull_green.png` | `player/hand1/staff_skull.png` | `item/staff/staff05.png` | серый металл → зелёный (skull-staff 3) |
| `player/hand1/bow_three_wood.png` | `player/hand1/bow_three.png` | `item/weapon/ranged/longbow1.png` | красный → бронза/кожа (longbow 1, 3) |
| `player/hand1/spear_two_blue.png` | `player/hand1/spear_two.png` | `item/weapon/spear2.png` | золото → синий (war-pike 1) |
| `player/hand1/bow_two_wood.png` | `player/hand1/bow_two.png` | `item/weapon/ranged/shortbow1.png` | золото → бронза/кожа (short-bow 1) |
| `player/hand1/arbalest_two_blue.png` | `player/hand1/arbalest_two.png` | `item/weapon/ranged/arbalest3.png` | бронза/кожа → синий (arbalest 3) |
| `player/hand1/whip2_green.png` | `player/hand1/whip2.png` | `item/weapon/bullwhip3.png` | бронза/кожа → зелёный (barbed-whip 1) |
| `player/hand1/double_sword_blue.png` | `player/hand1/double_sword.png` | `item/weapon/double_sword2.png` | серый металл → синий (double-sword 2) |
| `player/hand1/double_sword_red.png` | `player/hand1/double_sword.png` | `item/weapon/double_sword3.png` | серый металл → красный (double-sword 3) |
| `player/hand1/scythe_blue.png` | `player/hand1/scythe.png` | `item/weapon/scythe2.png` | красный → синий (war-scythe 2) |
| `player/hand1/flail_ball_blue.png` | `player/hand1/flail_ball.png` | `item/weapon/flail2.png` | серый металл → синий (iron-flail 2) |
| `player/hand1/eveningstar_blue.png` | `player/hand1/eveningstar.png` | `item/weapon/eveningstar2.png` | серый металл → синий (eveningstar 2) |
| `player/hand1/flail_great_blue.png` | `player/hand1/flail_great.png` | `item/weapon/dire_flail2.png` | серый металл → синий (dire-flail 2) |
| `player/hand1/giant_club_spike_red.png` | `player/hand1/giant_club_spike.png` | `item/weapon/giant_spiked_club.png` | бронза/кожа → красный (spiked-club 1, 5) |
| `player/hand1/long_sword_slant2_steel.png` | `player/hand1/long_sword_slant2.png` | `item/weapon/long_sword1.png` | синий → серый металл (long-sword 1-2) |
| `player/hand2/short_sword_slant2_steel.png` | `player/hand2/misc/short_sword_slant2.png` | `item/weapon/long_sword1.png` | синий → серый металл (long-sword 1-2, левая рука) |
| `player/hand1/falchion2_steel.png` | `player/hand1/falchion2.png` | `item/weapon/falchion1.png` | синий → серый металл (iron-falchion 2) |
| `player/hand1/great_sword_slant2_steel.png` | `player/hand1/great_sword_slant2.png` | `item/weapon/greatsword1.png` | синий → серый металл (dungeon-greatsword 1-2) |
| `player/hand1/dagger_slant_gold.png` | `player/hand1/dagger_slant.png` | `item/weapon/dagger3.png` | серый металл → бронза/кожа (bone-dirk 1) |
| `player/hand2/dagger_gold.png` | `player/hand2/misc/dagger.png` | `item/weapon/dagger3.png` | серый металл → бронза/кожа (bone-dirk 1, левая рука) |
| `player/hand1/club_slant_red.png` | `player/hand1/club_slant.png` | `item/weapon/club2.png` | бронза/кожа → красный (oak-club 2) |
| `player/hand1/mace_blue.png` | `player/hand1/mace.png` | `item/weapon/mace2.png` | серый металл → синий (iron-mace 2) |
| `player/hand1/morningstar_two_blue.png` | `player/hand1/morningstar_two.png` | `item/weapon/morningstar2.png` | серый металл → синий (morning-star 1) |
| `player/hand1/morningstar_two_green.png` | `player/hand1/morningstar_two.png` | `item/weapon/morningstar3.png` | серый металл → зелёный (morning-star 3) |
| `player/hand1/bow_two_silver.png` | `player/hand1/bow_two.png` | `item/weapon/ranged/shortbow3.png` | золото → серый металл (short-bow 3) |
| `player/hand1/hand_crossbow_steel.png` | `player/hand1/hand_crossbow.png` | `item/weapon/ranged/hand_crossbow2.png` | бронза/кожа → серый металл (hand-crossbow 1) |
| `player/hand1/scimitar_bone.png` | `player/hand1/scimitar.png` | `item/weapon/scimitar3.png` | серый металл → бронза/кожа (scimitar 2) |
| `player/hand1/triple_sword_blue.png` | `player/hand1/triple_sword.png` | `item/weapon/triple_sword2.png` | серый металл → синий (triple-sword 2) |
| `player/hand1/eveningstar_red.png` | `player/hand1/eveningstar.png` | `item/weapon/eveningstar3.png` | серый металл → красный (eveningstar 3) |
| `player/hand1/giant_club_spike_steel.png` | `player/hand1/giant_club_spike.png` | `item/weapon/giant_spiked_club3.png` | бронза/кожа → серый металл (spiked-club 3) |
| `player/hand1/large_mace_bronze.png` | `player/hand1/large_mace.png` | `item/weapon/mace_large3.png` | серый металл → бронза/кожа (great-mace 3) |
| `player/body/robe_black_gold_green.png` | `player/body/robe_black_gold.png` | `item/armour/robe_art1.png` | серый металл → зелёный (runic-robe 1) |
| `player/body/half_plate_bronze.png` | `player/body/half_plate.png` | `item/armour/scale_mail3.png` | серый металл → бронза/кожа (half-plate 3) |
| `player/body/dragonsc_ice.png` | `player/body/dragonsc_cyan.png` | `item/armour/ice_dragon_hide.png` | синий → серый металл (ice-dragon-scales 3) |
| `player/body/chain_bronze.png` | `player/body/green_chain.png` | `item/armour/ring_mail1.png` | зелёный → бронза/кожа (ring-mail 1) |
| `player/body/isildur_red.png` | `player/body/isildur.png` | `item/armour/artefact/urand_salamander.png` | серый металл → красный (ring-mail 3) |
| `player/body/gil-galad_violet.png` | `player/body/gil-galad.png` | `item/armour/ring_mail3.png` | синий → фиолетовый (ring-mail 5) |
| `player/body/dragonarm_ice.png` | `player/body/dragonarm_cyan.png` | `item/armour/ice_dragon_hide.png` | синий → серый металл (ice-dragon-scales 2) |
| `item/body/robe_art2_red.png` | `item/armour/robe_art2.png` | `player/body/robe_red_gold.png` | фиолетовый → красный (значок blood-robe 1) |
| `player/head/fhelm_horn2_red.png` | `player/head/fhelm_horn2.png` | `item/armour/headgear/helmet_art1.png` | серый металл → красный (horned-helm 1) |
| `player/head/helm_leather.png` | `player/head/helm_green.png` | `item/armour/headgear/elven_leather_helm.png` | зелёный → бронза/кожа (elven-helm 1) |
| `player/head/wizard_scholar.png` | `player/head/wizard_white.png` | `item/armour/headgear/hat1.png` | серый металл → синий (scholar-hat 1: шляпа, как на значке, а не капюшон) |
| `player/head/art_dragonhelm_steel.png` | `player/head/art_dragonhelm.png` | `item/armour/headgear/helmet_ego1.png` | синий → серый металл (drake-helm 1) |
| `player/head/bear_grey.png` | `player/head/bear.png` | `item/armour/artefact/urand_bear.png` | бронза/кожа → серый металл (bearskin-hood 1) |
| `player/boots/middle_gray_leather.png` | `player/boots/middle_gray.png` | `item/armour/boots2_jackboots.png` | серый металл → бронза/кожа (jackboots 1) |
| `player/boots/middle_brown2_gold.png` | `player/boots/middle_brown2.png` | `item/armour/boots3_stripe.png` | красный → золото (spider-boots 1) |
| `item/boots/boots1_gold.png` | `item/armour/boots1_brown.png` | `player/boots/middle_gold.png` | бронза/кожа → золото (значок golden-boots 1) |
| `player/cloak/black_leather.png` | `player/cloak/black.png` | `item/armour/cloak1_leather.png` | серый металл → бронза/кожа (travel-cloak 1: и почти чёрная заливка тоже) |
| `player/cloak/blue_silver.png` | `player/cloak/blue.png` | `item/armour/cloak2.png` | синий → серый металл (tide-cloak 1) |
| `player/cloak/blue_magenta.png` | `player/cloak/blue.png` | `item/armour/cloak4.png` | синий → фиолетовый (tide-cloak 2) |
| `player/cloak/dragonskin_blue.png` | `player/cloak/dragonskin.png` | `item/armour/cloak3.png` | зелёный → синий (dragon-cloak 1) |
| `player/gloves/glove_black_leather.png` | `player/gloves/glove_black.png` | `item/armour/glove1.png` | серый металл → красный (leather-gloves 1) |
| `player/gloves/claws_blue.png` | `player/gloves/claws.png` | `item/armour/glove5.png` | серый металл → синий (beast-claws 1) |
| `player/hand2/buckler_green_gold.png` | `player/hand2/buckler_green.png` | `item/armour/shields/buckler3.png` | зелёный → синий; серый металл → золото (wood-buckler 3) |
| `player/hand2/shield_knight_gray_blue.png` | `player/hand2/shield_knight_gray.png` | `item/armour/shields/shield2.png` | серый металл → синий (round-shield 2) |
| `player/hand2/shield_knight_gray_green.png` | `player/hand2/shield_knight_gray.png` | `item/armour/shields/shield1.png` | серый металл → зелёный (round-shield 1) |
| `player/hand2/buckler_green_rust.png` | `player/hand2/buckler_green.png` | `item/armour/shields/buckler2.png` | зелёный → бронза/кожа (wood-buckler 2) |
| `player/hand2/lshield_quartered_red.png` | `player/hand2/lshield_quartered.png` | `item/armour/shields/large_shield1.png` | синий → красный (tower-shield 1) |
| `player/hand2/lshield_quartered_gold.png` | `player/hand2/lshield_quartered.png` | `item/armour/shields/large_shield3.png` | синий → бронза/кожа (tower-shield 3) |
| `player/hand2/shield_bullseye_violet.png` | `player/hand2/shield_bullseye.png` | `item/armour/shields/shield3.png` | красный → фиолетовый (spiked-shield 1) |
| `player/hand2/book_moss.png` | `player/hand2/misc/book_red.png` | `derived/books/moss.png` | красный → серый металл (dead-book 1) |
| `player/hand2/lshield_long_blue.png` | `player/hand2/lshield_long_red.png` | `item/armour/shields/lshield_louise.png` | красный → синий (cross-pavise 1) |
| `player/hand2/lshield_of_ignorance_wood.png` | `player/hand2/lshield_of_ignorance.png` | `item/armour/artefact/urand_ignorance.png` | золото → бронза/кожа (cross-pavise 3) |
| `player/hand2/lshield_gold_red.png` | `player/hand2/lshield_gold.png` | `item/armour/shields/shield_donald.png` | бронза/кожа → красный (bulwark 1) |

Два значка оружия сделаны из своих слоёв тем же приёмом, что `item/hand1/`
(`tools/atlas/derive-hand-icons.py`): `item/hand1/staff_mage.png` — жезл
(раньше значком жезла была угловая накладка «посоха направления», не посох) и
`item/hand1/trident_elec.png` — трезубец бури (раньше — значок копья).

## Жезлы Ивана (03.10.2026, генератор v28)

Собирает `tools/atlas/derive-wands.py`, ничего не скачивая.

Значки видов жезлов `icon/wand-*.png` — тем же приёмом, что двадцать восемь
значков выше: угловая накладка библиотеки обрезана по содержимому, увеличена
ровно вдвое и положена в центр 32×32. Где у смысла нет своей накладки, взята
близкая и перекрашена в абсолютный тон (яркость — от исходника, тёмная обводка
остаётся).

| file | from | change |
| --- | --- | --- |
| `icon/wand-flood.png` | `item/staff/i-staff_air.png` | вихрь перекрашен в воду (синий) |
| `icon/wand-magma.png` | `item/staff/i-staff_earth.png` | глыба перекрашена в лаву (оранжево-красный) |
| `icon/wand-digging.png` | `item/wand/i-digging.png` | — |
| `icon/wand-stone.png` | `item/staff/i-staff_earth.png` | — |
| `icon/wand-thorns.png` | `item/rod/i-rod_inaccuracy.png` | — |
| `icon/wand-sparks.png` | `item/rod/i-rod_lightning.png` | — |
| `icon/wand-flame.png` | `item/wand/i-flame.png` | — |
| `icon/wand-miasma.png` | `item/rod/i-rod_clouds.png` | облако перекрашено в яд (зелёный) |
| `icon/wand-striking.png` | `item/rod/i-rod_striking.png` | — |
| `icon/wand-sleep.png` | `item/wand/i-paralysis.png` | — |
| `icon/wand-polymorph.png` | `item/wand/i-polymorph.png` | — |
| `icon/wand-teleportation.png` | `item/wand/i-teleportation.png` | — |
| `icon/wand-light.png` | `item/staff/i-staff_power.png` | самоцвет перекрашен в свет (жёлтый) |
| `icon/wand-lure.png` | `item/wand/i-enslavement.png` | — |
| `icon/wand-random.png` | `item/wand/i-random_effects.png` | — |
| `icon/wand-chill.png` | `mon/statues/block_of_ice.png` | целиком, без увеличения: снежинки уже у прилива и Ледяного копья |
| `icon/wand-hook.png` | — | крюк нарисован клетками 12×14 в палитре библиотеки (тёмная обводка, сталь, верёвка) и увеличен вдвое |
| `mon/frog_form.png` | `mon/animals/giant_frog.png` | ядовито-салатовая с лиловой тенью: превращённый жезлом враг, а не ручная жаба |
| `mon/wand_thorns.png` | `mon/fungi_plants/briar_patch.png` | темнее, с багровыми шипами: тернии жезла на 20 с, а не куст «Колючего леса» |
| `dngn/lava/cooled_stone.png` | `derived/dngn/lava/lava_bed.png` | та же сетка трещин без жара — серо-бурая корка остывшего камня |

Облики неизвестных жезлов берутся из библиотеки без правки:
`item/wand/gem_plastic.png` («Витой жезл») и `item/rod/rod00.png` …
`rod09.png` («Алый жезл» … «Стальной жезл»), всего обликов жезлов 22 на 19
видов. Приманка — библиотечное чучело `mon/statues/training_dummy.png`, лёд
стужи — плитки `dngn/floor/ice0.png` … `ice3.png`.

## Жезлы заклинаний (03.10.2026, генератор v29)

Собирает тот же `tools/atlas/derive-wands.py`, ничего не скачивая.

Облики неопознанных жезлов `item/wand/*.png` — перекраски жезлов-скипетров
библиотеки: тело скипетра перекрашено в новый цвет (тон и насыщенность;
яркость — от исходника), обводка и золотые накладки остались. Силуэт у
каждого скипетра свой, поэтому два облика одного силуэта различаются цветом,
а одного цвета — силуэтом.

| file | from | colour |
| --- | --- | --- |
| `item/wand/teal-rod.png` | `item/rod/rod00.png` | бирюзовый |
| `item/wand/charcoal-rod.png` | `item/rod/rod00.png` | угольный |
| `item/wand/lavender-rod.png` | `item/rod/rod00.png` | лавандовый |
| `item/wand/cobalt-rod.png` | `item/rod/rod01.png` | кобальтовый |
| `item/wand/pearl-rod.png` | `item/rod/rod01.png` | жемчужный |
| `item/wand/garnet-rod.png` | `item/rod/rod02.png` | гранатовый |
| `item/wand/sky-rod.png` | `item/rod/rod02.png` | небесный |
| `item/wand/sand-rod.png` | `item/rod/rod02.png` | песочный |
| `item/wand/honey-rod.png` | `item/rod/rod03.png` | медовый |
| `item/wand/amethyst-rod.png` | `item/rod/rod03.png` | аметистовый |
| `item/wand/ruby-rod.png` | `item/rod/rod04.png` | рубиновый |
| `item/wand/topaz-rod.png` | `item/rod/rod04.png` | топазовый |
| `item/wand/emerald-rod.png` | `item/rod/rod05.png` | изумрудный |
| `item/wand/rose-rod.png` | `item/rod/rod05.png` | розовый |
| `item/wand/mint-rod.png` | `item/rod/rod05.png` | мятный |
| `item/wand/coral-rod.png` | `item/rod/rod06.png` | коралловый |
| `item/wand/snow-rod.png` | `item/rod/rod06.png` | снежный |
| `item/wand/wine-rod.png` | `item/rod/rod06.png` | винный |
| `item/wand/jade-rod.png` | `item/rod/rod07.png` | нефритовый |
| `item/wand/lemon-rod.png` | `item/rod/rod07.png` | лимонный |
| `item/wand/sea-rod.png` | `item/rod/rod08.png` | морской |
| `item/wand/ebony-rod.png` | `item/rod/rod08.png` | эбеновый |
| `item/wand/gilded-rod.png` | `item/rod/rod09.png` | золочёный |
| `item/wand/crimson-rod.png` | `item/rod/rod09.png` | багряный |

Значки опознанных жезлов заклинаний `icon/spellwand-*.png`: знак
заклинания и маленький жезл в левом нижнем углу (нарисован клетками в
палитре библиотеки, 11×11), всё вместе — по центру 32×32. Знак — тот же,
что у заклинания на панели, кроме случаев, когда он занят другой вещью или
совпадает со знаком другого жезла: тогда взят свой.

| file | from | change |
| --- | --- | --- |
| `icon/spellwand-frost-lance.png` | `derived/icon/wand-frost.png` | жезл в углу |
| `icon/spellwand-glaciate.png` | `item/wand/i-slowing.png` | угловая накладка: обрезана, ×2, в центр; перекрашен в лёд; жезл в углу |
| `icon/spellwand-arcane-splinter.png` | `derived/icon/wand-magic_darts.png` | жезл в углу |
| `icon/spellwand-ember-burst.png` | `derived/icon/wand-fireball.png` | жезл в углу |
| `icon/spellwand-frost-burst.png` | `derived/icon/wand-fireball.png` | перекрашен в лёд; жезл в углу |
| `icon/spellwand-storm-burst.png` | `item/ring/i-stealth.png` | угловая накладка: обрезана, ×2, в центр; жезл в углу (с 04.10.2026 — «Ускорение») |
| `icon/spellwand-thunderclap.png` | `derived/icon/scroll-noise.png` | жезл в углу |
| `icon/spellwand-cauterise.png` | `item/weapon/brands/i-pain.png` | угловая накладка: обрезана, ×2, в центр; жезл в углу |
| `icon/spellwand-kindle.png` | `item/ring/i-r-fire.png` | угловая накладка: обрезана, ×2, в центр; жезл в углу |
| `icon/spellwand-ice-armour.png` | `item/ring/i-r-cold.png` | угловая накладка: обрезана, ×2, в центр; жезл в углу |
| `icon/spellwand-purging-light.png` | `derived/icon/scroll-holy_word.png` | жезл в углу |
| `icon/spellwand-renewal.png` | `item/potion/i-restore-abilities.png` | угловая накладка: обрезана, ×2, в центр; жезл в углу |
| `icon/spellwand-unbinding.png` | `item/amulet/i-faith.png` | угловая накладка: обрезана, ×2, в центр; жезл в углу |
| `icon/spellwand-cleanse-ally.png` | `derived/icon/potion-cancel.png` | жезл в углу |
| `icon/spellwand-ward.png` | `derived/icon/amulet-warding.png` | жезл в углу |
| `icon/spellwand-raise-skeleton.png` | `mon/undead/skeletons/skeleton_humanoid_small.png` | жезл в углу |
| `icon/spellwand-raise-ghoul.png` | `mon/undead/ghoul.png` | жезл в углу |
| `icon/spellwand-raise-warden.png` | `mon/undead/skeletal_warrior.png` | жезл в углу |
| `icon/spellwand-share-life.png` | `derived/icon/potion-blood.png` | жезл в углу |
| `icon/spellwand-flight.png` | `derived/icon/potion-flight.png` | жезл в углу |
| `icon/spellwand-invisibility.png` | `derived/icon/potion-invisibility.png` | жезл в углу |
| `icon/spellwand-teleport.png` | `derived/icon/scroll-teleportation.png` | жезл в углу |
| `icon/spellwand-camp-call.png` | `dngn/altars/makhleb_flame1.png` | жезл в углу |
| `icon/spellwand-unlock.png` | `item/misc/runes/generic.png` | жезл в углу |

## Выбор Ивана по листам вариантов (03.10.2026)

Собраны скриптом `tools/atlas/option-sheets.py` из слоёв библиотеки (CC0);
Иван выбрал номера на листах.

| file | from | как |
| --- | --- | --- |
| `hud/hunger.png` | `player/hand1/trident.png`, `player/hand1/fork.png` | вилка (голова трезубца + ручка вилки) и ложка, набранная скриптом палитрой и контуром вилки; стоя, ×2 — значок голода (№ 6) |
| `mon/innkeeper.png` | `player/base/human_m.png`, `player/legs/pants_brown.png`, `player/boots/short_brown2.png`, `player/body/shirt_vest.png`, `player/beard/pj.png`, `player/hair/brown1.png`, `player/hand1/misc/bottle.png` | фигура из слоёв героя; стекло бутылки перекрашено из синего в зелёное — трактирщик (№ 1) |
| `mon/free-blade.png` | `player/cloak/black.png`, `player/base/human_m.png`, `player/legs/pants_black.png`, `player/boots/mesh_black.png`, `player/body/leather_metal.png`, `player/hair/aragorn.png`, `player/hand1/great_sword_slant.png` | фигура из слоёв героя в порядке игры — Вольный клинок (№ 1) |
