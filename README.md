# MusicaHub - Setup rápido (Ubuntu 22)


## Dependências


sudo apt update && sudo apt install -y python3-venv python3-pip build-essential libpq-dev nginx


## Criar ambiente


python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt


## Variáveis de ambiente (exemplo .env)


SECRET_KEY=uma_chave_aleatoria
DEBUG=1
ALLOWED_HOSTS=localhost,SEU_DOMINIO
DATABASE_URL=postgres://user:pass@localhost:5432/musichubdb
MERCADOPAGO_ACCESS_TOKEN=SEU_TOKEN
MERCADOPAGO_PUBLIC_KEY=SUA_CHAVE_PUBLICA


## Migrar e criar superuser


python manage.py migrate
python manage.py createsuperuser


## Rodar local


python manage.py runserver 0.0.0.0:8000


## Deploy


Usar Gunicorn + systemd + Nginx (exemplos no fim do README completo).