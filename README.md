# 1. Клонируем репозиторий
git clone https://github.com/rasulow/task-management.git

cd task-management

# 2. Создаем и активируем виртуальное окружение
python -m venv env
source env/bin/activate  # Windows: env\Scripts\activate

# 3. Устанавливаем зависимости
pip install -r requirements.txt

# 4. Создаем .env файл
echo -e "DATABASE_URL=postgresql+asyncpg://user:password@localhost:5432/dbname

SECRET_KEY=your_secret_key" > .env

# 5. Применяем миграции
alembic upgrade head

# 6. Запускаем приложение
uvicorn app.main:app --reload
