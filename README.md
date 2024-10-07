# Commands for Device Control

## 1. Restart Command
- **Command Character:** `r`
- **Description:** Restarts the device.
- **JSON Payload Example:**
  ```json
  {"cmd":"r"}
  ```

---

## 2. List Directory Command
- **Command Character:** `l`
- **Required Payload:**
  - `dir`: The directory path to list (default is `"/"`).
- **Description:** Lists all files in the specified directory and publishes the results.
- **JSON Payload Example:**
  ```json
  {"cmd":"l", "dir":"/some_directory"}
  ```

---

## 3. Get File Command
- **Command Character:** `g`
- **Required Payload:**
  - `fn`: The filename to retrieve.
- **Description:** Reads the specified file and publishes its content.
- **JSON Payload Example:**
  ```json
  {"cmd":"g", "fn":"example.txt"}
  ```

---

## 4. Append to File Command
- **Command Character:** `a`
- **Required Payload:**
  - `fn`: The filename to append to.
  - `content`: The content to append.
- **Description:** Appends the provided content to the specified file.
- **JSON Payload Example:**
  ```json
  {"cmd":"a", "fn":"example.txt", "content":"New content to append."}
  ```

---

## 5. Delete File Command
- **Command Character:** `d`
- **Required Payload:**
  - `fn`: The filename to delete.
- **Description:** Deletes the specified file and publishes a success or failure message.
- **JSON Payload Example:**
  ```json
  {"cmd":"d", "fn":"example.txt"}
  ```

---

## 6. Unknown Command
- **Command Character:** (Any character not recognized by the above commands)
- **Description:** Publishes "Unknown command" to the specified topic.

---
