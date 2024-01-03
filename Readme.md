# Invoice Management API

This Django project provides APIs for managing Invoices and Invoice Details using Django Rest Framework.

## Getting Started

### Prerequisites

- [Poetry](https://python-poetry.org/) for dependency management
- Python 3.x

### Installation

1. **Install Poetry (if not already installed):**

    ```bash
    curl -sSL https://install.python-poetry.org | python3 -
    ```

2. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/invoice-management-api.git
    cd invoice-management-api
    ```

3. **Install project dependencies:**

    ```bash
    poetry install
    ```

### Database Setup

1. **Apply migrations:**

    ```bash
    poetry run python manage.py makemigrations
    poetry run python manage.py migrate
    ```

2. **Create a superuser for the Django admin:**

    ```bash
    poetry run python manage.py createsuperuser
    ```

3. **Run the development server:**

    ```bash
    poetry run python manage.py runserver
    ```

4. **Open Postman or any API testing tool to interact with the APIs.**

## API Endpoints

### Invoices

#### 1. Create Invoice

- **Endpoint**: `POST /invoices/`
- **Payload**:

    ```json
    {
        "date": "2022-01-01",
        "customer_name": "Test Customer"
    }
    ```

- **Screenshot**:
    ![Create Invoice](screenshots/create_invoice.png)

#### 2. Get Invoices

- **Endpoint**: `GET /invoices/`
- **Screenshot**:
    ![Get Invoices](screenshots/get_invoices.png)

#### 3. Update Invoice

- **Endpoint**: `PUT /invoices/{invoice_id}/`
- **Payload**:

    ```json
    {
        "date": "2022-01-02",
        "customer_name": "Updated Customer"
    }
    ```

- **Screenshot**:
    ![Update Invoice](screenshots/update_invoice.png)

#### 4. Delete Invoice

- **Endpoint**: `DELETE /invoices/{invoice_id}/`
- **Screenshot**:
    ![Delete Invoice](screenshots/delete_invoice.png)

### Invoice Details

#### 5. Create Invoice Detail

- **Endpoint**: `POST /invoice-details/`
- **Payload**:

    ```json
    {
        "invoice": 1,  # Replace with the actual Invoice ID
        "description": "Test Item",
        "quantity": 2,
        "unit_price": 10.00,
        "price": 20.00
    }
    ```

- **Screenshot**:
    ![Create Invoice Detail](screenshots/create_invoice_detail.png)

#### 6. Get Invoice Details

- **Endpoint**: `GET /invoice-details/`
- **Screenshot**:
    ![Get Invoice Details](screenshots/get_invoice_details.png)

#### 7. Update Invoice Detail

- **Endpoint**: `PUT /invoice-details/{detail_id}/`
- **Payload**:

    ```json
    {
        "description": "Updated Item",
        "quantity": 3,
        "unit_price": 12.00,
        "price": 36.00
    }
    ```

- **Screenshot**:
    ![Update Invoice Detail](screenshots/update_invoice_detail.png)

#### 8. Delete Invoice Detail

- **Endpoint**: `DELETE /invoice-details/{detail_id}/`
- **Screenshot**:
    ![Delete Invoice Detail](screenshots/delete_invoice_detail.png)

## Running Tests

Run the tests using the following command:

```bash
poetry run python manage.py test
