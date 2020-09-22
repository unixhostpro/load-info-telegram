# load-info-telegram
Скрипт уведомлений о нагрузки на сервер. При определенном пороге нагрузки вы будет получать уведомления с полной информацией о всех процессах. 

Скачиваем скрипт в папку /usb/bin
wget -P /usb/bin https://raw.githubusercontent.com/unixhostpro/load-info-telegram/master/load-info-telegram.sh

Cкачиваем файл который будет запускать скрипт как сервис 
wget -P /etc/systemd/system https://raw.githubusercontent.com/unixhostpro/load-info-telegram/master/tload.service

Редактируем скрипт и вставляем в него свой token и chatid 
nano /usb/bin/load-info-telegram.sh

В скрипте устанавливаем порог уведомлений

mem_threshold - процент занятой памяти при которой будет высылаться уведомление 

Управление работой скрипта

systemctl start tload.service

systemctl stop tload.service
