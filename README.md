# Дампы Томска в wplace.live

## Ежедневные таймлапсы из этих дампов в этом [репозитории](https://github.com/niklinque/wplace-tomsk-timelapse/releases) и [телеграм-канале](https://t.me/wplacetomsktimelapse)

Этот проект автоматически загружает тайлы изображений Томска с сайта wplace.live каждые 5 минут и объединяет их в одну большую картинку.

## Файлы проекта

- `download_and_merge_tiles.py` - Скрипт для загрузки и объединения изображений
- `requirements.txt` - Зависимости Python
- `.github/workflows/download-tiles.yml` - GitHub Actions workflow для загрузки дампов
- `output/` - Директория с результатами

## Возможности

#### Загрузка дампов
- 🔄 **Загрузка 9 тайлов по ссылкам**
- 🖼️ **Объединение в одно изображение 9000x9000 с увеличенными пикселями**
- 🔀 **Автоматический commit изменений**

## Результаты

### Изображения (папка `output/YYYYMMDD`)
- `merged_tiles_YYYYMMDD_HHMMSS.png` - файл с временной меткой (9000x9000 пикселей)

## Настройка автоматизации

### Активация GitHub Actions
1. Форкните или клонируйте репозиторий
2. Убедитесь, что Actions включены в настройках репозитория

### Запуск workflow через cron-job.org
1. Создайте токен Github и дайте права: Actions → read and write и Workflows → read and write
2. Создайте cron-задание, выберите график выполнения
3. В URL вставьте `https://api.github.com/repos/USER/REPO/actions/workflows/download-tiles.yml/dispatches`
4. Во вкладке "Расширенное" заполните заголовки
   ```
   Authorization: token GITHUB_TOKEN
   Accept: application/vnd.github.v3+json
   ```
6. Сохраните настройку, теперь задача автоматизирована

## Ручной запуск
```bash
# Установка зависимостей
pip install -r requirements.txt

# Запуск скрипта загрузки дампов
python download_and_merge_tiles.py
```

## Требования

- Python 3.11+
- Библиотеки: `requests`, `Pillow`

![Cron job status](https://api.cron-job.org/jobs/6496329/5046fc7072d18798/status-7.svg)
