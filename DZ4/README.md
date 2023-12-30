# CI/CD. Семинар 04. Troubleshooting (диагностика и решение проблем в CI/CD)

## Задача
Сделать локальный шаблон CI и отдельный репозиторий с шаблонами, подключить их к своему основному репозиторию через include




## Решение
Создан локальный файл `local-smoke-tests.gitlab-ci.yml`

```yaml
smoke-test-job:
  script: echo "SMOKE"
```

Создан основной файл `.gitlab-ci.yml`

```yaml
include:
  - local: local-smoke-tests.gitlab-ci.yml
  - remote: https://github.com/Valinetsky/-CI-CD_Seminar04/blob/main/remote-included-file.yml
```

Repository Seminar04
![repository](img/VirtualBox_cibox_04_12_2023_19_02_47.png "repository")

Remote included file job
![remote included file job](img/VirtualBox_cibox_04_12_2023_19_10_01.png "remote included file job")

Pipeline passed
![pipeline passed](img/VirtualBox_cibox_04_12_2023_19_10_34.png "pipeline passed")