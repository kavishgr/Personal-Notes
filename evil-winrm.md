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

