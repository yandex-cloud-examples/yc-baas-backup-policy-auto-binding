# Автоматическая привязка политики резервного копирования Yandex Cloud Backup к виртуальной машине Yandex Compute Cloud

В Yandex Cloud можно создать виртуальную машину на базе [поддерживаемого Cloud Backup образа](https://yandex.cloud/ru/docs/backup/concepts/vm-connection#os), к которой будет автоматически привязана [политика резервного копирования](https://yandex.cloud/ru/docs/backup/concepts/policy). Для этого нужно передать в [метаданных](https://yandex.cloud/ru/docs/compute/concepts/vm-metadata) скрипт для установки агента резервного копирования и идентификаторы нужных политик. Указанные политики автоматически привяжутся к ВМ после того, как ВМ и агент создадутся, инициализируются и запустятся.

Настройка описана в [практическом руководстве](https://yandex.cloud/ru/docs/backup/tutorials/vm-with-backup-policy). В репозитории хранятся конфигурационные файлы для развертывания инфраструктуры с помощью [Terraform](https://yandex.cloud/ru/docs/tutorials/infrastructure-management/terraform-quickstart):
* `backup-policy-auto-binding-config.tf` — манифест Terraform для создания облачной инфраструктуры.
* `cloud-init.yaml` — файл метаданных ВМ.