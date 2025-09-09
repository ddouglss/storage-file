
# 🗂 File Storage API

Uma API REST em Spring Boot para upload, download e listagem de arquivos, permitindo armazenamento simples de arquivos em uma pasta configurável no servidor.


## 🛠 Tecnologias utilizadas

- **Java 17+**
- **Back-end:** 
- **Spring Boot 3.x**
- **Spring Web MVC**
- **Spring Configuration Properties**
- **Jakarta Servlet**
- **Maven**
- **IDE: IntelliJ IDEA**
- **Postman (para testes)**


## Funcionalidades

**Upload de arquivos**

- Endpoint: ```POST /v1/files/upload```

- Permite enviar arquivos via ``` multipart/form-data.```

- Retorna um link para download do arquivo enviado.

**Download de arquivos**

- Endpoint: ```GET /v1/files/download/{fileName}```

- Permite baixar arquivos armazenados na pasta configurada.

- O arquivo é baixado com o mesmo nome enviado no upload.

**Listagem de arquivos**

Endpoint: ```GET /v1/files/list```

- Retorna uma lista de todos os arquivos disponíveis na pasta de armazenamento.

## ⚙ Configuração

No arquivo ```application.properties```:

```properties
  # Caminho da pasta de armazenamento dos arquivos
file.upload-dir=C:/Users/Douglas/Documents/file-storage/tmp
```
    
## 📦 Estrutura do Projeto
``` bash
src
 └─ main
     ├─ java
     │   └─ br.com.filestorage
     │       ├─ controller
     │       │    └─ FileStorageController.java
     │       └─ model
     │            └─ FileStorageProperties.java
     └─ resources
         └─ application.properties

```
## ⚠️ Observações

- A API retorna 404 se o arquivo não existir.

- Todos os arquivos são armazenados localmente, atenção ao espaço em disco e permissões.

- Para produção, recomenda-se integração com armazenamento em nuvem (AWS S3, GCP Storage, Azure Blob).
