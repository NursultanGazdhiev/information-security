---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе 1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину."
author: "Гаджиев Нурсултан Тофик оглы НПИ-01-18"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Задание

1. Установить и конфигурировать операционную систему на виртуальную машину.

2. Подключить образ диска Дополнений гостевой OC.

3. Установить mc

# Теоретические сведения

VirtualBox (Oracle VM VirtualBox) — программный продукт виртуализации для операционных систем Microsoft Windows, Linux, FreeBSD, macOS, Solaris/OpenSolaris, ReactOS, DOS и других.

CentOS — дистрибутив Linux. Дистрибутив операционной системы — это форма распространения системного программного обеспечения. ЦентОС основан на коммерческом дистрибутиве Линукс — Red Hat Enterprise Linux (RHEL), который предназначен для корпоративного использования и имеет коммерческую поддержку на протяжении десяти лет.

**Для чего нужна CentOS**

CentOS — это серверная операционная система с открытым исходным кодом. Не является коммерческой и предоставляется бесплатно для конечных пользователей. Ориентируется на бизнес и корпоративных клиентов. Используется на услугах виртуального выделенного сервера и выделенного сервера.

**CentOS 7: что это**

CentOS 7 — это седьмая версия операционной системы ЦентОС, выпущенная в две тысячи четырнадцатом году.

Описание и особенности системы:

- Дата релиза — седьмого июля 2014 года.

- Полная поддержка запланирована до четвертого квартала 2020 года.

- Критические обновления — до 30 июня 2024.

- Разработана на ядре Линукс версии 3.10.

- Включает HTTP-сервер Apache версии 2.4

- Улучшенная асинхронная обработка запросов.

# Выполнение лабораторной работы



Перешёл в каталог /var/tmp и создал каталог с именем пользователя ntgadzhiev. 


Скопировал образ, CentOS-7-x86_64-DVD-2009 виртуальной машины в своем каталоге: 


Запустил виртуальную машину. (рис. -@fig:001)

![Менеджер VirtualBox](image/20.jpg){ #fig:001 width=70% }

Проверить в свойствах VirtualBox месторасположение каталога для виртуальных машин. Для этого в VirtualBox выбрал Файл Свойства, вкладка Общие . В поле Папка для машин было указано другой каталог. Изменил его на /var/tmp/ntgadzhiev (рис. -@fig:002)

![Окно «Свойства» VirtualBox](image/4.jpg){ #fig:002 width=70% }

Создал новую виртуальную машину. Для этого в VirtualBox выбрал Машина Создать. Указал имя виртуальной машины — ntgadzhiev, тип операционной системы — Linux, RedHat.

Указал размер основной памяти виртуальной машины — 1024 МБ. 

Задал конфигурацию жёсткого диска — загрузочный 
VDI (BirtualBox Disk Image) 


Выбрали Динамический виртуальный диск.

Задали размер диска — 40 ГБ


Выделил в окне менеджера VirtualBox виртуальную машину Base, и открыл окно Свойства . Проверил, что папка для снимков виртуальной машины ntgadzhiev имеет путь  (рис. -@fig:003) 

![Окно «Свойства» виртуальной машины Base](image/4.jpg){ #fig:003 width=70% }

Выбрал в VirtualBox Свойства Носители виртуальной машины Base. Добавил новый привод оптических дисков и выбрал образ CentOS-8. (рис. -@fig:004) 

![Окно «Носители» виртуальной машины ntgadzhiev: выбор образа оптического диска](image/2.jpg){ #fig:004 width=70% }

Запустил виртуальную машину Base, выбрал установку системы на жёсткий диск,установил русский язык для интерфейса и раскладки клавиатуры.(рис. -@fig:005)

![Запуск установки системы, установка русского языка и установка русского языка для раскладки клавиатуры](image/5.jpg){ #fig:005 width=70% }

Указал часовой пояс «Москва» (рис. -@fig:006)

![Указать часовой пояс «Москва»](image/6.jpg){ #fig:006 width=70% }

Выберил раскладку клавиатуры. Определил английский язык как первая раскладка чтобы быть по умолчанию. (рис. -@fig:007)

![Раскладка клавиатуры](image/7.jpg){ #fig:007 width=70% }

Выбрал Сервер с GUI и по умолчанию установил Средства разработки. (рис. -@fig:008)

![Выбор программ](image/8.jpg){ #fig:008 width=70% }

Смотрел конфигурацию жёсткого диска. (рис. -@fig:009)

![Конфигурация жёсткого диска](image/9.jpg){ #fig:009 width=70% }

Отключил kdump. (рис. -@fig:010)

![Отключение kdump](image/10.jpg){ #fig:010 width=70% }

Включил интернет и в качестве имени машины указать «ntgadzhiev.localdomain» (рис. -@fig:011)

![Задать сетевое имя виртуальной машины](image/11.jpg){ #fig:011 width=70% }

Установил пароль для root. (рис. -@fig:012)

![Задать сетевое имя виртуальной машины](image/12.jpg){ #fig:012 width=70% }

Создал пользователья. (рис. -@fig:013)

![Создание пользователя](image/13.jpg){ #fig:013 width=70% }

Принимал лицензионное соглашение и вошёл в систему. 

Подключил образ диска Дополнений гостевой OC. (рис. -@fig:014)

![Подключение образа диска Дополнений гостевой OC](image/18.jpg){ #fig:014 width=70% }

# Выводы

Приобрел практические навыки установки операционной системы на виртуальную машину и настройки минимально необходимых для дальнейшей работы сервисов.

