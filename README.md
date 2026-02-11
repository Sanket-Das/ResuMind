# Resumind - AI Resume Analyzer

An intelligent resume analysis platform that provides AI-powered feedback and ATS (Applicant Tracking System) scoring to help job seekers optimize their resumes for specific job applications.

## Overview

Resumind analyzes your resume against job descriptions using Claude AI, providing detailed feedback across multiple dimensions including ATS compatibility, content quality, structure, tone, and skills alignment. The application runs entirely in the browser with serverless backend capabilities powered by Puter.js.

## Features

- **Browser-Based Authentication** - Secure sign-in powered by Puter.js with no backend setup required
- **Resume Upload & Storage** - Drag-and-drop PDF upload with cloud storage
- **AI-Powered Analysis** - Claude 3.7 Sonnet analyzes resumes against job descriptions
- **ATS Scoring** - Get a 0-100 score on how well your resume performs with Applicant Tracking Systems
- **Multi-Dimensional Feedback** - Detailed scoring across 5 categories:
  - ATS Compatibility
  - Tone & Style
  - Content Quality
  - Structure & Formatting
  - Skills Alignment
- **Visual Score Display** - Animated gauges and badges for easy score interpretation
- **Resume Management** - Track multiple resume submissions and their feedback
- **PDF Preview** - Automatic conversion of resume to image for quick preview
- **Responsive Design** - Works seamlessly across desktop, tablet, and mobile devices

## Tech Stack

- **React 19** - Modern React with hooks and concurrent features
- **React Router v7** - File-based routing with data loaders and SSR support
- **TypeScript** - Type-safe development with strict mode enabled
- **Tailwind CSS 4** - Utility-first styling with custom animations
- **Vite** - Lightning-fast build tool and dev server
- **Zustand** - Minimal state management with zero boilerplate
- **Puter.js** - Serverless backend SDK providing:
  - Authentication
  - File storage
  - Key-value database
  - AI services (Claude, GPT, DALL·E, OCR)
- **pdfjs-dist** - Client-side PDF rendering and processing
- **react-dropzone** - Drag-and-drop file upload interface

## Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher)
- [npm](https://www.npmjs.com/) or [pnpm](https://pnpm.io/)
- Modern web browser with JavaScript enabled

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/Sanket-Das/ResuMind.git
cd ai-resume-analyzer
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to:
```
http://localhost:5173
```

## Available Scripts

- `npm run dev` - Start development server with hot module replacement
- `npm run build` - Build production-ready application
- `npm run start` - Start production server
- `npm run typecheck` - Run TypeScript type checking

## Project Structure

```
app/
├── routes/              # Page components
│   ├── home.tsx        # Resume dashboard
│   ├── upload.tsx      # Resume upload & analysis
│   ├── resume.tsx      # Detailed feedback view
│   ├── auth.tsx        # Authentication page
│   └── wipe.tsx        # Data cleanup utility
├── components/         # Reusable UI components
│   ├── ATS.tsx         # ATS score display with suggestions
│   ├── FileUploader.tsx # PDF drag-and-drop uploader
│   ├── ScoreGauge.tsx  # Animated SVG score gauge
│   ├── Summary.tsx     # Overall score summary
│   ├── Details.tsx     # Detailed feedback accordion
│   ├── Navbar.tsx      # Navigation bar
│   ├── ResumeCard.tsx  # Resume list item
│   ├── ScoreBadge.tsx  # Score badge component
│   ├── ScoreCircle.tsx # Score circle display
│   └── Accordion.tsx   # Reusable accordion component
├── lib/
│   ├── puter.ts       # Zustand store for Puter.js API
│   ├── pdf2img.ts     # PDF to PNG conversion utility
│   └── utils.ts       # Helper functions
├── root.tsx           # App layout & error boundary
└── routes.ts          # Route configuration
constants/
└── index.ts           # AI prompt templates & sample data
types/
├── index.d.ts         # TypeScript type definitions
└── puter.d.ts         # Puter.js type definitions
public/
├── icons/             # SVG icons
└── images/            # Static images and backgrounds
```

## How It Works

1. **Authentication** - Users sign in via Puter.js browser-based authentication
2. **Upload Resume** - Users upload a PDF resume and provide job details (company name, job title, job description)
3. **Processing** - The application:
   - Uploads the PDF to Puter cloud storage
   - Converts the first page to PNG for preview
   - Stores resume metadata in Puter's key-value database
4. **AI Analysis** - Claude AI analyzes the resume against the job description using a structured prompt
5. **Feedback Display** - Users receive:
   - Overall ATS score (0-100)
   - Category-specific scores and tips
   - Visual score gauges and badges
   - Actionable improvement suggestions
6. **Resume Management** - All analyzed resumes are saved and accessible from the dashboard

## Key Features Explained

### ATS Scoring
The application evaluates how well your resume will perform with Applicant Tracking Systems used by employers. Scores are categorized as:
- 70-100: Great Job (Green)
- 50-69: Good Start (Yellow)
- 0-49: Needs Improvement (Red)

### AI Feedback Categories
Each resume receives detailed feedback across five dimensions:
- **ATS Compatibility** - Keyword optimization, formatting, and parseability
- **Tone & Style** - Professional language, consistency, and voice
- **Content Quality** - Relevance, achievements, and impact statements
- **Structure & Formatting** - Organization, readability, and visual hierarchy
- **Skills Alignment** - Match between your skills and job requirements

### Serverless Architecture
Puter.js provides a complete backend infrastructure without requiring server setup:
- No API keys or environment variables needed
- User costs borne by the platform
- Automatic scaling and reliability
- Built-in security and privacy

## Browser Compatibility

- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Acknowledgments

- Built with [React Router v7](https://reactrouter.com/)
- Powered by [Puter.js](https://puter.com/) serverless platform
- AI analysis by Claude (Anthropic)
- UI components styled with [Tailwind CSS](https://tailwindcss.com/)
