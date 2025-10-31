
## Prompts
```
Turn this element into a new component named 'Button-Primary'. Then, create 3 variants:

'Hover' state with 90% opacity.

'Disabled' state with gray background ($#555555$) and lighter text.

'Secondary' variant with a blue outline ($#007AFF$) and transparent background.
```

## Output
```
import { Search, Sparkles, BookOpen, Star, Zap, TrendingUp, User, Settings } from 'lucide-react';
import Masonry from 'react-responsive-masonry';
import { PromptCard } from './components/PromptCard';
import { ButtonPrimary } from './components/Button-Primary';

const prompts = [
  {
    id: 1,
    title: 'Blog Post Generator',
    description: 'Create engaging blog posts with SEO optimization. Include relevant keywords, compelling headlines, and a clear call-to-action.',
    category: 'Content Writing',
    isPro: false,
    likes: 234,
    saves: 89,
  },
  {
    id: 2,
    title: 'Advanced Data Analysis',
    description: 'Perform comprehensive data analysis with statistical insights, trend identification, and predictive modeling. Generate visualizations and actionable recommendations based on complex datasets.',
    category: 'Analytics',
    isPro: true,
    likes: 512,
    saves: 201,
  },
  {
    id: 3,
    title: 'Social Media Caption',
    description: 'Write catchy social media captions that drive engagement and increase reach.',
    category: 'Marketing',
    isPro: false,
    likes: 189,
    saves: 67,
  },
  {
    id: 4,
    title: 'Code Review Assistant',
    description: 'Comprehensive code review covering best practices, security vulnerabilities, performance optimizations, and maintainability improvements. Includes detailed explanations and refactoring suggestions.',
    category: 'Development',
    isPro: true,
    likes: 678,
    saves: 312,
  },
  {
    id: 5,
    title: 'Email Subject Lines',
    description: 'Craft compelling email subject lines that improve open rates.',
    category: 'Marketing',
    isPro: false,
    likes: 156,
    saves: 43,
  },
  {
    id: 6,
    title: 'Product Description',
    description: 'Generate persuasive product descriptions that highlight features and benefits to convert browsers into buyers.',
    category: 'E-commerce',
    isPro: false,
    likes: 298,
    saves: 112,
  },
  {
    id: 7,
    title: 'API Documentation Generator',
    description: 'Create professional API documentation with endpoint descriptions, parameter specifications, example requests and responses, authentication details, and error handling guides.',
    category: 'Development',
    isPro: true,
    likes: 445,
    saves: 178,
  },
  {
    id: 8,
    title: 'Meeting Notes Summarizer',
    description: 'Transform lengthy meeting transcripts into concise, actionable summaries.',
    category: 'Productivity',
    isPro: false,
    likes: 321,
    saves: 145,
  },
  {
    id: 9,
    title: 'SEO Meta Tags',
    description: 'Generate optimized meta titles and descriptions for better search rankings.',
    category: 'SEO',
    isPro: false,
    likes: 267,
    saves: 98,
  },
  {
    id: 10,
    title: 'UX Research Synthesizer',
    description: 'Analyze user research data, identify patterns, extract key insights, create user personas, and generate actionable recommendations for product improvements.',
    category: 'UX Design',
    isPro: true,
    likes: 589,
    saves: 234,
  },
  {
    id: 11,
    title: 'Tweet Thread Creator',
    description: 'Build engaging Twitter threads that tell a compelling story.',
    category: 'Social Media',
    isPro: false,
    likes: 412,
    saves: 167,
  },
  {
    id: 12,
    title: 'Brand Voice Generator',
    description: 'Define and maintain consistent brand voice across all communications.',
    category: 'Branding',
    isPro: false,
    likes: 198,
    saves: 76,
  },
  {
    id: 13,
    title: 'Financial Report Analyzer',
    description: 'Deep dive into financial statements, identify trends, calculate key metrics, assess financial health, and provide investment recommendations with risk analysis.',
    category: 'Finance',
    isPro: true,
    likes: 734,
    saves: 289,
  },
  {
    id: 14,
    title: 'Video Script Writer',
    description: 'Create engaging video scripts with hooks, storytelling elements, and clear messaging.',
    category: 'Video Content',
    isPro: false,
    likes: 345,
    saves: 134,
  },
  {
    id: 15,
    title: 'Landing Page Copy',
    description: 'Write high-converting landing page copy that drives action.',
    category: 'Copywriting',
    isPro: false,
    likes: 423,
    saves: 189,
  },
];

export default function App() {
  return (
    <div className="flex h-screen bg-[#1E1E24] overflow-hidden">
      {/* Glassmorphism Sidebar */}
      <nav className="w-[60px] relative flex flex-col items-center py-6 gap-6 backdrop-blur-xl bg-white/5 border-r border-white/10">
        {/* Glass effect overlay */}
        <div className="absolute inset-0 bg-gradient-to-br from-white/10 to-transparent pointer-events-none"></div>
        
        <div className="relative z-10 flex flex-col items-center gap-6 w-full">
          {/* Logo */}
          <div className="w-10 h-10 rounded-xl bg-[#007AFF] flex items-center justify-center">
            <Sparkles className="w-5 h-5 text-white" strokeWidth={2} />
          </div>
          
          {/* Navigation Icons */}
          <button className="w-10 h-10 rounded-xl bg-[#007AFF]/20 flex items-center justify-center hover:bg-[#007AFF]/30 transition-all">
            <BookOpen className="w-5 h-5 text-[#007AFF]" strokeWidth={2} />
          </button>
          
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <Star className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
          
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <Zap className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
          
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <TrendingUp className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
        </div>

        {/* Bottom Icons */}
        <div className="relative z-10 mt-auto flex flex-col items-center gap-4 w-full">
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <Settings className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
          
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <User className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
        </div>
      </nav>

      {/* Main Content */}
      <div className="flex-1 flex flex-col overflow-hidden">
        {/* Top Bar */}
        <header className="h-16 flex items-center px-8 border-b border-gray-800 backdrop-blur-sm bg-[#1E1E24]/80">
          <div className="flex-1 max-w-2xl">
            <div className="relative">
              <Search className="absolute left-4 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-500" strokeWidth={2} />
              <input
                type="text"
                placeholder="Search prompts..."
                className="w-full h-11 pl-12 pr-4 bg-[#2A2A32] border border-gray-800 rounded-xl text-white placeholder-gray-500 focus:outline-none focus:border-[#007AFF] transition-colors"
              />
            </div>
          </div>
        </header>

        {/* Masonry Grid Content */}
        <main className="flex-1 overflow-y-auto px-8 py-8">
          <div className="mb-6">
            <h1 className="text-white text-3xl mb-2">Explore Prompts</h1>
            <p className="text-gray-400">Discover and use AI prompts crafted by the community</p>
          </div>

          {/* Button Variants Demo */}
          <div className="mb-8 p-6 bg-[#2A2A32] rounded-xl border border-gray-800">
            <h2 className="text-white mb-4">Button-Primary Component Variants</h2>
            <div className="flex flex-wrap gap-4">
              <div className="flex flex-col gap-2">
                <span className="text-xs text-gray-400">Primary</span>
                <ButtonPrimary>Primary Button</ButtonPrimary>
              </div>
              <div className="flex flex-col gap-2">
                <span className="text-xs text-gray-400">Primary Hover (90% opacity)</span>
                <ButtonPrimary className="opacity-90">Hover State</ButtonPrimary>
              </div>
              <div className="flex flex-col gap-2">
                <span className="text-xs text-gray-400">Primary Disabled</span>
                <ButtonPrimary disabled>Disabled Button</ButtonPrimary>
              </div>
              <div className="flex flex-col gap-2">
                <span className="text-xs text-gray-400">Secondary</span>
                <ButtonPrimary variant="secondary">Secondary Button</ButtonPrimary>
              </div>
              <div className="flex flex-col gap-2">
                <span className="text-xs text-gray-400">Secondary Disabled</span>
                <ButtonPrimary variant="secondary" disabled>Disabled Secondary</ButtonPrimary>
              </div>
            </div>
          </div>

          <Masonry columnsCount={3} gutter="24px">
            {prompts.map((prompt) => (
              <PromptCard
                key={prompt.id}
                title={prompt.title}
                description={prompt.description}
                category={prompt.category}
                isPro={prompt.isPro}
                likes={prompt.likes}
                saves={prompt.saves}
              />
            ))}
          </Masonry>
        </main>
      </div>
    </div>
  );
}
```