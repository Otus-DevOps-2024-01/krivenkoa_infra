# krivenkoa_infra
# Homework 3

### Подключение к someinternalhost в одну команду
bastion_IP = 89.169.140.102
someinternalhost_IP = 10.128.0.3
```
ssh -J appuser@<bastion_IP> appuser@<someinternalhost_IP>
```

### Настройка SSH для доступа по алиасу хоста
Добавить настройки в "~/.ssh/config"
```
Host bastion
  HostName <bastion_IP>
  User appuser
  Port 22
Host someinternalhost
  HostName <someinternalhost_IP>
  User appuser
  Port 22
  proxyjump bastion
```

Проверка подключения

```
ssh bastion
ssh someinternalhost
```
