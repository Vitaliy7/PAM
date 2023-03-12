# Пользователи и группы. Авторизация и аутентификация

## Домашнее задание по теме _Пользователи и группы. Авторизация и аутентификация_
> Запретить всем пользователям, кроме группы admin логин в выходные (суббота и воскресенье), без учета праздников

### Решение ДЗ

Решение полностью автоматическое. При помощи _Vagrantfile_ и _Ansible_ разворачиваем виртуальную машину и пробуем залогиниться 
> ssh otus@192.168.57.10  

Если это происходит в выходной день, то терминал откажет в соединении: 

![](https://github.com/Vitaliy7/PAM/blob/main/Error.png?raw=true)

При этом пользователь _otusadm_ может законнектиться:

![](https://github.com/Vitaliy7/PAM/blob/main/Accept.png?raw=true)

При попытке первого входа выходит ошибка идентификации удаленного хоста:

![](https://github.com/Vitaliy7/PAM/blob/main/Error2.png?raw=true)

В таком случае удаляем текущий ключ _ssh_ командой  
 > ssh-keygen -f "/home/your_directory/.ssh/known_hosts" -R "192.168.57.10"
