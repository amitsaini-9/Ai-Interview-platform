# AI Interview

Open-source AI-powered mock interview platform built with Next.js, Supabase, and Google Gemini.

## About

AI Interview helps you prepare for job interviews by simulating real-world interview scenarios with AI-powered interviewers. Practice with different personas including HR managers, tech leads, senior developers, and more. Get instant feedback, real-time guidance, and detailed performance reports after each session.

This project is fully open source. Anyone can clone it, set up their own instance, and start using it. All the services used have generous free tiers.

## Features

- **Real-Time AI Conversations** - Natural interview conversations with follow-up questions that adapt to your answers
- **Multiple Interviewer Personas** - HR, Software Developer, Web Developer, Tech Lead, Fresher/Intern roles
- **Smart Feedback & Guidance** - Real-time hints and tips when you're stuck
- **Detailed Performance Reports** - Post-session analysis covering communication, technical depth, and confidence
- **Voice & Text Input** - Answer questions by typing or speaking
- **Instant Sessions** - No scheduling needed, practice anytime

## Tech Stack

- **Framework**: [Next.js](https://nextjs.org/) 16
- **Authentication & Database**: [Supabase](https://supabase.com/) (free tier available)
- **AI**: [Google Gemini](https://ai.google.dev/) (free tier available)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) 4
- **Animations**: [Framer Motion](https://www.framer.com/motion/)
- **Language**: TypeScript

## Getting Started

### Prerequisites

- Node.js 18+
- A [Supabase](https://supabase.com/) project (free)
- A [Google Gemini API key](https://aistudio.google.com/app/apikey) (free)

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/amitsaini-9/Ai-Interview-platform.git
   cd Ai-Interview-platform
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. **Set up the database**: Run the SQL migrations in order from the `supabase/migrations/` folder in your Supabase SQL Editor:
   - `001_create_profiles.sql` - User profiles table
   - `002_create_interviewers_and_topics.sql` - Interviewer personas and topic categories
   - `003_create_interview_sessions.sql` - Interview session tracking
   - `004_create_session_analyses.sql` - Post-session analysis data
   - `005_storage_buckets.sql` - Storage buckets for audio, transcripts, and avatars

4. Copy the environment example and fill in your credentials:
   ```bash
   cp .env.example .env.local
   ```

   Required environment variables:
   | Variable | Where to find it |
   |---|---|
   | `NEXT_PUBLIC_SUPABASE_URL` | Supabase Dashboard > Project Settings > API |
   | `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Supabase Dashboard > Project Settings > API |
   | `SUPABASE_SERVICE_ROLE_KEY` | Supabase Dashboard > Project Settings > API |
   | `GOOGLE_GEMINI_API_KEY` | [Google AI Studio](https://aistudio.google.com/app/apikey) |

   The Gemini model names in `.env.example` may become deprecated over time. Check the [Gemini documentation](https://ai.google.dev/gemini-api/docs/models) for the latest available models and update accordingly.

5. Run the development server:
   ```bash
   npm run dev
   ```

6. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Project Structure

```
src/
  app/          # Next.js app router pages and layouts
  lib/          # Utility functions and Supabase client
public/         # Static assets
supabase/
  migrations/   # Database schema (run these in order in Supabase SQL Editor)
```

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

## License

MIT
