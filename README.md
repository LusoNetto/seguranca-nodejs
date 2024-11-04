
# Supermarket Inventory API

## Overview
The Supermarket Inventory API is a robust and scalable solution designed for managing supermarket inventory efficiently. This project includes comprehensive CRUD functionalities, user authentication, user roles, and permissions management. It leverages Node.js and Sequelize ORM for a seamless integration with SQL-based databases, ensuring reliable data handling and flexible development.

## Project Structure
The project is organized into various folders that support modular development, making it easier to maintain and extend:

```
│   .gitignore
│   .sequelizerc
│   package-lock.json
│   package.json
│
└───api
    │   index.js
    │
    ├───config
    │       config.json
    │       jsonSecret.js
    │
    ├───controllers
    │       authController.js
    │       permissaoController.js
    │       produtoController.js
    │       roleController.js
    │       segurancaController.js
    │       usuarioController.js
    │
    ├───middleware
    │       autenticado.js
    │       permissoes.js
    │       permissoesRoles.js
    │       roles.js
    │
    ├───migrations
    │       20221222234111-create-produtos.js
    │       20230216210729-create-usuarios.js
    │       20230228212712-create-roles.js
    │       20230228222233-create-permissoes.js
    │       20230307212858-create-usuarios-roles.js
    │       20230307212933-create-usuarios-permissoes.js
    │       20230307213004-create-roles-permissoes.js
    │       20241028232048-create-usuarios.js
    │       20241029231109-create-roles.js
    │       20241029235729-create-permissoes.js
    │       20241030235139-create-usuarios-roles.js
    │       20241030235218-create-usuarios-permissoes.js
    │       20241030235239-create-roles-permissoes.js
    │
    ├───models
    │       index.js
    │       permissoes.js
    │       produtos.js
    │       roles.js
    │       roles_permissoes.js
    │       usuarios.js
    │       usuarios_permissoes.js
    │       usuarios_roles.js
    │
    ├───routes
    │       authRoute.js
    │       index.js
    │       permissao.js
    │       permissaoRoute.js
    │       produtoRoute.js
    │       role.js
    │       roleRoute.js
    │       seguranca.js
    │       usuariosRoute.js
    │
    └───services
            authService.js
            permissaoService.js
            produtoService.js
            roleService.js
            segurancaService.js
            usuarioService.js
```

### Key Components
- **Config**: Configuration files for the API, including database and JWT settings.
- **Controllers**: Handle incoming requests and call appropriate services.
- **Middleware**: Implement authentication and authorization logic to secure routes.
- **Migrations**: Database migration scripts for managing schema changes.
- **Models**: Define the database models using Sequelize.
- **Routes**: Define the API endpoints and map them to the appropriate controllers.
- **Services**: Contain the business logic and interact with the models to process data.

## Features
- **Full CRUD Operations**: Perform Create, Read, Update, and Delete operations on inventory items and user data.
- **User Authentication**: Secure login with JWT, ensuring only authenticated users can access protected routes.
- **Role and Permission Management**: Assign roles to users (e.g., manager, salesperson, stock clerk) with tailored permissions.
- **Security Middlewares**: Validate JWT tokens and enforce role-based access control to protect endpoints.
- **Relational Database Support**: Utilize Sequelize ORM to manage relationships such as users and their roles and permissions.

## Technology Stack
- **Node.js**: Backend runtime for JavaScript.
- **Sequelize ORM**: For defining models and relationships with an SQL database.
- **JWT**: For secure user authentication.
- **Express.js**: Web framework for building RESTful APIs.

## Getting Started

### Prerequisites
- **Node.js** (version 14 or higher)
- **npm** (Node package manager)
- **Sequelize CLI**
- **PostgreSQL** (or other SQL database)

### Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/supermarket-inventory-api.git
   cd supermarket-inventory-api
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   Create a `.env` file and add the following:
   ```dotenv
   JWT_SECRET=your_jwt_secret
   DATABASE_URL=your_database_url
   ```

4. **Run database migrations**:
   ```bash
   npx sequelize-cli db:migrate
   ```

5. **Start the server**:
   ```bash
   npm start
   ```

### Usage
- Use **Postman** or **Insomnia** to test API endpoints.
- Authenticate by sending a login request and receiving a JWT token for protected routes.
- Use the token in the `Authorization` header to access secure endpoints.

## API Endpoints
### Authentication
- **POST /auth/login**: Log in and receive a JWT token.
- **POST /auth/register**: Register a new user with a role.

### Inventory
- **GET /produtos**: Get all products.
- **POST /produtos**: Add a new product (Manager/Stock Clerk access).
- **PUT /produtos/:id**: Update product details (Manager/Stock Clerk access).
- **DELETE /produtos/:id**: Delete a product (Manager access).

### User and Role Management
- **GET /usuarios**: Get all users (Manager access).
- **POST /usuarios**: Add a new user with a specific role.
- **GET /roles**: Get all available roles.
- **GET /permissoes**: Get all permissions.

## License
This project is licensed under the ISC License.

---

For questions or support, feel free to reach out or submit an issue.