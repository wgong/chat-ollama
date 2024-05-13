# ChatOllama

## Use with Nuxt 3 Development Server

If you'd like to run with the latest code base and apply changes as needed, you can clone this repository and follow the steps below.

1. Install and run Ollama server

    You will need an Ollama server running. Follow the installation guide of [Ollama](https://github.com/ollama/ollama). By default, it's running on http://localhost:11434.    

2. Install Chroma

    Please refer to [https://docs.trychroma.com/getting-started](https://docs.trychroma.com/getting-started) for Chroma installation.

    launch docker desktop, 
    We recommend you run it in a docker container:

    ```bash
    #https://hub.docker.com/r/chromadb/chroma/tags

    docker pull chromadb/chroma
    docker run -d -p 8000:8000 chromadb/chroma
    ```
    Now, ChromaDB is running on http://localhost:8000

3. ChatOllama Setup

    Now, we can complete the necessary setup to run ChatOllama.

    3.1 Copy the `.env.example` file to `.env` file:

    ```bash
    cp .env.example .env
    ```

    3.2 Make sure to install the dependencies:

    ```bash
    # npm
    npm install

    # pnpm
    pnpm install

    # yarn
    yarn install

    # bun
    bun install
    ```

    3.3 Run a migration to create your database tables with Prisma Migrate

    ```bash
    # npm
    npm run prisma-migrate

    # pnpm
    pnpm prisma-migrate

    # yarn
    yarn prisma-migrate

    # bun
    bun run prisma-migrate
    ```

4. Launch Development Server

    > Make sure both __[Ollama Server](#ollama-server)__ and __[ChromaDB](#install-chromadb-and-startup)__ are running.

    Start the development server on `http://localhost:3000`:

    ```bash
    # npm
    npm run dev -- --port 3003   # use port 3003

    # pnpm
    pnpm dev

    # yarn
    yarn dev

    # bun
    bun run dev
    ```


## Tips

- restart Ubuntu if chat-ollama is not very responsive, reported an issue: https://github.com/sugarforever/chat-ollama/issues/224
