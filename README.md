# WGforge2019
## Virtualization

#### Установка для Linux и macOS
* Устанавливаем [VirtualBox](https://www.virtualbox.org/)
* Устанавливаем [Vagrant](https://www.vagrantup.com/)

#### Установка для Windows 10
* Устанавливаем [WSL (Windows Subsystem for Linux)](https://docs.microsoft.com/en-us/windows/wsl/wsl2-install) с ОС Ubuntu
* Затем внутри WSL, устанавливаем [Vagrant](https://www.vagrantup.com/)

#### Запуск виртуальной машины.
* Клонируем репозиторий и переходим в каталог с репозиторием. \
* `git clone https://github.com/roman-kozin/wgforge2019_virtualization.git`
* `~$ cd ~/wgforge2019_virtualization/`
* `~$ vagrant up`

*Ждем пока создастся vm и накатится конфигурация через ansible.* \
*После старта vm, на localhost хостовой машины будут проброшены tcp порты 80(http), 443(https), 5900(vnc)*

#### Краткая справка коммнд (подробнее на оф. сайте [Vagrant](https://www.vagrantup.com/docs/cli/))
* Зайти в vm по ssh - `~$ vagrant ssh`
* Посмотреть статус vm - `~$ vagrant status`
* Выключить vm - `~$ vagrant halt`
* Удалить vm - `~$ vagrant destroy`

Примеры команд для тестирования запуска и управления vm и контейнерами внутри данной VM (сори за тафтологию), лежат файлах commands.txt, в каталоге `~/examples/(docker|kvm|lxc)`


```
~$ tree examples -P commands.txt
examples
├── docker
│   ├── commands.txt
│   └── conf
├── kvm
│   └── commands.txt
└── lxc
    └── commands.txt
```
