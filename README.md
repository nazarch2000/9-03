# Домашнее задание к занятию 9.3 «Система мониторинга Zabbix. Часть 2» - `Рыженко Назарий`

 ---

### Задание 1

Создайте свой шаблон, в котором будут элементы данных, мониторящие загрузку CPU и RAM хоста.
![image](https://user-images.githubusercontent.com/106932460/213871427-7affc726-be05-4da2-be8a-7d5107f46567.png)
*Сохраните в Git скриншот страницы шаблона с названием «Задание 1».*

 ---

### Задание 2

Добавьте в Zabbix два хоста и задайте им имена <фамилия и инициалы-1> и <фамилия и инициалы-2>. Например: ivanovii-1 и ivanovii-2.

*Результат этого задания сдавайте вместе с заданием 3.*

 ---

### Задание 3

Привяжите созданный шаблон к двум хостам. Также привяжите к обоим хостам шаблон Linux by Zabbix Agent.
![image](https://user-images.githubusercontent.com/106932460/213871461-c5f248e2-9450-4767-9005-9766c34de047.png)
*Сохраните в Git скриншот страницы хостов, где будут видны привязки шаблонов с названиями «Задание 2-3». Хосты должны иметь зелёный статус подключения.*

 ---

### Задание 4

Создайте свой кастомный дашборд.
![image](https://user-images.githubusercontent.com/106932460/214048332-9b6dbf5d-1db7-42e9-9c53-0adc7dd66ba7.png)

*Сохраните в Git скриншот дашборда с названием «Задание 4».*

 ---

### Задание 5* со звёздочкой

Создайте карту и расположите на ней два своих хоста:
1. Настройте между хостами линк.
2. Привяжите к линку триггер, связанный с agent.ping одного из хостов, и установите индикатором сработавшего триггера красную пунктирную линию.
3. Выключите хост, чей триггер добавлен в линк. Дождитесь срабатывания триггера.
![image](https://user-images.githubusercontent.com/106932460/214050957-edebebe8-b82f-4e21-945a-7ae984254c93.png)
![image](https://user-images.githubusercontent.com/106932460/214051031-511f85bf-4537-47ab-b671-ed06ef7b5196.png)
![image](https://user-images.githubusercontent.com/106932460/214051210-6da3a81d-6f45-4f38-8b51-3fbcacd82960.png)

* Сохраните в Git скриншот карты, где видно, что триггер сработал, с названием «Задание 5».* 

 ---

### Задание 6* со звёздочкой

Создайте UserParameter на bash и прикрепите его к созданному вами ранее шаблону. Он должен вызывать скрипт, который:
- при получении 1 будет возвращать ваши ФИО,
- при получении 2 будет возвращать текущую дату.

*Приложите в Git код скрипта, а также скриншот Latest data с результатом работы скрипта на bash, чтобы был виден результат работы скрипта при отправке в него 1 и 2.*

![image](https://user-images.githubusercontent.com/106932460/214124139-9ff69111-47a7-45b6-bbe8-f4740c39a11e.png)
![image](https://user-images.githubusercontent.com/106932460/214130313-ab264d0f-5d20-4ba9-8c3e-7e4cc957f9b2.png)

 ---

### Задание 7* со звёздочкой

Доработайте Python-скрипт из лекции, создайте для него UserParameter и прикрепите его к созданному вами ранее шаблону. 
Скрипт должен:
- при получении 1 возвращать ваши ФИО,
- при получении 2 возвращать текущую дату,
- делать всё, что делал скрипт из лекции.
`import sysimport osimport reif (sys.argv[1] == '-ping'): # Если -pingresult=os.popen("ping -c 1 " + sys.argv[2]).read() # Делаем пинг по заданному адресуresult=re.findall(r"time=(.*) ms", result) # Выдёргиваем из результата времяprint(result[0]) # Выводим результат в консольelif (sys.argv[1] == '-simple_print'): # Если simple_print print(sys.argv[2]) # Выводим в консоль содержимое sys.arvg[2]else: # Во всех остальных случаяхprint(f"unknown input: {sys.argv[1]}") Выводим непонятый запрос в консоль.`


*Приложите код скрипта в Git. Приложите в Git скриншот Latest data с результатом работы скрипта на Python, чтобы были видны результаты работы скрипта при отправке в него 1, 2, -ping, а также -simple_print.*
 
 ---

### Задание 8* со звёздочкой

Настройте автообнаружение и прикрепление к хостам созданного вами ранее шаблона.

*Приложите в Git скриншот правила обнаружения. Приложите в Git скриншот страницы Discover, где видны оба хоста.*

 ---

### Задание 9* со звёздочкой

Доработайте скрипты Vagrant для 2-х агентов, чтобы они были готовы к автообнаружению сервером, а также имели на борту разработанные вами ранее параметры пользователей.

*Приложите в Git файлы Vagrantfile и zabbix-agent.sh.*
