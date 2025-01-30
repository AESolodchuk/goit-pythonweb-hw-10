# Storing and Managing Contacts

## Setup Instructions

### 1. Install Dependencies

Run the following command to install all dependencies:

```shell
poetry install
```

### 2. Create .env File

Create a .env file in the project root directory and add the necessary credentials:

```
DB_URL=postgresql+asyncpg://<db_user>:<db_password>@localhost:5432/<db_name>
JWT_SECRET=<your_jwt_secret>
JWT_ALGORITHM=HS256
JWT_EXPIRATION_SECONDS=3600
MAIL_USERNAME=<your_mail_username>
MAIL_PASSWORD=<your_mail_password>
MAIL_FROM=<your_mail_from>
MAIL_FROM_NAME=<your_mail_from_name>
MAIL_PORT=<your_mail_port>
MAIL_SERVER=<your_mail_server>

# Cloudinary
CLD_NAME=<your_cloudinary_name>
CLD_API_KEY=<your_cloudinary_api_key>
CLD_API_SECRET=<your_cloudinary_api_secret>

```

Replace the placeholders (e.g., <db_user>, <db_password>, <db_name>, etc.) with your actual credentials.

### 3. Run Docker Container for PostgreSQL

Run the following command to start a PostgreSQL container:

```
docker run --name postgres-container -e POSTGRES_USER=YourUsername -e POSTGRES_PASSWORD=YourPassword -e POSTGRES_DB=contacts_app -p 5432:5432 -d postgres
```

### 4. Create Initial Migration

Run the following command to create the initial migration:

```
alembic revision --autogenerate -m "Initial migration"
```

### 5. Apply Initial Migration

Run the following command to apply the initial migration:

```
alembic upgrade head
```

### 6. Start the Application

Run the following command to start the FastAPI application:

```
python main.py
```

The application should now be running and accessible at http://localhost:8000.

Additional Information
To access the API documentation, navigate to http://localhost:8000/docs in your web browser.
Ensure Docker is installed and running on your machine before executing the Docker commands.
Make sure to replace placeholder values in the .env file with your actual credentials.
