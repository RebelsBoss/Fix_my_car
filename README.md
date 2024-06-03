# Fix My Car - Vertex AI Search

У цьому посібнику описано, як розгорнути додаток **Fix My Car** в **GKE**, використовуючи **Vertex AI Search** як сховище даних.

<img width="2098" alt="arch-vertex-ai-search" src="https://github.com/RebelsBoss/Fix_my_car/assets/126337643/ba691211-6e73-42cb-90c9-99dd9f5a5a36">

## Передумови

Щоб розгорнути цей додаток, вам знадобиться:

- Проект [Google Cloud](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project) з увімкненим білінгом.
- [Google Cloud SDK (gcloud)](https://cloud.google.com/sdk/docs/install), встановлений і налаштований у вашому локальному середовищі (або використовуйте [Google Cloud Shell](https://cloud.google.com/sdk/docs/interactive-gcloud)).
- [Docker Engine](https://docs.docker.com/engine/install/), АБО інструмент з відкритим вихідним кодом, такий як [Colima](https://github.com/abiosoft/colima), який може виконувати **docker build** та **docker push**.
- Java 18+, Maven 3.9.6+
- Python 3.9+

## Створіть Artifact Registry repository

Тут ви зберігатимете зображення контейнерів для фронту **Streamlit** та бекенду **Java**. [Контейнери](https://cloud.google.com/learn/what-are-containers) - це зібраний вихідний код і залежності, які можна розгортати в різних середовищах.

1. Відкрийте консоль **Google Cloud**. Відкрийте пошуковий рядок і введіть **"Artifact Registry"**. Відкрийте сторінку консолі **Artifact Registry**.
2. Натисніть **Create Repository**.
3. Назвіть ваш репозиторій **fixmycar**. Залиште **Docker** по дефолту. Виберіть будь-який регіон, наприклад **us-central1**. Натисніть кнопку **Create**.

## Build та push зображення контейнерів.

1. У консолі **Artifact Registry** виберіть ваш репозиторій, **fixmycar**. Потім натисніть **Setup Instructions**.
2. Скопіюйте команду автентифікації, наприклад

```
gcloud auth configure-docker us-central1-docker.pkg.dev
```

3. Відкрийте термінал або **Cloud Shell**. Вставте команду і запустіть її. Це дозволить автентифікувати ваш **Docker**-клієнт у вашому **Artifact Registry**.

```
{
  "credHelpers": {
    "us-central1-docker.pkg.dev": "gcloud"
  }
}
Adding credentials for: us-central1-docker.pkg.dev
```
