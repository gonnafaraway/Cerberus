# Cerberus

Мощный сканер уязвимостей, взлом поддоменов использует aioDNS, асинхронное быстрое сканирование asyncio, охватывающее все целевые активы для пакетного сканирования уязвимостей, сбор информации промежуточного программного обеспечения, автоматический сбор IP-прокси, автоматическое использование при обнаружении информации Waf для защиты машины Настоящий IP-адрес, после того, как локальный IP-адрес будет уничтожен Waf, IP-адрес прокси-сервера будет автоматически переключен на сканирование, сбор информации Waf (более 100 данных Waf дома и за рубежом), включая охранную собаку, облачную блокировку, Alibaba Cloud, Cloud Shield, Tencent Cloud и т. Д. Некоторые известные схемы обхода waf, обнаружение уязвимостей промежуточного программного обеспечения (Thinkphp, weblogic и другие CVE-2018-5955, CVE-2018-12613, CVE-2018-11759 и т. Д.), Поддерживают внедрение SQL, XSS, выполнение команд, включение файлов, уязвимость ssrf Сканирование, поддержка настраиваемой функции отправки электронной почты с уязвимостями.

[![asciicast](https://asciinema.org/a/289717.svg)](https://asciinema.org/a/289717)


## Основная функция

- :smiling_imp:Сканирование уязвимостей одного URL

  Поддержка SQL-инъекций, XSS, выполнения команд, включения файлов, ssrf

  Выполните сканирование уязвимостей одного сайта

  `python3 cerberus.py -target www.qq.com`
  
  [![asciicast](https://asciinema.org/a/6fOJu4DkVhMGutLeIGmwE7Ppi.svg)](https://asciinema.org/a/6fOJu4DkVhMGutLeIGmwE7Ppi)
  
- :cherry_blossom: Настройки детализации

  Многопоточный, по умолчанию 7 потоков
  
  `python3 cerberus.py -target www.qq.com -thread 7`


- :imp:Асинхронное пакетное сканирование поддоменов

  Используйте aioDNS, asyncio asynchronous, после взлома субдомена присоединитесь к очереди сканирования, чтобы охватить все целевые ресурсы для пакетного сканирования уязвимостей:
  `python3 cerberus.py -target www.qq.com -subdomain`
  
  [![asciicast](https://asciinema.org/a/n8zwz58eOkqH8JNZAi85opa61.svg)](https://asciinema.org/a/n8zwz58eOkqH8JNZAi85opa61)


- :skull: Сбор прокси IP

  Просканировал бесплатные IP-адреса прокси-серверов в реальном времени 9 сайтов, но выживаемость IP-адресов низкая, около 20%. Процесс проверки того, является ли IP-адрес живым, может заблокировать процесс сканирования.

  - www.data5u.com
  - www.xicidaili.com
  - www.goubanjia.com
  - www.ip3366.net
  - www.iphai.com
  - cn-proxy.com
  - ip.jiangxianli.com
  - www.xiladaili.com
  - ip.ihuan.me

  `python3 cerberus.py -target www.qq.com -proxy`
  
  [![asciicast](https://asciinema.org/a/p4A6ZhN5kCKIzlXZbdApltgNe.svg)](https://asciinema.org/a/p4A6ZhN5kCKIzlXZbdApltgNe)
  
- :japanese_ogre:Waf сбор сообщений

  Более 100 сведений о Waf внутри страны и за рубежом, мощная библиотека отпечатков пальцев, включая охранную собаку, облачный замок, Alibaba Cloud, Cloud Shield, Tencent Cloud и т.д. Предоставляют некоторые известные решения для обхода waf.
  
  Обязательно укажите URL-адрес с параметрами для тестирования WAF!
  
  `python3 cerberus.py -target https://open.weixin.qq.com/frame?t=home/web_tmpl&lang=zh_CN -waf`

- :see_no_evil:Сбор информации по промежуточного слоя

  После сбора информации автоматическое сканирование на наличие уязвимостей промежуточного ПО на основе полученных результатов.

  - WAF
  
  - CDN
  
  - CMS
  
  - Web Servers
  
  - Web Frameworks
  
  - Operating Systems
  
  `python3 cerberus.py -target -detectMid`
  
  [![asciicast](https://asciinema.org/a/mQ6qLc98J87Srpf7nGq8MakdP.svg)](https://asciinema.org/a/mQ6qLc98J87Srpf7nGq8MakdP)
  
- :panda_face: Укажите сканирование уязвимостей промежуточного ПО.

  Если целевая часть информации промежуточного программного обеспечения известна, вы можете указать тип и сканировать напрямую ->
  
  - Thinkphp CVE-2018-5955
  
  - Phpmyadmain CVE-2018-12613
  
  - Dedecms
  
  - Tomcat CVE-2018-11759
  
  - Weblogic
  
  - Wordpress
  
  `python3 cerberus.py -target www.qq.com -midlleware weblogic`
  
  
  
- :trollface: Пакетное сканирование входных файлов

  - Путь к файлу должен быть абсолютным.
  
  - Должен быть в формате txt, убедитесь, что в каждой строке указано только одно доменное имя.
  
  `python3 cerberus.py -file absolute path`

- :cookie: Настройка cookie
  
  `python3 cerberus.py -cookie cookie`

- :speak_no_evil: Вывод отчета о сканировании уязвимостей

  `python3 cerberus.py -outfile`
  
  

## :rabbit: Praise me!

   - :kissing_cat: Если вы думаете, что этот проект полезен для вас, для улучшения инструментов безопасности с открытым исходным кодом! Пожалуйста, оцените меня! Спасибо за благодарность!

   ![praise](https://github.com/YagamiiLight/Cerberus/blob/master/images/praise.jpg)

## Заявление

Этот проект предназначен только для обучения и общения, любые незаконные последствия, вызванные использованием этого инструмента, не имеют ко мне никакого отношения! 


  



  
  
  

