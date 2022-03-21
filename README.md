# Installation:
```
pip install PyMailGw
```

# Usage Example:
```py
from PyMailGw import MailGwApi
import time

api = MailGwApi(proxy='http://127.0.0.1:8080', timeout=30)

email = api.get_mail()
print(f'Your temp-mail: {email}')

while True:
    time.sleep(5)
    for mail in api.fetch_inbox():
        content = api.get_message_content(mail['id'])
        print(f'Message from: {mail["from"]["address"]}\n{content}')
```
