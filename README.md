## Создание сертификатов для localhost

1. Создаем закрытый ключ: `openssl genrsa -out rootCA.key 2048`
2. Создаем корневой сертификат: `openssl req -x509 -new -nodes -key rootCA.key -sha256 -days 1024 -out rootCA.pem`
3. Запускаем скрипт: `./create_cert.sh mysite.test`
4. Полученные `mysite.test.crt` и `device.key` передаем веб-серверу
5. Созданный `rootCA.pem` добавляем в доверенные центры сертификации браузера
