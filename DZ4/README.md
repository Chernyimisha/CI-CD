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
  - remote: https://raw.github.com/Chernyimisha/CI-CD/main/DZ4/remote_included-file.yml
```

Repository Seminar04
![repository](img/2023-12-30_16-26-05.png "repository")

Remote included file job
![remote included file job](img/2023-12-30_16-58-39.png "remote included file job")

Pipeline passed
![pipeline passed](img/2023-12-30_16-59-04.png "pipeline passed")