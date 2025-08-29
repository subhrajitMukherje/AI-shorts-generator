# 🎬 AI Video Generator

Transform your ideas into stunning short videos with the power of AI! This application automatically creates engaging videos complete with realistic images, professional voiceovers, and synchronized captions.

## ✨ What This App Does

This is an AI-powered video creation platform that turns simple text prompts into professional-looking short videos. Perfect for social media content, educational materials, or creative projects.

### 🎯 Key Features

- **🤖 AI Script Generation**: Converts your ideas into engaging video scripts
- **🎨 Realistic Image Creation**: Generates high-quality images that match your content
- **🎙️ Professional Voiceovers**: Creates natural-sounding audio narration
- **📝 Auto Captions**: Adds synchronized subtitles to your videos
- **📱 Mobile-Optimized**: Creates vertical videos perfect for social media
- **☁️ Cloud Processing**: All heavy lifting happens in the cloud
- **💳 Flexible Pricing**: Pay-per-use credit system

## 🚀 How It Works

1. **Enter Your Idea**: Type what you want your video to be about
2. **AI Magic Happens**: The system creates a script, generates images, records audio, and adds captions
3. **Get Your Video**: Download your finished video in minutes

### Example Prompts
- "Explain how photosynthesis works"
- "Top 5 productivity tips for remote workers"
- "The history of the internet in 30 seconds"
- "How to make the perfect cup of coffee"

## 🛠️ Technology Stack

### Frontend
- **Next.js 15**: Modern React framework for the web interface
- **TypeScript**: Type-safe JavaScript for better code quality
- **Tailwind CSS**: Utility-first CSS framework for styling
- **Framer Motion**: Smooth animations and transitions
- **Clerk**: User authentication and management

### Backend & AI Services
- **OpenAI GPT-4**: Generates video scripts and content
- **Replicate (Ideogram)**: Creates realistic images from text
- **ElevenLabs**: Converts text to natural speech
- **AssemblyAI**: Generates accurate captions from audio
- **Remotion**: Renders final videos programmatically

### Database & Infrastructure
- **PostgreSQL**: Stores user data and video information
- **Prisma**: Database toolkit and ORM
- **AWS S3**: Stores generated images, audio, and videos
- **Redis**: Manages background job processing
- **BullMQ**: Handles video generation queue

### Payment Processing
- **Stripe**: Secure payment processing for credits

## 📋 Prerequisites

Before setting up this project, you'll need accounts and API keys for:

1. **Database**: PostgreSQL database (we recommend [Neon](https://neon.tech/) or [Supabase](https://supabase.com/))
2. **OpenAI**: For script generation ([Get API key](https://platform.openai.com/api-keys))
3. **Replicate**: For image generation ([Get API key](https://replicate.com/account/api-tokens))
4. **ElevenLabs**: For voice synthesis ([Get API key](https://elevenlabs.io/))
5. **AssemblyAI**: For caption generation ([Get API key](https://www.assemblyai.com/))
6. **AWS S3**: For file storage ([Setup guide](https://aws.amazon.com/s3/))
7. **Upstash Redis**: For job queue ([Get started](https://upstash.com/))
8. **Stripe**: For payments ([Get API keys](https://dashboard.stripe.com/apikeys))
9. **Clerk**: For authentication ([Get started](https://clerk.com/))

## 🔧 Installation & Setup

### 1. Clone and Install
```bash
git clone https://github.com/subhrajitMukherje/AI-shorts-generator.git
cd ai-video-generator
npm install
```

### 2. Environment Configuration
Copy the example environment file and fill in your API keys:
```bash
cp .env.example .env
```

Fill in all the required environment variables in `.env`:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Database
DATABASE_URL=your_postgresql_connection_string
DIRECT_URL=your_direct_postgresql_connection_string

# AI Services
OPENAI_API_KEY=your_openai_api_key
REPLICATE_API_TOKEN=your_replicate_token
ELEVENLABS_API_KEY=your_elevenlabs_key
ASSEMBLY_API_KEY=your_assemblyai_key

# AWS S3 Storage
AWS_REGION=your_aws_region
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
S3_BUCKET_NAME=your_s3_bucket_name

# Remotion (for video rendering)
REMOTION_AWS_ACCESS_KEY_ID=your_remotion_aws_key
REMOTION_AWS_SECRET_ACCESS_KEY=your_remotion_aws_secret

# Stripe Payments
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

# Redis Queue
UPSTASH_REDIS_HOST=your_redis_host
UPSTASH_REDIS_PORT=your_redis_port
UPSTASH_REDIS_PASSWORD=your_redis_password
```

### 3. Database Setup
```bash
# Generate Prisma client
npx prisma generate

# Run database migrations
npx prisma db push
```

### 4. Start the Application
```bash
# Start the web application
npm run dev

# In a separate terminal, start the background worker
npm run worker:dev
```

The app will be available at `http://localhost:3000`

## 📁 Project Structure

```
├── app/                    # Next.js app directory
│   ├── (auth)/            # Authentication pages
│   ├── actions/           # Server actions for AI processing
│   ├── api/               # API routes
│   ├── components/        # Reusable UI components
│   ├── dashboard/         # User dashboard
│   ├── lib/               # Utility functions
│   ├── new/               # Video creation page
│   ├── pricing/           # Pricing page
│   ├── remotion/          # Video composition components
│   └── videos/            # Video viewing pages
├── components/            # Shared UI components
├── lib/                   # Utility functions
├── prisma/                # Database schema
├── worker/                # Background job processor
└── public/                # Static assets
```

## 🎮 Usage Guide

### For Users
1. **Sign Up**: Create an account using email or social login
2. **Get Credits**: Purchase credits through the pricing page
3. **Create Video**: Enter your idea and let AI do the work
4. **Download & Share**: Get your finished video in MP4 format

### For Developers
1. **Video Creation Flow**: `prompt → script → images → audio → captions → video`
2. **Background Processing**: Videos are processed asynchronously using Redis queues
3. **File Storage**: All assets are stored in AWS S3 for reliability
4. **User Management**: Clerk handles authentication and user sessions

## 🔄 Video Generation Process

1. **Script Generation**: OpenAI creates a detailed script with scene descriptions
2. **Image Creation**: Replicate generates realistic images for each scene
3. **Audio Production**: ElevenLabs converts script to natural speech
4. **Caption Generation**: AssemblyAI creates synchronized subtitles
5. **Video Assembly**: Remotion combines everything into a final video

## 💰 Credit System

- **1 Credit = 1 Video**
- **Starter Plan**: $1 for 1 video
- **Pro Plan**: $20 for 25 videos (most popular)
- **Enterprise Plan**: $99 for 150 videos

## 🚀 Deployment

### Prerequisites for Production
- Set up all required external services
- Configure production database
- Set up AWS S3 bucket with proper permissions
- Configure Stripe webhooks
- Set up Redis instance

### Environment Setup
Make sure all environment variables are properly configured in your production environment.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📞 Support

If you encounter any issues:
1. Check that all environment variables are correctly set
2. Ensure all external services are properly configured
3. Check the console for error messages
4. Verify your API keys have sufficient credits/quota

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- OpenAI for powerful language models
- Replicate for image generation capabilities
- ElevenLabs for realistic voice synthesis
- AssemblyAI for accurate transcription
- Remotion for programmatic video creation

---

**Ready to create amazing videos?** Start by setting up your environment variables and running the development server!
