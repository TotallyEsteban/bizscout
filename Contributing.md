# Contributing to BizScout

First off, thank you for considering contributing to BizScout! It's people like you that make BizScout such a great tool.

Following these guidelines helps to communicate that you respect the time of the developers managing and developing this open source project. In return, they should reciprocate that respect in addressing your issue, assessing changes, and helping you finalize your pull requests.

## What we're looking for

BizScout is an open source project and we love to receive contributions from our community! There are many ways to contribute, from writing tutorials or blog posts, improving the documentation, submitting bug reports and feature requests, or writing code which can be incorporated into BizScout itself.

## Getting started

For something that is bigger than a one or two line fix:

1. Create your own fork of the code
2. Do the changes in your fork
3. If you like the change and think the project could use it:
    * Be sure you have followed the code style for the project.
    * Sign the Contributor License Agreement, CLA, with the project maintainers.
    * Note the BizScout Code of Conduct.
    * Send a pull request indicating that you have a CLA on file.

Small contributions such as fixing spelling errors, where the content is small enough to not be considered intellectual property, can be submitted by a contributor as a patch.

### Setting up your development environment

The project uses a standard Python/React development environment. Here's how to set it up:

#### Backend (Python)

1. Ensure you have Python 3.9+ installed
2. Clone the repository: `git clone https://github.com/yourusername/bizscout.git`
3. Navigate to the backend directory: `cd bizscout/backend`
4. Create a virtual environment: `python -m venv venv`
5. Activate the virtual environment:
   * Windows: `venv\Scripts\activate`
   * Unix/MacOS: `source venv/bin/activate`
6. Install dependencies: `pip install -r requirements.txt`
7. Set up environment variables: Copy `.env.example` to `.env` and adjust as needed
8. Ensure PostgreSQL with PostGIS extension is running
9. Apply database migrations: `alembic upgrade head`
10. Run the development server: `uvicorn main:app --reload`

#### Frontend (React)

1. Ensure you have Node.js 16+ installed
2. Navigate to the frontend directory: `cd bizscout/frontend`
3. Install dependencies: `npm install`
4. Set up environment variables: Copy `.env.example` to `.env.local` and adjust as needed
5. Run the development server: `npm run dev`

## How to report a bug

If you find a security vulnerability, do NOT open an issue. Email security@bizscout.com instead.

When filing an issue, make sure to answer these five questions:

1. What version of BizScout are you using?
2. What operating system and processor architecture are you using?
3. What did you do?
4. What did you expect to see?
5. What did you see instead?

## How to suggest a feature or enhancement

If you find yourself wishing for a feature that doesn't exist in BizScout, you are probably not alone. There are bound to be others out there with similar needs. Open an issue on our issues list on GitHub which describes the feature you would like to see, why you need it, and how it should work.

## Code review process

The core team looks at Pull Requests on a regular basis. After feedback has been given we expect responses within two weeks. After two weeks we may close the PR if it isn't showing any activity.

## Coding conventions

Start reading our code and you'll get the hang of it. We optimize for readability:

### Python (Backend)

- We follow PEP 8 style guide for Python code
- We use type annotations wherever possible
- We use black for code formatting
- We use isort for organizing imports
- Use docstrings for functions, classes, and modules

### JavaScript/TypeScript (Frontend)

- We use ESLint with the Airbnb style guide
- We use Prettier for code formatting
- We prefer TypeScript over JavaScript
- Use JSDoc comments for functions, components, and modules

## Commit messages

We follow conventional commits specification:

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, etc)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to the build process or auxiliary tools and libraries

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/yourusername/bizscout/tags).

## Community

Feel free to join our [Discord server](https://discord.gg/bizscout) for questions, discussions, and community support.

## License

By contributing, you agree that your contributions will be licensed under the project's MIT License.
