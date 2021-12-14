Задания для выполнения
Реализовать протокол Диффи-Хеллмана в виде клиент-серверного приложения.
Реализовать клиент-серверную пару, которая шифрует сообщения асимметричным способом
Дополнительные задания
Модифицируйте код клиента и сервера так, чтобы приватный и публичный ключ хранились в текстовых файлах на диске и, таким образом, переиспользовались между запусками.
Проведите рефакторинг кода клиента и сервера так, чтобы все, относящееся к генерации ключей, установлению режима шифрования, шифрованию исходящих и дешифрованию входящих сообщений было отделено от основного алгоритма обмена сообщениями.
Реализуйте на сервере проверку входящих сертификатов. На сервере должен храниться список разрешенных ключей. Когда клиент посылает на сервер свой публичный ключ, сервер ищет его среди разрешенных и, если такого не находит, разрывает соединение. Проверьте правильность работы не нескольких разных клиентах.
Модифицируйте код клиента и сервера таким образом, чтобы установление режима шифрования происходило при подключении на один порт, а основное общение - на другом порту. Номер порта можно передавать как первое зашифрованное сообщение.
Модифицируйте код FTP-сервера таким образом, чтобы он поддерживал шифрование.

Скрины проделанной работы:
Основная логика проделанной работы: 
Клиент наряду с сервером генерирует пару ключей. Во время подключения клиент посылает серверу свой ключ(открытый), в то же время, сервер посылает клиенту свой ключ. Сообщение, которое посылается клиентом серверу, шифруется закрытым ключом клиента и открытым ключом сервера. Затем сервер принимает сообщение, расшифровывает его своим закрытым ключом и открытым ключом клиента. Аналогично посылается и обратное сообщение. Для шифрования и расшифрования используются функции симметричного шифрования

Файл client.py: 

![image](https://user-images.githubusercontent.com/92279258/145915241-5b17d3ab-3d91-4790-a8cf-a6285e317d9d.png)
