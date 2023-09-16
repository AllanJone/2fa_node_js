# Two-Factor Authentication with Node.js

This project is a simple implementation of two-factor authentication (2FA) in a Node.js application using OTP (One Time Password). The application uses Express.js as the web framework and Prisma as the ORM for interacting with the database.

## Features

- User Registration
- User Login
- Generate OTP
- Verify OTP
- Validate OTP
- Disable OTP

## Tech Stack

- Node.js
- Express.js
- Prisma
- PostgreSQL
- OTPAuth

## Installation

1. Clone the repository:

```sh
git clone https://github.com/AllanJone/2fa_node_js.git
cd 2fa_node_js
```

2. Install the dependencies:

```sh
npm install
```

3. Set up the database:

You need to have PostgreSQL installed on your machine or hosted in a cloud environment.
Update the `DATABASE_URL` in the `.env` file with your own PostgreSQL connection string.

Run the following command to apply the migrations and create the database schema:

```sh
npm run db:migrate
npm run db:push
```

4. Start the server:

```sh
npm start
```

The server will start on port 8000.

## API Endpoints

- `POST /api/auth/register`: Register a new user.
- `POST /api/auth/login`: Login a user.
- `POST /api/auth/generate-otp`: Generate OTP for a user.
- `POST /api/auth/verify-otp`: Verify the OTP of a user.
- `POST /api/auth/validate-otp`: Validate the OTP of a user.
- `POST /api/auth/disable-otp`: Disable the OTP of a user.

## Usage

### Register a User

To register a user, make a `POST` request to `/api/auth/register` with the following body:

```json
{
  "name": "John Doe",
  "email": "johndoe@gmail.com",
  "password": "password123"
}
```

### Login a User

To login a user, make a `POST` request to `/api/auth/login` with the following body:

```json
{
  "email": "johndoe@gmail.com",
  "password": "password123"
}
```

### Generate OTP

To generate an OTP for a user, make a `POST` request to `/api/auth/generate-otp` with the following body:

```json
{
  "user_id": "user_id"
}
```

### Verify OTP

To verify the OTP of a user, make a `POST` request to `/api/auth/verify-otp` with the following body:

```json
{
  "user_id": "user_id",
  "token": "123456"
}
```

### Validate OTP

To validate the OTP of a user, make a `POST` request to `/api/auth/validate-otp` with the following body:

```json
{
  "user_id": "user_id",
  "token": "123456"
}
```

### Disable OTP

To disable the OTP of a user, make a `POST` request to `/api/auth/disable-otp` with the following body:

```json
{
  "user_id": "user_id"
}
```
