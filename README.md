# ENF — Django Online Store

A backend for a clothing online store built with **Django**. It models a product
catalog with categories, sizes with per-size stock, and product image galleries,
all manageable through the Django admin.

![Python](https://img.shields.io/badge/Python-3.12+-3776AB?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-6.0-092E20?logo=django&logoColor=white)
![SQLite](https://img.shields.io/badge/DB-SQLite-003B57?logo=sqlite&logoColor=white)

## Features

- **Categories** with auto-generated slugs
- **Products** with color, price, description, main image and timestamps
- **Sizes and stock**: each product has its own stock count per size
- **Image gallery**: any number of extra images per product
- **Admin panel**: products are edited together with their sizes and images inline

## Data model

```
Category 1 ──< Product 1 ──< ProductSize >── 1 Size
                       1 ──< ProductImage
```

## Getting started

```bash
# 1. Clone the repository
git clone https://github.com/marcsovnurislom/enf-project.git
cd enf-project

# 2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS / Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set up environment variables
copy .env.example .env       # Windows
# cp .env.example .env       # macOS / Linux
# then put a real SECRET_KEY into .env

# 5. Create the database and an admin user
python manage.py migrate
python manage.py createsuperuser

# 6. Run the development server
python manage.py runserver
```

Open http://127.0.0.1:8000/admin/ and sign in with the admin user you created.

## Project structure

```
enf-project/
├── enf/                # Project settings and root URL config
│   ├── settings.py
│   └── urls.py
├── main/               # Store app: models, admin, migrations
│   ├── models.py
│   ├── admin.py
│   └── migrations/
├── manage.py
├── requirements.txt
└── .env.example        # Template for environment variables
```

## Roadmap

- [ ] Public catalog pages (product list and product detail)
- [ ] Shopping cart and checkout
- [ ] Tests
