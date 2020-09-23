# load-info-telegram

![alt tag](https://github.com/unixhostpro/load-info-telegram/blob/master/loadinfotel.png)

Скрипт уведомлений о нагрузки на сервер. При определенном пороге нагрузки вы будет получать уведомления с полной информацией о всех процессах. 

Скачиваем скрипт в папку /usb/bin
> wget -P /usr/bin https://raw.githubusercontent.com/unixhostpro/load-info-telegram/master/load-info-telegram.sh

Cкачиваем файл который будет запускать скрипт как сервис 
> wget -P /etc/systemd/system https://raw.githubusercontent.com/unixhostpro/load-info-telegram/master/tload.service

Редактируем скрипт и вставляем в него свой token и chatid 

> nano /usr/bin/load-info-telegram.sh

В скрипте устанавливаем порог уведомлений

mem_threshold - процент занятой памяти при которой будет высылаться уведомление 

load_threshold - значение нагрузки, выше которого, будет высылаться уведомление

Управление работой скрипта

> systemctl start tload.service

> systemctl stop tload.service

Для проверки скрипта установим пакет для стресс-тестирования системы stress-ng 

>apt install stress-ng

Выполним команду для нагрузки CPU и RAM

>stress-ng --cpu 8 --io 2 --vm 1 --vm-bytes 5G --timeout 600s --metrics-brief




[Наш сайт UnixHost](https://unixhost.pro/)

[Блог UnixHost](https://blog.unixhost.pro/)

[Telegram](https://t.me/unixhostpro)

[Twitter](https://twitter.com/UnixHostPro)

[Facebook](https://www.facebook.com/unixhost.pro)

[Вконтакте](https://vk.com/unixhost)
