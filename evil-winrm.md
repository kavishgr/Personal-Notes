---
description: To get a windows shell
---

# evil-winrm

{% embed url="https://github.com/Hackplayers/evil-winrm" %}

```text
git clone https://github.com/Hackplayers/evil-winrm
```

```text
cd evil-winrm

for i in $(cat Gemfile | tail -4 | cut -d ' ' -f 2 | tr -d "'"); do gem install $i; done; echo -e "\n\n\nDONE"
```

With the right credentials, run the following to get a shell\(**putting password inside quotes because of special characters**\):

```text
ruby evil-rm.rb -u chase -p 'Q4)sJu\Y8qz*A3?d' -i 10.10.10.149
```

Full output:

![evil-winrm shell](.gitbook/assets/evilwinrm%20%281%29.png)



