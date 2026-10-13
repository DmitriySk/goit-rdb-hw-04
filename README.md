# goit-rdb-hw-04 — DML, DDL і складні SQL-запити на Olist

## Датасет

- **Назва:** Olist Brazilian E-commerce Public Dataset (~100 тис. замовлень, 2016–2018).
- **Джерело:** Kaggle — https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Як отримати файли

Notebook сам знаходить дані:

1. якщо в репозиторії є папка `data/olist/` з CSV — бере файли звідти;
2. інакше завантажує датасет через `kagglehub.dataset_download('olistbr/brazilian-ecommerce')`
   (публічний датасет, у Colab завантажується без логіну в Kaggle).

## Використані таблиці

Використано весь датасет (без семплування):

| CSV | raw-таблиця | typed-таблиця | рядків |
|---|---|---|---|
| `olist_customers_dataset.csv` | `olist_customers_raw` | `olist_customers` | 99 441 |
| `olist_orders_dataset.csv` | `olist_orders_raw` | `olist_orders` | 99 441 |
| `olist_order_items_dataset.csv` | `olist_order_items_raw` | `olist_order_items` | 112 650 |
| `olist_products_dataset.csv` | `olist_products_raw` | `olist_products` | 32 951 |
| `olist_sellers_dataset.csv` | `olist_sellers_raw` | `olist_sellers` | 3 095 |
| `olist_order_reviews_dataset.csv` | `olist_order_reviews_raw` | `olist_order_reviews` | 99 224 |

Додаткові таблиці, створені в ДЗ: `seller_alerts`, `seller_score`, `olist_customer_dim`, `customer_segments`.

## Запуск

Відкрийте `dz_topic_4_Skalskyi.ipynb` у Google Colab і виконайте **Runtime → Restart and run all**.
Перша клітинка встановлює залежності (`pgserver psycopg2-binary sqlalchemy pandas kagglehub`),
друга запускає PostgreSQL через `pgserver` і виводить його версію.
