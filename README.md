# Course Selling Backend App

This is a backend application for a course-selling platform. The application is built using Express.js and utilizes JWT for authentication and Zod for schema validation.

## Table of Contents

-   Features
-   Installation
-   Usage
-   API Endpoints
-   Authentication
-   Validation
-   Contributing
-   License

## Features

-   User authentication with JWT
-   Course management (CRUD operations)
-   Secure routes with token-based authentication
-   Data validation using Zod

## Installation

1.  Clone the repository:
    
    
    git clone
			    
		 https://github.com/syedahmedullah14/Course-Selling-App-Backend.git

2.  Navigate to the project directory:
		
		cd course-selling-backend
3.  Install the dependencies:
					
		npm install
4.  Create a `.env` file in the root directory and add the following environment variables:
	
		PORT=3000
		JWT_SECRET=your_jwt_secret
		DATABASE_URL=your_database_url
5.  Start the application:
 
		npm start
## Usage

Once the server is running, you can interact with the API using a tool like Postman or via frontend application.

## API Endpoints

### Authentication

-   **POST /api/auth/register**: Register a new user.
-   **POST /api/auth/login**: Authenticate a user and receive a JWT.

### Courses

-   **GET /api/courses**: Retrieve a list of all courses.
-   **GET /api/courses/:id**: Retrieve details of a specific course.
-   **POST /api/courses**: Create a new course. (Protected)
-   **PUT /api/courses/:id**: Update an existing course. (Protected)
-   **DELETE /api/courses/:id**: Delete a course. (Protected)

### Example Requests
#### Register
	POST /api/auth/register
	Content-Type: application/json

	{
	  "username": "exampleuser",
	  "password": "examplepassword"
	}
#### Login

	POST /api/auth/login
	Content-Type: application/json

	{
	  "username": "exampleuser",
	  "password": "examplepassword"
	}
#### Get Courses

	GET /api/courses

## Authentication

This application uses JWT (JSON Web Tokens) for authentication. After a successful login, the server returns a token which must be included in the `Authorization` header of requests to protected routes.

Example of setting the Authorization header:

	Authorization: Bearer your_jwt_token

## Validation

Zod is used for schema validation to ensure the correctness of data. It is applied to incoming requests for user registration, course creation, and updates.

Example of Zod schema for user registration:
		
	const userSchema = z.object({
	username: z.string().min(3).max(20),
	password: z.string().min(6).max(100),
	});
## Contributing

Contributions are welcome! Please create an issue or submit a pull request.

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature-branch`).
3.  Commit your changes (`git commit -am 'Add new feature'`).
4.  Push to the branch (`git push origin feature-branch`).
5.  Create a new Pull Request.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
