## ⚙️ Памятка по настройке VS Code и виртуального окружения

### 1. Установка и подготовка среды

* Скачайте и установите **[Visual Studio Code](https://code.visualstudio.com/)**.
* На **Windows** используйте **Git Bash** как терминал (идёт вместе с [Git](https://git-scm.com/downloads)).
* На **macOS** Bash установлен по умолчанию.

### 2. Проверка и установка Python

* Проверьте, установлен ли Python:

  ```bash
  which python
  python --version
  ```
* Если Python не установлен — скачайте с [python.org/downloads](https://www.python.org/downloads/).

> 💡 Рекомендуемая версия: **Python 3.10+**

### 3. Настройка VS Code

* Установите расширения:

  * **Python** (Microsoft)
  * **Jupyter** (для `.ipynb` файлов)
  * **Russian Language Pack for VS Code** (русификатор)
* Откройте терминал прямо в VS Code:
  `Terminal → New Terminal` (или **Ctrl + `**).

### 4. Создание виртуального окружения

> Зачем это нужно?
> Чтобы библиотеки разных проектов не конфликтовали между собой.

```bash
python -m venv _название_ (env)
```

После создания структура:

* **Windows:** `env/Scripts/`
* **macOS/Linux:** `env/bin/`

### 5. Активация виртуального окружения

* **Windows:**

  ```bash
  source env/Scripts/activate
  ```
* **macOS/Linux:**

  ```bash
  source env/bin/activate
  ```

> После активации в начале строки терминала появится `(env)`.

### 6. Выбор интерпретатора в VS Code

* Нажмите **Ctrl + Shift + P → “Python: Select Interpreter”**
* Выберите интерпретатор внутри вашего окружения (`env`).

### 7. Проверка корректности

```bash
which python
python --version
```

Если путь указывает на `env/...` — всё настроено правильно.

---

## 💡 Частые ошибки и как их исправить

| Проблема                                                | Причина                                    | Решение                                                                                                |
| ------------------------------------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| ❌ `python` не распознаётся в терминале                  | Python не добавлен в PATH                  | При установке Python отметьте “Add Python to PATH” или переустановите с этой опцией                    |
| ❌ Терминал VS Code открывает PowerShell (а не Git Bash) | VS Code по умолчанию использует PowerShell | В VS Code: **Ctrl + Shift + P → Terminal: Select Default Profile → Git Bash**                          |
| ❌ Окружение не активируется                             | Команда для другой ОС                      | Проверьте, используете ли `env\Scripts\activate` (Windows) или `source env/bin/activate` (macOS/Linux) |
| ❌ Библиотеки не видны                                   | Установлены в глобальную среду             | Убедитесь, что активировано окружение перед `pip install`                                              |
| ⚠️ Несовпадает версия Python                            | Разные версии установлены в системе        | Проверьте путь: `which python` или используйте `python3` при создании окружения                        |


