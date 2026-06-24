MIST Chat Studio
Personal AI chat studio with multi-provider support and GitHub OAuth authentication.
Features
• GitHub OAuth Login — Secure authentication via GitHub
• Multi-Provider AI — OpenAI, Anthropic, Gemini, Cloudflare Workers AI
• Server-Side API Keys — Keys stored securely in .env, never exposed to frontend
• Chat History — Persistent conversations stored in browser
• Markdown Support — Full rendering with syntax highlighting
• Model Switching — Change AI provider/model on the fly
Quick Start
1. Clone & Install
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
npm install
2. Configure Environment
cp .env.example .env
# Edit .env with your actual credentials
3. Set up GitHub OAuth App
1. Go to GitHub Developer Settings
2. Click OAuth Apps → New OAuth App
3. Fill in:
• Application name: MIST Chat Studio
• Homepage URL: http://localhost:3000
• Authorization callback URL: http://localhost:3000/auth/callback
4. Copy Client ID and Client Secret to your .env
4. Run the Server
npm start # Production
npm run dev # Development with auto-reload
Open http://localhost:3000 in your browser.
Deployment
Deploy to Render/Railway/Heroku
1. Push code to GitHub
2. Connect your repo to the platform
3. Add environment variables in the platform dashboard
4. Update GitHub OAuth callback URL to your production domain

Environment Variables for Production
Variable Description
GITHUB_CLIENT_ID From GitHub OAuth App
GITHUB_CLIENT_SECRET From GitHub OAuth App
JWT_SECRET Random string for JWT signing
NODE_ENV Set to production
REDIRECT_URI Your production callback URL
OPENAI_API_KEY OpenAI API key
ANTHROPIC_API_KEY Anthropic API key
GEMINI_API_KEY Google Gemini API key
CLOUDFLARE_API_TOKEN Format: account_id|api_token
Project Structure
.
├── .env # Secrets (never commit!)
├── .env.example # Template for .env
├── .gitignore
├── package.json
├── server.js # Express backend
├── public/ # Static files
│ └── index.html # Frontend app
└── README.md
Security Notes
• Never commit .env — it’s in .gitignore by default
• API keys stay server-side — frontend only talks to your backend
• JWT tokens are httpOnly cookies — protected from XSS attacks
• State parameter — prevents CSRF attacks during OAuth
License
MIT
