# 🧠 Recallify - AI-Powered Study Assistant

A modern, intelligent study companion that leverages Together AI to help students learn more effectively. Generate flashcards, create quizzes, and get personalized study assistance powered by state-of-the-art AI models.

![Next.js](https://img.shields.io/badge/Next.js-14.0.0-black)
![React](https://img.shields.io/badge/React-18.0.0-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0.0-blue)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.3.0-38B2AC)
![Together AI](https://img.shields.io/badge/Together_AI-API-orange)

## ✨ Features

### 🎯 **Study Buddy AI**
- Get instant, educational answers to any question
- Structured responses with clear headings and bullet points
- Friendly, encouraging language to keep you motivated
- Perfect for homework help and concept clarification

### 🗂️ **Smart Flashcard Generator**
- Convert your study notes into interactive flashcards
- AI-powered content extraction and organization
- JSON format for easy integration with flashcard apps
- Focus on key concepts and important facts

### 📝 **Intelligent Quiz Creator**
- Generate multiple-choice questions from any text
- Challenging yet fair questions with plausible distractors
- Detailed explanations for correct answers
- Perfect for test preparation and self-assessment

## 🚀 Tech Stack

- **Frontend**: Next.js 14, React 18, TypeScript
- **Styling**: Tailwind CSS
- **AI Integration**: Together AI API
- **AI Models**: Mistral 7B, Qwen 7B, Gemma 2 9B, Llama 2, CodeLlama
- **Deployment**: Netlify-ready

## 🏗️ Architecture

```
Recallify/
├── app/                    # Next.js 14 App Router
│   ├── api/               # API Routes
│   │   ├── study-buddy/   # Study assistance endpoint
│   │   ├── flashcards/    # Flashcard generation
│   │   └── quiz/          # Quiz creation
│   ├── globals.css        # Global styles
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Main page
├── components/             # React components
├── lib/                    # Utility libraries
│   └── together-api.ts    # Together AI integration
└── public/                 # Static assets
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn
- Together AI API key

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/recallify.git
   cd recallify
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp env.example .env.local
   ```
   
   Add your Together AI API key to `.env.local`:
   ```bash
   TOGETHER_API_KEY=your_api_key_here
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 🔑 Getting Your Together AI API Key

1. Visit [Together AI](https://together.ai/)
2. Sign up for an account
3. Navigate to your API keys section
4. Create a new API key
5. Add it to your `.env.local` file

## 📚 API Endpoints

### Study Buddy
```http
POST /api/study-buddy
Content-Type: application/json

{
  "question": "What is photosynthesis?"
}
```

**Response:**
```json
{
  "answer": "**Introduction**\nPhotosynthesis is the process by which plants convert light energy into chemical energy...\n\n**Main Points**\n• Plants use sunlight, water, and carbon dioxide\n• Chlorophyll captures light energy\n• Glucose and oxygen are produced\n\n**Examples**\n• Green leaves in sunlight\n• Algae in ponds\n• Trees in forests\n\n**Summary**\nPhotosynthesis is essential for life on Earth..."
}
```

### Flashcard Generator
```http
POST /api/flashcards
Content-Type: application/json

{
  "notes": "Photosynthesis is the process by which plants convert light energy into chemical energy. They use chlorophyll to capture sunlight and convert CO2 and water into glucose and oxygen."
}
```

**Response:**
```json
{
  "flashcards": [
    {
      "front": "What is photosynthesis?",
      "back": "The process by which plants convert light energy into chemical energy"
    },
    {
      "front": "What pigment do plants use to capture sunlight?",
      "back": "Chlorophyll"
    }
  ]
}
```

### Quiz Creator
```http
POST /api/quiz
Content-Type: application/json

{
  "text": "Photosynthesis is the process by which plants convert light energy into chemical energy. They use chlorophyll to capture sunlight and convert CO2 and water into glucose and oxygen."
}
```

**Response:**
```json
{
  "quiz": [
    {
      "question": "What is the main purpose of photosynthesis?",
      "options": [
        "To convert light energy into chemical energy",
        "To produce oxygen only",
        "To create water",
        "To absorb carbon dioxide"
      ],
      "correct": 0,
      "explanation": "Photosynthesis converts light energy into chemical energy stored in glucose molecules."
    }
  ]
}
```

## 🤖 AI Models

The project uses Together AI's serverless models for optimal performance and cost-effectiveness:

- **Mistral 7B** (Default) - Fast, accurate, cost-effective
- **Qwen 7B** - Good balance of speed and quality
- **Gemma 2 9B** - Google's efficient model
- **Llama 2 7B/13B** - Meta's reliable models
- **CodeLlama 7B** - Specialized for code-related tasks

## 🎨 Customization

### Changing AI Models
Update the model in any API route:

```typescript
const response = await callTogetherAPI(prompt, {
  model: TOGETHER_MODELS.QWEN_7B,  // Change model here
  systemPrompt: 'Your custom system prompt',
  maxTokens: 2048,
  temperature: 0.7
})
```

### Adjusting AI Parameters
- **maxTokens**: Control response length (default: 2048)
- **temperature**: Control creativity (0.0 = focused, 1.0 = creative)
- **systemPrompt**: Define AI behavior and role

## 🚀 Deployment

### Netlify (Recommended)
1. Connect your GitHub repository to Netlify
2. Set environment variables in Netlify dashboard
3. Deploy automatically on push to main branch

### Vercel
1. Import your repository to Vercel
2. Add environment variables
3. Deploy with one click

### Other Platforms
The project is compatible with any platform that supports Next.js:
- Railway
- Render
- DigitalOcean App Platform
- AWS Amplify

## 📊 Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `TOGETHER_API_KEY` | Your Together AI API key | ✅ |
| `TOGETHER_DEFAULT_MODEL` | Override default AI model | ❌ |

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines
- Follow TypeScript best practices
- Use meaningful commit messages
- Test your changes thoroughly
- Update documentation as needed

## 🐛 Troubleshooting

### Common Issues

**API Key Error**
```bash
Error: TOGETHER_API_KEY environment variable is required
```
**Solution**: Ensure your `.env.local` file contains the correct API key.

**Model Not Available**
```bash
Error: Unable to access non-serverless model
```
**Solution**: The project now uses serverless models by default. No action needed.

**Rate Limiting**
```bash
Error: Rate limit exceeded
```
**Solution**: Check your Together AI usage limits and upgrade if necessary.

### Getting Help
- Check the [Together AI documentation](https://docs.together.ai/)
- Review [Next.js documentation](https://nextjs.org/docs)
- Open an issue on GitHub

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Together AI** for providing powerful AI models
- **Next.js team** for the amazing framework
- **Vercel** for the deployment platform
- **Open source community** for inspiration and tools

## 📞 Support

- **GitHub Issues**: [Report bugs or request features](https://github.com/ayushk1233/recallify/issues)
- **Discussions**: [Join the community](https://github.com/ayushk1233/recallify/discussions)
- **Email**: ayushk1503@gmail.com

---

<div align="center">
  <p>Made with ❤️ for students everywhere</p>
  <p>Star this repo if it helps you study better! ⭐</p>
</div>
