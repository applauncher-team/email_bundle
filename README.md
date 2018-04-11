# Email bundle for AppLauncher
Email support for applauncher. This is a wrapper of the python standard library so there not any dependecies

Installation
-----------
```bash
pip install email_bundle 
```
Then add to your main.py
```python
import email_bundle

bundle_list = [
    email_bundle.EmailBundle(),
]
```

Configuration
-------------
```yml
email:
   username: myuser
   password: mypass
   smtp_host: localhost
   smtp_port: 1025
   use_ttls: True
   use_authentication: True
```

Sending an email
-----------------
Create a file for your tasks, for example "tasks.py" (you can create any files you want always you register it later)

```python
import inject
from email_bundle import EmailSender
es = inject.instance(EmailSender)
# Sending a simple text email
es.send_email("My subject","maxpowel@gmail.com", "email_receiver@email.com", "Hi man!")

# Sending a html email
es.send_email("My subject", "maxpowel@gmail.com", "receiver@gmail.com", "<strong>This is my html message!!</strong>", mime="html")

```
