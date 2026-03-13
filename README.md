# 🎯 Lead Matching System

An AI-powered matchmaking platform that connects **Influencers**, **Brands**, and **Collaborators** using vector search and semantic matching.

Built with **Next.js**, **Pinecone Vector Database**, and **OpenAI Embeddings**.

---

## 🚀 Getting Started

Follow these steps to get the system running on your local machine.

### 1. Prerequisites
Make sure you have the following installed:
*   [Node.js](https://nodejs.org/) (v18 or higher)
*   [npm](https://www.npmjs.com/) (usually comes with Node.js)

### 2. Prepare your API Keys
You will need accounts and API keys from:
1.  **[Pinecone](https://www.pinecone.io/)**: Create an index named `lead-matching-system` with **1536 dimensions** (Cosine similarity).
2.  **[OpenAI](https://platform.openai.com/)**: To generate data embeddings.

### 3. Installation
1.  **Download and Unzip** the project folder.
2.  Open your terminal (Terminal on Mac, Command Prompt on Windows).
3.  Navigate to the project folder:
    ```bash
    cd path/to/lead-matching-system
    ```
4.  Install dependencies:
    ```bash
    npm install
    ```

### 4. Configuration
1.  Copy the environment template:
    ```bash
    cp .env.example .env
    ```
2.  Open the newly created `.env` file in a text editor and paste your API keys:
    ```env
    PINECONE_API_KEY=your_key_here
    OPENAI_API_KEY=your_key_here
    ```

### 5. Seed the Data (First Time Only)
To populate your Pinecone database with sample influencers and brands:
```bash
npx tsx src/scripts/seedPinecone.ts
```

### 6. Run the App
Start the development server:
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser to see the result!

---

## 🛠️ How it Works

1.  **Data Encoding**: Profiles (Influencers/Brands) are converted into mathematical vectors (embeddings) using OpenAI.
2.  **Vector Storage**: These vectors are stored in **Pinecone**.
3.  **Semantic Search**: When you search for "Tech reviewers for a $500 app review," the system finds profiles whose vectors are mathematically closest to your query.
4.  **Smart Matching**: The system ranks matches based on niche, platform, and budget compatibility.

## 📂 Project Structure

*   `src/app`: Frontend pages and API routes.
*   `src/services`: Core logic for matching and database interaction.
*   `src/scripts`: Tools for seeding and testing the database.
*   `directives/`: Agent-specific logic and system instructions.

---

## 📄 License
MIT
