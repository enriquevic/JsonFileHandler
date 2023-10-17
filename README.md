# Classe JsonFileHandler

Uma classe Java projetada para lidar com arquivos JSON. Esta classe fornece métodos para criar, verificar e manipular arquivos JSON, com foco em criar uma abordagem estruturada para lidar com dados JSON.

#### Uso Básico

A seguir, um exemplo de como utilizar a classe `JsonFileHandler`:

```java
public class ExemploDeUso {

    public static void main(String[] args) {
        // Defina o diretório e nome do arquivo JSON
        String directory = "src/bd/";
        String jsonName = "0";

        // Defina os nomes dos objetos e as informações associadas
        String[][] objectNames = {{"access", "Colors"}};
        String[][] informations = {{"firstAccess:0", "Defaut:ffffff"}};

        // Instancie a classe JsonFileHandler
        JsonFileHandler jsonHandler = new JsonFileHandler();

        // Crie o arquivo JSON e insira os dados, se ainda não existir
        jsonHandler.createJsonFile(directory, jsonName, objectNames, informations);

        // Verifique se os dados correspondem ao conteúdo atual do arquivo
        boolean contentMatches = jsonHandler.checkContentJsonFile(directory, jsonName, objectNames, informations);

        if (contentMatches) {
            System.out.println("Os dados no arquivo correspondem às expectativas.");
        } else {
            System.out.println("Os dados no arquivo não correspondem às expectativas.");
        }
    }
}
```
## Métodos

### `createJsonFile`

- **Descrição:** Cria um novo arquivo JSON ou verifica a existência de um já criado. Se o arquivo não existir, inicializa o arquivo e adiciona as informações especificadas.
  
- **Parâmetros:**
  - `directory`: O diretório onde o arquivo JSON será criado.
  - `jsonName`: O nome do arquivo JSON (sem a extensão do arquivo).
  - `objectNames`: Uma matriz especificando os nomes dos objetos a serem criados no arquivo JSON.
  - `informations`: Uma matriz contendo informações a serem adicionadas ao arquivo JSON.

### `checkJsonFile`

- **Descrição:** Verifica se um arquivo JSON existe no diretório especificado.
  
- **Parâmetros:**
  - `directory`: O diretório onde o arquivo JSON será verificado.
  - `jsonName`: O nome do arquivo JSON (sem a extensão do arquivo).
  
- **Retorna:** `true` se o arquivo existir, `false` caso contrário.

### `inputObjects`

- **Descrição:** Lê objetos, verifica o conteúdo do arquivo JSON existente e adiciona novas informações, se necessário.
  
- **Parâmetros:**
  - `directory`: O diretório onde o arquivo JSON está localizado.
  - `jsonName`: O nome do arquivo JSON (sem a extensão do arquivo).
  - `objectNames`: Uma matriz especificando os nomes dos objetos a serem criados no arquivo JSON.
  - `informations`: Uma matriz contendo informações a serem adicionadas ao arquivo JSON.

### `checkContentJsonFile`

- **Descrição:** Verifica se o conteúdo do arquivo JSON corresponde aos nomes de objetos e informações fornecidos.
  
- **Parâmetros:**
  - `directory`: O diretório onde o arquivo JSON está localizado.
  - `jsonName`: O nome do arquivo JSON (sem a extensão do arquivo).
  - `objectNames`: Uma matriz especificando os nomes dos objetos a serem verificados.
  - `informations`: Uma matriz contendo informações a serem verificadas no arquivo JSON.

- **Retorna:** `true` se o conteúdo corresponder, `false` caso contrário.

### `checkDataMatch`

- **Descrição:** Verifica se os dados no arquivo JSON correspondem aos nomes de objetos e informações especificados.
  
- **Parâmetros:**
  - `jsonObject`: O JsonObject a ser verificado.
  - `objectNames`: Uma matriz especificando os nomes dos objetos a serem verificados.
  - `informations`: Uma matriz contendo informações a serem verificadas no arquivo JSON.

- **Retorna:** `true` se os dados corresponderem, `false` caso contrário.
