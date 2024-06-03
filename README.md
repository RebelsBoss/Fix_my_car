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
