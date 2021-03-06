# devops-win

## Подготовка:

1. Для развертывания инфраструктуры в main.tf в провайдере aws заполнить значения для параметров access_key, secret_key, в модуле ec2 заполнить значение для параметра key_name. В файле module/ec2/variables заполнить значение для переменной key_name.
2. Для управление конфигурации инстансов необходимо скопировать приватный ключ в ansible/files/.ssh/id_rsa

 ## Запуск проекта:
1. Для запуска проекта зайти в terraform/, запустить последовательно: terraform init, terraform plan, terraform apply
2. Для получения публичного ip адреса выполнить: terraform show | grep public_ip
3. Добавить в ansible/inventory.yml полученный ip адрес для запуска playbook
4. Запустить выполнение: ansible_playbook -i ansible/inventory.yml playbook_ii_docker.yml   

## Результат:
Необходимо подготовить код, который запускает веб сервер и доступна страница вида: <DevOps Course 2021>. Веб сервер должен быть запущен в инфраструктуре AWS в новой VPC. 
Конфигурирование веб сервера должно быть с помощью Ansible. Сам веб сервер необходимо запустить в docker контейнере. Код выложить в репозиторий Github. В репозитории должны быть добавлены автоматические проверки `ansible lint` и `terraform validate`. Все изменения могут происходить только через отдельную ветку. Код должен содержать все best practices которые были пройдены в течении курса.
