# my_project_3(TelegramBot Mining Info@Stats)
Телеграм бот. Статистика майнига. Контроль работы ригов. Информация по криптовалютам

![image](https://user-images.githubusercontent.com/91089601/145733657-4e30082b-3e34-43c3-a0d9-f9b5c0afb366.png)

### В этом проекте все работает через телеграмм бота по API. Статистика ригов, статистика майнинг пула, статистика коинов с биржи, мониторинг работы ригов/ферм.

Мониторинг ригов/ферм. Раз в определеный период опрашивает по API программу miner(она непосредственно занимается добычей криптовалют) и парсит полученные данные, в случае перегрева по GPU or Memory, а также, ошибок в майнере, отправляет сообщение в телеграм. В случае запуска скрипта непосредственно на риге, скрипт не работает если нет инета или риг полностью выкючился. Если задеплоить скрипт на внешнем сервере и собирать данные с внешних IP ригов, то еще будет сообщать в телеграмм о падении инета на риге или его полного отключения.

В телеграмм боте после /start, появляются кнопки /pool_stat /coin_stat /rig_stat которые пришлют в телеграм соответствующую информацию с пула / биржи / ригов.

### Развертование проекта:
```
python -m venv venv
source venv/Scripts/activate
pip install -r requirements.txt

Создать файл .env , указать параметры бота:
TELEGRAM_TOKEN=
TELEGRAM_CHAT_ID=

python mining_tele_bot.py
```