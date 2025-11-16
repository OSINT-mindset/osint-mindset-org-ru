# Как добавить контент на сайт

## Быстрый старт

### 1. Запустить локальный сервер

```bash
source .venv/bin/activate
mkdocs serve
```

Откройте http://127.0.0.1:8000/

### 2. Добавить новую страницу

#### Русская версия

1. Создайте файл в `docs/ru/`, например: `docs/ru/guides/my-guide.md`
2. Добавьте в `mkdocs.yml` в секцию `nav`:
   ```yaml
   - Руководства:
     - Мой гайд: guides/my-guide.md
   ```
3. Сохраните — сайт обновится автоматически

#### Английская версия

1. Создайте файл в `docs/en/` с тем же путём: `docs/en/guides/my-guide.md`
2. Переведите контент
3. Добавьте перевод названия в `mkdocs.yml` в секцию `nav_translations`:
   ```yaml
   Мой гайд: My Guide
   ```

### 3. Добавить изображение

1. Положите изображение в `docs/assets/`
2. Вставьте в markdown:
   ```markdown
   ![Описание](../assets/image.png)
   ```

## Структура файлов

```
docs/
├── ru/              # Русский контент
│   ├── README.md    # Главная страница
│   ├── community/   # Материалы сообщества
│   └── guides/      # Руководства
├── en/              # Английский контент
│   ├── README.md    # Главная страница
│   ├── community/   # Материалы сообщества
│   └── guides/      # Руководства
└── assets/          # Изображения (общие для всех языков)
```

## Markdown синтаксис

### Основы

```markdown
# Заголовок 1
## Заголовок 2
### Заголовок 3

**Жирный текст**
*Курсив*

- Список
- Элементов

1. Нумерованный
2. Список

[Ссылка](https://example.com)
![Изображение](../assets/image.png)
```

### Кнопки

```markdown
[Текст кнопки](https://example.com){ .md-button .md-button--primary }
```

### Предупреждения

```markdown
!!! note "Заголовок"
    Текст заметки

!!! warning "Внимание"
    Важная информация

!!! tip "Совет"
    Полезный совет
```

### Код

````markdown
```python
def hello():
    print("Hello, world!")
```
````

## Проверка перед коммитом

```bash
# Проверить сборку
mkdocs build --clean

# Убедиться, что нет ошибок
# Должно быть: INFO - Documentation built in X.XX seconds
```

## Полезные ссылки

- [Документация MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [Markdown Guide](https://www.markdownguide.org/)

