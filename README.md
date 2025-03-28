# E-commerce Pipelines Client-Side

This project demonstrates the integration of Cloudflare Workers with Cloudflare Pipelines for data streaming. It sends the data to the pipleline from the client-side.

If you are looking for an example with server-side ingestion, check out the [Pipelines Server Side GitHub repo](https://github.com/harshil1712/cf-pipelines-bindings-demo).

## 🚀 Features

- Built with Cloudflare Workers
- Static asset handling
- Ingest data to Cloudflare Pipelines from the client

## 📋 Prerequisites

- Node.js (LTS version recommended)
- Cloudflare account with access to Pipelines and R2
- An R2 bucket

## Get started

1. Clone the repository:

```bash
git clone git@github.com:harshil1712/e-commerce-pipelines-client-side.git
cd e-commerce-pipelines-client-side
```

2. Install dependencies:

```bash
npm install
```

3. Create a new Cloudflare Pipeline

```bash
npx wrangler pipeline create clickstream-binding --r2-bucket <your-bucket-name>
```

4. Update your `public/index.html` file with the correct pipeline URL.

5. Update the CORS policy.

```bash
npx wrangler pipeline update clickstream-binding --cors-origin http://localhost:8787
```

6. Start the development server:

```bash
npm run dev
```

This will start Wrangler in development mode, allowing you to test your Worker locally.

## 🚀 Deployment

Deploy your Worker to Cloudflare:
```bash
npm run deploy
```

Update the CORS policy for the deployed pipeline.

```bash
npx wrangler pipeline update clickstream-binding --cors-origin https://<your-worker-name>.workers.dev
```

## 📁 Project Structure

- `/src` - Source code files
- `/public` - Static assets
- `wrangler.jsonc` - Cloudflare Workers configuration
- `tsconfig.json` - TypeScript configuration


## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

MIT
