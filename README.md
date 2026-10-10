# AI College Knowledge Assistant

An AI-powered college knowledge assistant designed to help students find accurate answers to college-related questions using official college documents and academic resources.

The project uses a **monorepo architecture** with Next.js for the frontend and NestJS for the backend. The planned AI layer will use Retrieval-Augmented Generation (RAG) to answer questions based on relevant college documents and provide source references.

## Features

### Planned Features

- **AI-powered Q&A:** Ask questions about college rules, academic schedules, examinations, and other college-related information.
- **Document-based answers:** Retrieve relevant information from official college documents.
- **Source references:** Help users verify answers by identifying the supporting document or page when available.
- **Modern web interface:** A responsive and user-friendly interface built with Next.js.
- **Scalable backend:** A modular REST API built with NestJS.
- **RAG pipeline:** Retrieve relevant document content before generating an answer to reduce unsupported responses.

> Note: Features listed above are planned capabilities and may not be implemented yet.

## Tech Stack

| Area            | Technology                        |
| --------------- | --------------------------------- |
| Frontend        | Next.js, React, TypeScript        |
| Styling         | Tailwind CSS                      |
| Backend         | NestJS, Node.js, TypeScript       |
| AI integration  | Planned: LLM, RAG, LangChain      |
| Database        | Planned: PostgreSQL with pgvector |
| Package manager | pnpm                              |
| Code quality    | ESLint, Oxlint, Prettier          |
| Git hooks       | Husky, lint-staged                |
| CI/CD           | GitHub Actions                    |

## Project Structure

```text
ai-college-knowledge-assistant/
├── apps/
│   ├── web/                  # Next.js frontend
│   └── api/                  # NestJS backend
├── packages/                 # Shared packages (optional)
├── .github/
│   └── workflows/
│       └── main.yaml         # CI workflow
├── .husky/                   # Git hooks
├── .lintstagedrc.json
├── .prettierrc.json
├── .prettierignore
├── package.json
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
└── README.md
```

## Prerequisites

Install the following before running the project:

- [Node.js](https://nodejs.org/) — version 22
- [pnpm](https://pnpm.io/) — version 12.10.1

Check your installed versions:

```bash
node --version
pnpm --version
```

## Getting Started

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd ai-college-knowledge-assistant
```

Replace `<YOUR_GITHUB_REPOSITORY_URL>` with your actual GitHub repository URL.

### 2. Install dependencies

```bash
pnpm install
```

### 3. Start the frontend

```bash
pnpm dev:web
```

The Next.js application will usually be available at:

http://localhost:3000

### 4. Start the backend

Open another terminal in the project root:

```bash
pnpm dev:api
```

The NestJS API will usually be available at:

http://localhost:4000

If your backend is configured to use a different port, use that port instead.

## Available Commands

Run these commands from the monorepo root.

| Command             | Description                              |
| ------------------- | ---------------------------------------- |
| `pnpm dev:web`      | Start the frontend development server    |
| `pnpm dev:api`      | Start the backend in development mode    |
| `pnpm build:web`    | Build the frontend                       |
| `pnpm build:api`    | Build the backend                        |
| `pnpm lint:web`     | Lint the frontend                        |
| `pnpm lint:api`     | Lint the backend                         |
| `pnpm lint`         | Run both lint checks                     |
| `pnpm format`       | Format supported project files           |
| `pnpm format:check` | Check formatting without modifying files |
| `pnpm test:api`     | Run backend tests                        |

## Environment Variables

Create environment files only when the corresponding features need them.

### Frontend — `apps/web/.env.local`

```env
NEXT_PUBLIC_API_URL=http://localhost:4000
```

### Backend — `apps/api/.env`

Add backend configuration here as needed, such as the API port, database connection string, and AI provider credentials.

```env
PORT=4000
DATABASE_URL=your_database_connection_string
```

Use the environment variable names expected by your implementation. Never commit real API keys, passwords, or production credentials.

## How the AI Assistant Will Work

The planned RAG workflow is:

1. **Document ingestion:** Collect approved college documents, such as academic notices, regulations, and student handbooks.
2. **Text extraction:** Extract text and preserve useful document metadata, such as page numbers.
3. **Chunking and embeddings:** Split the extracted content into smaller passages and convert them into vector embeddings.
4. **Retrieval:** Find passages relevant to the student's question.
5. **Answer generation:** Provide the retrieved context to an LLM to generate a grounded response.
6. **Source attribution:** Return supporting document references so students can verify the information.

The quality of answers depends on the quality, freshness, and completeness of the source documents.

## Development Workflow

This repository uses a monorepo structure to keep the frontend and backend in one place while maintaining separate applications.

Before pushing changes, run:

```bash
pnpm format:check
pnpm lint
pnpm build:web
pnpm build:api
```

GitHub Actions is configured to run automated quality checks on pushes and pull requests according to the workflow configuration.

## Project Goals

- Make college information easier for students to access.
- Reduce the time spent searching through lengthy documents.
- Provide answers grounded in official information.
- Make responses easier to verify through source references.
- Build a maintainable foundation for future AI features.

## Future Improvements

- College document ingestion and processing pipeline
- PostgreSQL and pgvector integration
- Semantic search and retrieval evaluation
- LLM integration with citation-aware responses
- Conversation history and follow-up questions
- Document update and re-indexing support
- Automated tests and improved error handling

## Contributing

Contributions, suggestions, and bug reports are welcome.

1. Create a feature branch.
2. Make your changes.
3. Run formatting, linting, and build checks.
4. Open a pull request with a clear description of the changes.

## License

The project license has not been selected yet. Add a license before distributing the project publicly.
