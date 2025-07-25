### Summary

A Stored Cross-Site Scripting (XSS) vulnerability was identified in the `agenda.php ` endpoint of the I-educar application 2.8,2.9 and 2.10. This vulnerability allows attackers to inject malicious scripts into the `agenda_rap_conteudo` and `agenda_rap_titulo` parameters. The injected scripts are stored on the server and executed automatically whenever the affected page is accessed by users, posing a significant security risk.

### Details

Vulnerable Endpoint: `agenda.php`
Parameters: agenda_rap_conteudo and agenda_rap_titulo

The application fails to properly validate and sanitize user inputs in the `agenda_rap_conteudo` and `agenda_rap_titulo parameters`. This lack of validation allows attackers to inject malicious scripts, which are then stored on the server. Whenever the affected page is accessed, the malicious payload is executed in the victim's browser, potentially compromising the user's data and system.

### PoC

Payload = `"><img src=x onerror=alert('XSS-CVE-Hunters')>`
endpoint: `agenda_rap_titulo`
![image](/images/xss013.png)

Payload = `"><img src=x onerror=alert('XSS-CVE-Hunters2')>`
endpoint: `agenda_rap_titulo`

![image](/images/xss014.png)


### Impact

- Stealing session cookies: Attackers can use stolen session cookies to hijack a user's session and perform actions on their behalf.
- Downloading malware: Attackers can trick users into downloading and installing malware on their computers.
- Hijacking browsers: Attackers can hijack a user's browser or deliver browser-based exploits.
- Stealing credentials: Attackers can steal a user's credentials.
- Obtaining sensitive information: Attackers can obtain sensitive information stored in a user's account or in their browser.
- Defacing websites: Attackers can deface a website by altering its content.
- Misdirecting users: Attackers can change the instructions given to users who visit the target website, misdirecting their behavior.
- Damaging a business's reputation: Attackers can damage a business's image or spread misinformation by defacing a corporate website.

# Discoverer

[Natan Maia Morette](https://nmmorette.github.io) 

by [CVE-Hunters](https://github.com/Sec-Dojo-Cyber-House/cve-hunters)

