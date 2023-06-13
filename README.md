## Тиждень 8

### Задача 2

1. Отримаємо інфраструктурний код для розгортання за допомогою **terraform**:

  ```bash
  git clone --branch tf_gke_flux_sops --single-branch https://github.com/NickP007/les07.git tf_sops
  cd tf_sops
  ```

2. Імпортуємо персональний токен GitHub

  ```bash
  export TF_VAR_GITHUB_OWNER=${YOUR_GITHUB_ACCOUNT}
  export TF_VAR_GITHUB_TOKEN=${YOUR_GITHUB_ACCESS_TOKEN}
  ```

3. Створемо Google Storage Bucket `tf-gke-demo`

4. Розгорнемо Kubernetes Cluster з встановленою системою **flux** за допомогою **terraform**:

  ```bash
  terraform init
  terraform apply
  ```
