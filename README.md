# Spreader
Видео инструкция: https://youtu.be/teco29Rfh68
--------------------------------------------------------------------------------

Устанавливаем бота "Spreader", предоставляем ликвидность в стакан xcc usdt на бирже LBANK и забираем спред.

Торговый алгоритм для биржи LBank(xcc_usdt)


Бот „Spreader“ одновременно устанавливает два лимитных ордера „limit buy“ и „limit sell“  объёмом „SIZE“, на расстояние „STEP“ в обе стороны от последней цены. При срабатывание одного из ордеров происходит повторная установка новой пары „limit buy“ и „limit sell“. Таким образом, бот продолжает устанавливать пары ордеров в бесконечном цикле следуя за ценой. Каждый ордер имеет свою пару, отследить это можно по времени установки ордеров. Такой подход позволяет купить дешевле, а продать дороже! Для работы бота требуется не только USDT, но и XCC.

------------------------------------------------------------------------------


Конфигурация бота ./constant.ini :
#

[BASE]
HOST = https://www.lbkex.net
PORT = 80

[WEBSOCKET]
URL = wss://www.lbkex.net/ws/V2/

[API]
APIKEY = «Создаётся в личном кабинете LBank»
SECRTKEY = «Создаётся в личном кабинете LBank»

[START_STOP]
# Bot operation. When 'START_STOP = START' the bot works.
START_STOP = START

[FEES]
# Trade rate (%)
TAKERFEE = 0.1

[SIZE]
# If 'FIXED = True' we use values from '[STEP]SIZESTEP'
FIXED = True
# If 'FIXED != True'
SIZE = 1000
STEP = 0.00025

[STEP]
# Let's list 'SIZE' and 'STEP' with a space. Add a new value 'SIZESTEP' on a new line.
# There should be no duplicates 'SIZE'
SIZESTEP = 1000 0.00025


------------------------------------------------

Применение новых значений происходит без перезагрузки бота, после сохранения изменений в файле ./constant.ini

START_STOP — Вкл./Выкл.

TAKERFEE — комиссия биржи за исполнение лимитного ордера.

FIXED — при «FIXED = True» бот использует фиксированный размер ордера, при «FIXED = False» бот использует линейную зависимость от соотношения USDT к XCC. Когда цена снижается бот уменьшает объём покупки и  увеличивает объём продажи, при росте цены, наоборот, уменьшает объём продажи и увеличивает объём покупки.

SIZE — объём ордера в XCC.

STEP — расстояние от текущей цены для установки лимитных ордеров.

SIZESTEP — список каналов (спредов) используемых ботом.

--------------------------------------------------

Выразить благодарность автору за труды и поддержать развитие проекта можно по адресу:

XCH: xch1q5sff0qhv5pzfu9fe2retmx6q7dm5g3yzegutdyjsk48jurcz7qsvemcut

XCC: xcc1zshmdfd8ez4ahjr84gn63845h5qls4cn2cpvg6j9tyxazchdqetsvm2gkk
