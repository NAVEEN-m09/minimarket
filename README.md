# MiniMarket

MiniMarket is a Django-based mini e-commerce project for browsing vegetables and grocery items, creating user accounts, logging in, adding products to a cart, and placing simple orders.

## Features

- User registration and login flow
- Session-based authentication
- Product listing pages for vegetables and grocery items
- Add-to-cart flow and cart summary page
- Single-item and cart checkout screens
- Admin-ready Django project structure with app-level separation

## Project Structure

- `MiniMarket/` - project settings, root URLs, middleware
- `users/` - user registration, login, cart, checkout flows
- `marketAdmin/` - product models and list views for vegetables and grocery
- `core/` - shared base templates/assets scaffolding
- `templates/` - root-level templates
- `static/` and `media/` - static assets and uploaded images
- `frontend/` and `React/` - frontend experiments/assets included in the repo

## Tech Stack

- Python
- Django
- MySQL
- HTML templates
- Bootstrap-style form classes in templates/forms

## Main Routes

- `/` - home page
- `/user/createaccount/` - create account
- `/user/login/` - login
- `/user/show/mycart/` - view cart
- `/market/vegs/` - vegetables listing
- `/market/groc/` - grocery listing

## Data Models

### `users`

- `Users` - stores name, password, mobile, email, address
- `cart` - stores user, item name, and item price

### `marketAdmin`

- `vegitables` - vegetable catalog entries
- `grocrey` - grocery catalog entries

## Setup

1. Clone the repository.
2. Create and activate a virtual environment.
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Update the database configuration in `MiniMarket/settings.py`.
5. Run migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

6. Start the development server:

```bash
python manage.py runserver
```

## Database Configuration

The project is currently configured to use MySQL in `MiniMarket/settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'minimarket',
        'USER': 'root',
        'PASSWORD': 'password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

Make sure:

- MySQL is installed and running
- A database named `minimarket` exists
- The configured username and password are correct

If those credentials are not valid, `python manage.py migrate` will fail with a database access error.

## Current Notes

- `makemigrations` currently reports `No changes detected`
- `migrate` depends on valid MySQL credentials
- A `db.sqlite3` file is present in the repo, but the active settings are pointed at MySQL
- Some model and class names use the original project naming, such as `vegitables` and `grocrey`

## Possible Improvements

- Move sensitive settings like database credentials into environment variables
- Use Django's built-in `User` model or a custom auth model instead of storing plain-text passwords
- Clean up naming and spelling for models, forms, and routes
- Add tests for auth, cart, and checkout flows
- Trim unused packages from `requirements.txt`

## License

This project does not currently include a license file.
