<p align="center">
    <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/ec559a9f6bfd399b82bb44393651661b08aaf7ba/icons/folder-markdown-open.svg" align="center" width="30%">
</p>
<p align="center"><h1 align="center">KNOWLEDGE_CHAT_SYSTEM.GIT</h1></p>
<p align="center">
	<em>Empowering knowledge sharing with cutting-edge technology.</em>
</p>
<p align="center">
	<img src="https://img.shields.io/github/license/tez-thecoder8122/knowledge_chat_system.git?style=default&logo=opensourceinitiative&logoColor=white&color=0080ff" alt="license">
	<img src="https://img.shields.io/github/last-commit/tez-thecoder8122/knowledge_chat_system.git?style=default&logo=git&logoColor=white&color=0080ff" alt="last-commit">
	<img src="https://img.shields.io/github/languages/top/tez-thecoder8122/knowledge_chat_system.git?style=default&color=0080ff" alt="repo-top-language">
	<img src="https://img.shields.io/github/languages/count/tez-thecoder8122/knowledge_chat_system.git?style=default&color=0080ff" alt="repo-language-count">
</p>
<p align="center"><!-- default option, no dependency badges. -->
</p>
<p align="center">
	<!-- default option, no dependency badges. -->
</p>
<br>

## 🔗 Table of Contents

- [📍 Overview](#-overview)
- [👾 Features](#-features)
- [📁 Project Structure](#-project-structure)
  - [📂 Project Index](#-project-index)
- [🚀 Getting Started](#-getting-started)
  - [☑️ Prerequisites](#-prerequisites)
  - [⚙️ Installation](#-installation)
  - [🤖 Usage](#🤖-usage)
  - [🧪 Testing](#🧪-testing)
- [📌 Project Roadmap](#-project-roadmap)
- [🔰 Contributing](#-contributing)
- [🎗 License](#-license)
- [🙌 Acknowledgments](#-acknowledgments)

---

## 📍 Overview

The knowledgechatsystem.git project is a comprehensive solution that simplifies building a robust Knowledge Chat System API. It streamlines user authentication, document management, and AI-generated query responses. Ideal for developers seeking efficient database management, secure user interactions, and seamless integration of advanced functionalities.

---

## 👾 Features

|      | Feature         | Summary       |
| :--- | :---:           | :---          |
| ⚙️  | **Architecture**  | <ul><li>Utilizes **FastAPI** for building robust APIs</li><li>Integrates **SQLAlchemy** for database operations</li><li>Employs **Pydantic** for data validation</li></ul> |
| 🔩 | **Code Quality**  | <ul><li>Follows PEP 8 coding standards</li><li>Includes comprehensive unit tests with **pytest**</li><li>Utilizes **logging** for effective debugging</li></ul> |
| 📄 | **Documentation** | <ul><li>Well-documented codebase with inline comments</li><li>Includes detailed README.md for setup and usage</li><li>Utilizes **Sphinx** for generating documentation</li></ul> |
| 🔌 | **Integrations**  | <ul><li>Integrates **OpenAI** for AI-generated answers</li><li>Utilizes **PostgreSQL** for data storage</li><li>Includes **FAISS** for similarity search</li></ul> |
| 🧩 | **Modularity**    | <ul><li>Organized codebase with modular components</li><li>Separation of concerns for clear functionality</li><li>Utilizes **services** for encapsulating business logic</li></ul> |
| 🧪 | **Testing**       | <ul><li>Comprehensive unit tests covering core functionalities</li><li>Includes integration tests for API endpoints</li><li>Utilizes **pytest** for testing framework</li></ul> |
| ⚡️  | **Performance**   | <ul><li>Efficient text processing and indexing for quick responses</li><li>Utilizes **FAISS** for fast similarity search</li><li>Optimized database queries for performance</li></ul> |
| 🛡️ | **Security**      | <ul><li>Hashes passwords for secure storage</li><li>Implements JWT token generation for user authentication</li><li>Ensures data validation and sanitization</li></ul> |
| 📦 | **Dependencies**  | <ul><li>Includes essential dependencies like **FastAPI**, **SQLAlchemy**, and **OpenAI**</li><li>Utilizes **pip** for package management</li><li>Ensures version control with **requirements.txt**</li></ul> |

---

## 📁 Project Structure

```sh
└── knowledge_chat_system.git/
    ├── Dockerfile
    ├── app
    │   ├── __init__.py
    │   ├── config.py
    │   ├── db
    │   ├── main.py
    │   ├── models
    │   ├── routes
    │   ├── services
    │   └── utils
    ├── docker-compose.yml
    └── requirements.txt
```


### 📂 Project Index
<details open>
	<summary><b><code>KNOWLEDGE_CHAT_SYSTEM.GIT/</code></b></summary>
	<details> <!-- __root__ Submodule -->
		<summary><b>__root__</b></summary>
		<blockquote>
			<table>
			<tr>
				<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/requirements.txt'>requirements.txt</a></b></td>
				<td>- Facilitates project dependencies management by specifying required packages and versions<br>- Supports seamless integration of various libraries for enhanced functionality and performance within the codebase architecture.</td>
			</tr>
			<tr>
				<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/docker-compose.yml'>docker-compose.yml</a></b></td>
				<td>- Defines services and configurations for a PostgreSQL database and a FastAPI application within the project's Docker Compose setup<br>- Manages database environment variables, ports, volumes, and network connections for seamless communication between the database and the FastAPI application<br>- Ensures the health and availability of the PostgreSQL service.</td>
			</tr>
			<tr>
				<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/Dockerfile'>Dockerfile</a></b></td>
				<td>- Facilitates building and running a Python web application within a Docker container<br>- Sets up the necessary environment, installs dependencies, copies application code, creates essential directories, exposes a port, and defines the command to start the application<br>- This Dockerfile streamlines the deployment process for the project.</td>
			</tr>
			</table>
		</blockquote>
	</details>
	<details> <!-- app Submodule -->
		<summary><b>app</b></summary>
		<blockquote>
			<table>
			<tr>
				<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/config.py'>config.py</a></b></td>
				<td>- Defines project settings including database, JWT, OpenAI, and application configurations<br>- Utilizes pydantic_settings for type validation<br>- Centralizes configuration management for the entire codebase.</td>
			</tr>
			<tr>
				<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/main.py'>main.py</a></b></td>
				<td>- Manages the startup and shutdown events of the Knowledge Chat System API, initializing the database and configuring the OpenAI API key<br>- The code sets up the FastAPI application, adds CORS middleware, includes routers for different functionalities, and defines endpoints for root and health checks<br>- It ensures the smooth operation and health status of the system.</td>
			</tr>
			</table>
			<details>
				<summary><b>models</b></summary>
				<blockquote>
					<table>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/models/schemas.py'>schemas.py</a></b></td>
						<td>- Defines Pydantic schemas for user registration, login, responses, JWT tokens, document upload, listing, knowledge base queries, and health checks<br>- These schemas structure data for various functionalities within the project, ensuring consistency and validation of input/output data across different parts of the system.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/models/database.py'>database.py</a></b></td>
						<td>- Defines SQLAlchemy models for users and documents, establishing relationships between them<br>- Manages user authentication and document ownership, storing metadata for uploaded files<br>- Facilitates data retrieval and manipulation within the application's database structure.</td>
					</tr>
					</table>
				</blockquote>
			</details>
			<details>
				<summary><b>routes</b></summary>
				<blockquote>
					<table>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/routes/query.py'>query.py</a></b></td>
						<td>- Enables querying the knowledge base for AI-generated answers based on user input<br>- Utilizes FastAPI to handle HTTP requests, SQLAlchemy for database operations, and logging for tracking queries<br>- Employs user authentication and error handling to ensure secure and reliable query processing.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/routes/documents.py'>documents.py</a></b></td>
						<td>- Enables uploading, listing, and deleting user documents<br>- Handles document processing, deletion, and retrieval for the authenticated user<br>- Logs relevant actions and provides necessary error handling<br>- Supports file removal and database operations for document management.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/routes/auth.py'>auth.py</a></b></td>
						<td>- Handles user authentication and registration by providing endpoints for user registration and login<br>- Utilizes FastAPI for routing and SQLAlchemy for database operations<br>- Implements JWT token generation for user login<br>- Logs registration and login activities<br>- Maintains a structured approach to user authentication within the project architecture.</td>
					</tr>
					</table>
				</blockquote>
			</details>
			<details>
				<summary><b>utils</b></summary>
				<blockquote>
					<table>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/utils/logger.py'>logger.py</a></b></td>
						<td>- Create a logger to handle console and file logging, ensuring no duplicate handlers are added<br>- Set logging levels and formatters for both handlers<br>- Log messages include timestamps, logger name, log level, function name, line number, and message.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/utils/helpers.py'>helpers.py</a></b></td>
						<td>- Defines a function to retrieve the current authenticated user from a JWT token<br>- Handles token decoding, user retrieval from the database, and error handling for invalid tokens or missing users<br>- This utility function plays a crucial role in ensuring secure user authentication within the project's architecture.</td>
					</tr>
					</table>
				</blockquote>
			</details>
			<details>
				<summary><b>services</b></summary>
				<blockquote>
					<table>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/services/auth_service.py'>auth_service.py</a></b></td>
						<td>- Handles authentication operations by hashing passwords, creating JWT access tokens, decoding tokens, creating new users, authenticating users, and retrieving users by ID<br>- The AuthService class in auth_service.py ensures secure user authentication and registration processes within the project's architecture.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/services/query_service.py'>query_service.py</a></b></td>
						<td>- Facilitates querying the knowledge base by loading user documents, searching for similar text chunks using FAISS, and generating answers with GPT-4 based on context<br>- Integrates with the database, embedding service, and OpenAI for a comprehensive knowledge retrieval system.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/services/embedding_service.py'>embedding_service.py</a></b></td>
						<td>- Handles text embedding operations by generating embeddings for single or multiple texts, calculating cosine similarity between vectors<br>- Utilizes OpenAI API with a predefined model for embedding generation<br>- Logs relevant information for each operation.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/services/document_service.py'>document_service.py</a></b></td>
						<td>- Handles document processing, including validation, saving, text extraction based on file type, chunking, embedding generation, and FAISS indexing<br>- The service ensures uploaded files are processed, indexed, and stored efficiently, enabling users to search and retrieve documents effectively within the system.</td>
					</tr>
					</table>
				</blockquote>
			</details>
			<details>
				<summary><b>db</b></summary>
				<blockquote>
					<table>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/db/session.py'>session.py</a></b></td>
						<td>- Manages database connections, sessions, and table initialization<br>- Utilizes SQLAlchemy to create an engine with connection pooling and a session factory<br>- Implements functions to initialize database tables and retrieve database sessions<br>- Integrates with project settings, models, and logging for seamless database operations.</td>
					</tr>
					<tr>
						<td><b><a href='https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/master/app/db/__int__.py'>__int__.py</a></b></td>
						<td>Enables seamless database interactions within the project architecture, ensuring efficient data management and retrieval.</td>
					</tr>
					</table>
				</blockquote>
			</details>
		</blockquote>
	</details>
</details>

---
## 🚀 Getting Started

### ☑️ Prerequisites

Before getting started with knowledge_chat_system.git, ensure your runtime environment meets the following requirements:

- **Programming Language:** Python
- **Package Manager:** Pip
- **Container Runtime:** Docker


### ⚙️ Installation

Install knowledge_chat_system.git using one of the following methods:

**Build from source:**

1. Clone the knowledge_chat_system.git repository:
```sh
❯ git clone https://github.com/tez-thecoder8122/knowledge_chat_system.git
```

2. Navigate to the project directory:
```sh
❯ cd knowledge_chat_system.git
```

3. Install the project dependencies:


**Using `pip`** &nbsp; [<img align="center" src="https://img.shields.io/badge/Pip-3776AB.svg?style={badge_style}&logo=pypi&logoColor=white" />](https://pypi.org/project/pip/)

```sh
❯ pip install -r requirements.txt
```


**Using `docker`** &nbsp; [<img align="center" src="https://img.shields.io/badge/Docker-2CA5E0.svg?style={badge_style}&logo=docker&logoColor=white" />](https://www.docker.com/)

```sh
❯ docker build -t tez-thecoder8122/knowledge_chat_system.git .
```




### 🤖 Usage
Run knowledge_chat_system.git using the following command:
**Using `pip`** &nbsp; [<img align="center" src="https://img.shields.io/badge/Pip-3776AB.svg?style={badge_style}&logo=pypi&logoColor=white" />](https://pypi.org/project/pip/)

```sh
❯ python {entrypoint}
```


**Using `docker`** &nbsp; [<img align="center" src="https://img.shields.io/badge/Docker-2CA5E0.svg?style={badge_style}&logo=docker&logoColor=white" />](https://www.docker.com/)

```sh
❯ docker run -it {image_name}
```


### 🧪 Testing
Run the test suite using the following command:
**Using `pip`** &nbsp; [<img align="center" src="https://img.shields.io/badge/Pip-3776AB.svg?style={badge_style}&logo=pypi&logoColor=white" />](https://pypi.org/project/pip/)

```sh
❯ pytest
```


---
## 📌 Project Roadmap

- [X] **`Task 1`**: <strike>Implement feature one.</strike>
- [ ] **`Task 2`**: Implement feature two.
- [ ] **`Task 3`**: Implement feature three.

---

## 🔰 Contributing

- **💬 [Join the Discussions](https://github.com/tez-thecoder8122/knowledge_chat_system.git/discussions)**: Share your insights, provide feedback, or ask questions.
- **🐛 [Report Issues](https://github.com/tez-thecoder8122/knowledge_chat_system.git/issues)**: Submit bugs found or log feature requests for the `knowledge_chat_system.git` project.
- **💡 [Submit Pull Requests](https://github.com/tez-thecoder8122/knowledge_chat_system.git/blob/main/CONTRIBUTING.md)**: Review open PRs, and submit your own PRs.

<details closed>
<summary>Contributing Guidelines</summary>

1. **Fork the Repository**: Start by forking the project repository to your github account.
2. **Clone Locally**: Clone the forked repository to your local machine using a git client.
   ```sh
   git clone https://github.com/tez-thecoder8122/knowledge_chat_system.git
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to github**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.
8. **Review**: Once your PR is reviewed and approved, it will be merged into the main branch. Congratulations on your contribution!
</details>

<details closed>
<summary>Contributor Graph</summary>
<br>
<p align="left">
   <a href="https://github.com{/tez-thecoder8122/knowledge_chat_system.git/}graphs/contributors">
      <img src="https://contrib.rocks/image?repo=tez-thecoder8122/knowledge_chat_system.git">
   </a>
</p>
</details>

---

## 🎗 License

This project is protected under the [SELECT-A-LICENSE](https://choosealicense.com/licenses) License. For more details, refer to the [LICENSE](https://choosealicense.com/licenses/) file.

---

## 🙌 Acknowledgments

- List any resources, contributors, inspiration, etc. here.

---
