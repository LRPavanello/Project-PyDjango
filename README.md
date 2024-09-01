# MMORPG Django Project

This is an initial project for an MMORPG developed with Django and PostgreSQL. The goal is to provide a basic structure for developing an MMORPG with Django, including database setup, superuser creation, and running the development server.

## Requirements

- [Python 3.12+](https://www.python.org/downloads/)
- [Django 5.x](https://www.djangoproject.com/)
- [PostgreSQL 15.x](https://www.postgresql.org/download/)
- [psycopg2](https://pypi.org/project/psycopg2/) (PostgreSQL driver for Python)

## Setup

1. **Clone the Repository**

   ```bash
   git clone <REPOSITORY_URL>
   cd <REPOSITORY_NAME>
   ```

2. **Create a Virtual Environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure PostgreSQL**

   - Create a database in PostgreSQL:
     ```sql
     CREATE DATABASE mydatabase;
     ```

   - Set the password for the `postgres` user:
     ```sql
     ALTER USER postgres WITH PASSWORD 'your_password';
     ```

5. **Update Django Settings**

   - Edit `settings.py` in your Django project to include the database settings:
     ```python
     DATABASES = {
         'default': {
             'ENGINE': 'django.db.backends.postgresql',
             'NAME': 'mydatabase',
             'USER': 'postgres',
             'PASSWORD': 'your_password',
             'HOST': 'localhost',
             'PORT': '5432',
         }
     }
     ```

6. **Apply Database Migrations**

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

7. **Create a Superuser**

   ```bash
   python manage.py createsuperuser
   ```

   Follow the prompts to set the username, email, and password for the superuser.

8. **Start the Development Server**

   ```bash
   python manage.py runserver
   ```

   The server will be available at `http://127.0.0.1:8000/`.

## Usage

- **Admin Interface**: Access the Django admin panel at `http://127.0.0.1:8000/admin/` to manage site content.

- **Development**: Add your features, models, and APIs as needed to build the MMORPG.

## Contributing

If you wish to contribute to this project, please open an issue or submit a pull request. Be sure to follow best practices and maintain code quality.

## License

This project is licensed under the [MIT License](LICENSE).