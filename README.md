# Comandos para Controle do Dispositivo

## 1. Comando de Reinício
- **Caracter de Comando:** `r`
- **Descrição:** Reinicia o dispositivo.
- **Exemplo de Payload JSON:**
  ```json
  {"cmd":"r"}
  ```

---

## 2. Comando para Listar Diretório
- **Caracter de Comando:** `l`
- **Payload Requerido:**
  - `dir`: O caminho do diretório a ser listado (o padrão é `"/"`).
- **Descrição:** Lista todos os arquivos no diretório especificado e publica os resultados.
- **Exemplo de Payload JSON:**
  ```json
  {"cmd":"l", "dir":"/some_directory"}
  ```

---

## 3. Comando para Obter Arquivo
- **Caracter de Comando:** `g`
- **Payload Requerido:**
  - `fn`: O nome do arquivo a ser recuperado.
- **Descrição:** Lê o arquivo especificado e publica seu conteúdo.
- **Exemplo de Payload JSON:**
  ```json
  {"cmd":"g", "fn":"example.txt"}
  ```

---

## 4. Comando para Anexar a um Arquivo
- **Caracter de Comando:** `a`
- **Payload Requerido:**
  - `fn`: O nome do arquivo ao qual anexar.
  - `content`: O conteúdo a anexar.
- **Descrição:** Anexa o conteúdo fornecido ao arquivo especificado.
- **Exemplo de Payload JSON:**
  ```json
  {"cmd":"a", "fn":"example.txt", "content":"Novo conteúdo a anexar."}
  ```

---

## 5. Comando para Deletar Arquivo
- **Caracter de Comando:** `d`
- **Payload Requerido:**
  - `fn`: O nome do arquivo a ser deletado.
- **Descrição:** Deleta o arquivo especificado e publica uma mensagem de sucesso ou falha.
- **Exemplo de Payload JSON:**
  ```json
  {"cmd":"d", "fn":"example.txt"}
  ```

---

## 6. Comando Desconhecido
- **Caracter de Comando:** (Qualquer caractere não reconhecido pelos comandos acima)
- **Descrição:** Publica "Comando desconhecido" no tópico especificado.
