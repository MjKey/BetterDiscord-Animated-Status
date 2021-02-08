# BetterDiscord-Animated-Status

<!-- vim-markdown-toc GFM -->

* [Установка](#установка)
* [Использование](#использование)
* [Таймаут / Время текста](#таймаут)
* ['rich' или 'raw' редакторы](#rich-или-raw-редакторы)
* [Анимация](#анимация)
* [Примеры](#примеры)
* [Discord Nitro Смайлики](#discord-nitro-смайлики)
	* [Кастомный Javascript](#кастомный-javascript)

<!-- vim-markdown-toc -->

## Установка
Установить [BetterDiscord](https://github.com/rauenzi/BetterDiscordApp)\
Скачать [animated-status.plugin.js](/animated-status.plugin.js?raw=true) into the following directory\
Mac: `~/Library/Preferences/BetterDiscord`\
Windows: `%appdata%\BetterDiscord\plugins`\
Linux: `~/.config/BetterDiscord/plugins`

## Использование
Откройте Discord, зайдите в Настройки\>Plugins, включите AnimatedStatus и нажмите Настройки.\
Введите необходимую вам информацию и нажмите `save`

## Таймаут
Это значение указывает длину каждого шага анимации в миллисекундах.\
Пример: Если таймаут 2000, то вся данная анимация пройдёт за 4 секунды. (2сек на каждую строчку)
```
"abc"
"def"
```
Тайм-аут анимации должен составлять не менее 2900 миллисекунд, чтобы анимация выглядела плавно на других клиентах. Это гарантирует, что ни один ключевой кадр не будет потерян.\
В мобильных системах тайм-аут может быть установлен немного выше (10-14 секунд)\
^ Информация от [@pintoso](https://github.com/pintoso)

## 'rich' или 'raw' редакторы
Начиная с последней версии, плагин теперь имеет новый улучшенный редактор. Это не добавляет функциональности, но делает редактирование ваших анимаций намного проще!\
![Rich Editor](/screenshots/rich.png?raw=true)\
Редактор raw-это просто поле ввода текста, в котором вы можете редактировать свои анимации вручную в формате json\

## Анимация
![Settings Page](/screenshots/settings.png?raw=true)\
Анимация выполнена в очень простом и понятном синтаксисе.\
Для анимации текста вы можите использовать мой генератор: [Клик](https://mjkey.ru/neco.php?src=Это+тестовый+текст+1+варианта+анимации+текста.+Разработано+MjKey%27ем+по+фану.+Будет+полезно+для+анимации+статуса+дискорда.&type=text1&s=20)
```
"Тест (Сообщение)"
"Тест (Сообщение)", "👍 (символ)"
"Тест (Сообщение)", "смайлик (Nitro смайлик)", "000000000000000000 (Nitro ID смайлика)"
"eval new String('тест') (Javascript)"
"eval new String('тест') (Javascript)", "eval new String('👍') (Javascript)"
...
```
## Примеры
Переключаение текста:
```
"Текст 1"
"Текст 2 с смайликом", "👍"
```

## Discord Nitro Смайлики
- Откройте чат discord, введите `\`.
<img src="screenshots/nitro0.png">
- Выберите эмодзи, которые вы хотите включить в свой статус, с помощью средства выбора эмодзи.
<img src="screenshots/nitro1.png">
- Обратите внимание, что сообщение изменилось на `<:emojiname:emojiid>`. Значения внутри скобок (emojiname и emojiid) - это значения, необходимые для статуса.
<img src="screenshots/nitro2.png">
- Измените настройки соответствующим образом
<img src="screenshots/nitro3.png">

### Кастомный Javascript
Использование текущего времени в качестве своего статуса:
```
"eval let fmt=t=>(t<10?'0':'')+t;let d=new Date();`${fmt(d.getHours())}:${fmt(d.getMinutes())}:${fmt(d.getSeconds())}`;"
```

Использование текущего времени в качестве смайлика своего статуса:
![Settings Page](/screenshots/status_clock.png?raw=true)
```
"eval let fmt=t=>(t<10?'0':'')+t;let d=new Date();`${fmt(d.getHours())}:${fmt(d.getMinutes())}:${fmt(d.getSeconds())}`;", "eval ['🕛','🕐','🕑','🕒','🕓','🕔','🕕','🕖','🕗','🕘','🕙','🕚'][((new Date()).getHours()%12)];"
```
