Немного странное консольное приложение, которое может отсылать сообщение от имени бота в приватный либо общий чат о наступлении определенного события на OPC сервере.
Такое событие может быть равенство некоторого сигнала определенной величине. Проверить работу можно с помощью симулятора OPC сервера  Gray Simulator http://gray-box.net/download_graysim.php?lang=ru
В качестве отслеживаемого сигнала можно выбрать битовый регистр storage.bool.reg02, который сравнивается со значением TRUE (в конфиге это пишется как ee;1) и как только значение бита становится TRUE, то отправляется соответствующее сообщение всем абонентам прописанным в конфиге. Аналогчным же образом можно сравнивать и сигналы типа real или int например numeric.sin.int16 >= 90 (в конфиге ge;90)
В конфиге каждому тегу соответствует свое условие, и сообщение. Условия описываются следующим образом: 
gt (greater) больше > (gt;0)
lt (lesser) меньше < (lt;0)
ge (greater equivalent) больше или равно >= (ge;0)
le (less equivalent) меньше или равно <= (le;0)
ee (equivalent) равно = (ee;0)
ne (not equivalent) не равно <> (ne;0)

Отсылка сообщения осуществляется простым get запросом на сервер телеграм. У меня же на одном компьютере выдавалась ошибка по сертификатам и потому пришлось посылать запрос на другой сервер, который пересылал это дело в телеграм.

