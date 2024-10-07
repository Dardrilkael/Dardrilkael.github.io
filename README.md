
# Comandos para Controle do Dispositivo

### 1. Comando de Reinício
- **Caracter de Comando:** r
- **Descrição:** Reinicia o dispositivo.
- **Exemplo de Payload JSON:**
```json
{
  "cmd": "r"
}
```
- **Tópico para Envio:** `sys//prefeituras/macae/estacoes/<station_name>`

### 2. Comando para Listar Diretório
- **Caracter de Comando:** l
- **Payload Requerido:**
  - `dir`: O caminho do diretório a ser listado (o padrão é "/").
- **Descrição:** Lista todos os arquivos no diretório especificado e publica os resultados.
- **Exemplo de Payload JSON:**
```json
{
  "cmd": "l",
  "dir": "/"
}
```
- **Tópico para Envio:** `sys//prefeituras/macae/estacoes/<station_name>`

### 3. Comando para Obter Arquivo
- **Caracter de Comando:** g
- **Payload Requerido:**
  - `fn`: O nome do arquivo a ser recuperado (deve incluir uma / no início, como "/exemplo.txt").
- **Descrição:** Lê o arquivo especificado e publica seu conteúdo.
- **Exemplo de Payload JSON:**
```json
{
  "cmd": "g",
  "fn": "/exemplo.txt"
}
```
- **Tópico para Envio:** `sys//prefeituras/macae/estacoes/<station_name>`

### 4. Comando para Anexar a um Arquivo
- **Caracter de Comando:** a
- **Payload Requerido:**
  - `fn`: O nome do arquivo ao qual anexar (deve incluir uma / no início).
  - `content`: O conteúdo a anexar.
- **Descrição:** Anexa o conteúdo fornecido ao arquivo especificado.
- **Exemplo de Payload JSON:**
```json
{
  "cmd": "a",
  "fn": "/exemplo.txt",
  "content": "Novo conteúdo a anexar."
}
```
- **Tópico para Envio:** `sys//prefeituras/macae/estacoes/<station_name>`

### 5. Comando para Deletar Arquivo
- **Caracter de Comando:** d
- **Payload Requerido:**
  - `fn`: O nome do arquivo a ser deletado (deve incluir uma / no início).
- **Descrição:** Deleta o arquivo especificado e publica uma mensagem de sucesso ou falha.
- **Exemplo de Payload JSON:**
```json
{
  "cmd": "d",
  "fn": "/exemplo.txt"
}
```
- **Tópico para Envio:** `sys//prefeituras/macae/estacoes/<station_name>`

### 6. Comando OTA (Atualização de Firmware)
- **Caracter de Comando:** u
- **Payload Requerido:**
  - `url`: URL do novo firmware.
  - `id`: Identificador do comando.
- **Descrição:** Envia um comando para atualizar o firmware.
- **Exemplo de Payload JSON:**
```json
{
  "cmd": "update",
  "url": "http://update.gpicm-ufrj.tec.br:18000/uploads/index.ino.bin",
  "id": "1"
}
```
- **Tópico para Envio:** `sys//prefeituras/macae/estacoes/<station_name>`

### 7. Comando Desconhecido
- **Caracter de Comando:** (Qualquer caractere não reconhecido pelos comandos acima)
- **Descrição:** Publica "Comando desconhecido" no tópico `sys//prefeituras/macae/estacoes/<station_name>`.

### Tópicos de Resposta do Dispositivo:
- **Handshake ao Ligar:** `sys-report//prefeituras/macae/estacoes/<station_name>/handshake`
- **Status do OTA:** `sys-report//prefeituras/macae/estacoes/<station_name>/OTA`
- **Leitura de Arquivos e Diretórios:** `sys-report//prefeituras/macae/estacoes/<station_name>`
