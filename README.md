# wine-vnc
Контейнер с Wine.
Возможен доступ по VNC и SSH протоколам.

# Использование:
```
wget https://github.com/lexandr0s/wine-vnc/raw/main/winerun && chmod +x winerun && sudo ./winerun prepare
```

Внутри контейнера работа ведется под учетной записью *wineuser*. Пароль по умолчанию: *wineuser*

При первом запуске скрипт подготовит домашнюю директорию пользователя.

После этого вам необходимо изменить переменные по умолчанию, открыв скрипт любым текстовым редактором. Например
```nano winerun```

После запуска контейнера к нему можно подключиться по протоколам VNC или SSH.

Пароль для подключения VNC задается в переменных скрипта.

В целях безопасности по умолчанию SSH доступ отключен. Т.к. порты контейнера смотрят напрямую в интернет (если нет внешнего брандмауэра), подключение с паролем по умолчанию крайне небезопасно. Поэтому, перед тем как включить SSH доступ, рекомендуется зайти через VNC и изменить пароль пользователя wineuser набрав в терминале ```passwd```

Скрипт требует запуска из под root или через sudo

### Допустимые команды:
```
sudo ./winerun start - запуск контейнера;
sudo ./winerun stop - останавка контейнера;
sudo ./winerun restart - перезапуск контейнера;
sudo ./winerun prepare - подготовка домашней директории пользователя.
```

В той же директории откуда был запущен скрипт создается директория *winevnc*. При запуске контейнера эта директория монтируется в домашнюю директорию пользователя внутри контейнера. Все данные в ней сохраняются при остановке/перезапуске. Так же любые данные можно изменять извне контейнера напрямую с хоста.

При подготовке в домашнюю директорию будут установлены скрипты *aliasxrus/torrent-manager* и *aliasxrus/go-torrent-manager*.

Также домашней директории присутствует bash-скрипт *autostart.sh*. В него можно добавить любые команды для автозапуска, в стандартном формате оболочки bash-shell.

# PS: Адреса для доната
Tron: **TLxWEnUodNVF7H3ocQUHU63V9RfaDryTMC**

BTT in-app: **BJqm3sy19jWOuRDCbG6QhMU5p3XuqupGrE7X2tEM+eqikjrrSEB2YM44Sa1tD0uqEoGMxRT5kihl/8ATkOZnz9E=**
