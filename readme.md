# Заготовка проекта UMI.CMS

Заготовка проекта для разработки на UMI.CMS с использованием `Vagrant`

## Зависимости

* VirtualBox <http://www.virtualbox.com>
* Vagrant <http://www.vagrantup.com>, вместе с плагинами:
 * Автоматическая настройка локального домена [vagrant-hostmanager](https://github.com/smdahlen/vagrant-hostmanager) `vagrant plugin install vagrant-hostmanager`
 * Ускорение повторного создания ВМ (кэширование устанавливаемых пакетов) [vagrant-cachier](https://github.com/fgrehm/vagrant-cachier) `vagrant plugin install vagrant-cachier`

## Использование

    $ git clone https://github.com/ilyar/umi-project-stub.git project
    $ cd project
    $ vagrant up

Для установки UMI.CMS открыть в браузере `http://project.local/install.php` и следуйте инструкциям.

Дополнительные комманды для управления виртуальной машиной:

    $ vagrant suspend # пауза
    $ vagrant halt # остановить
    $ vagrant destroy -f # удалить

## Начальные значения

### UMI.CMS

База данных

    host: localhost
    user: umi
    password: umi
    dbname: umi

Супервайзер

    login: umiuser
    password: umipass

### MySQL

    host: localhost или project.local
    username: root
    password: local

phpMyAdmin <http://project.local/phpmyadmin/>

### Xdebug

    IDE key = vagrant

### Настройки окружения `Vagrantfile`

```bash
custom_vm_os         = false # default 'trusty' - проверено, 'precise' - не поддерживается, а точнее HP 5.3.*
custom_project_name  = false # default from project name folder
custom_project_host  = false # default `project_name.local`
custom_project_alias = false # default `www.project_name.local`
custom_ip_address    = false # default "10.10.10.10" IPv4 private network range
custom_vm_arch       = false # default 32  or VM_ARCH
custom_vm_memory     = false # default 512 or VM_MEMORY
custom_vm_cores      = false # default 1   or VM_CORES
```
