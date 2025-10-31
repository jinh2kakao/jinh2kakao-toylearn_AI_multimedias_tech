
## prompts
```
[SCENE] A high-resolution UI mockup for the 'My Saved Prompts' page of a desktop web app. Dark mode.

[DESIGN SYSTEM CONTEXT] Must use the exact existing design system from the 'Explore' page:

Background: Deep charcoal (#1E1E24).

Primary Accent: Intelligent blue (#007AFF).

Text: text-white (primary), text-gray-400 (secondary).

Fonts: Modern sans-serif (as defined in 'Explore').

Components: Re-use the PromptCard component style, Top Bar style, and LNB style precisely.

[LAYOUT]

LNB (Left Nav Bar): Identical to 'Explore' page (60px width, Glassmorphism: bg-white/5, backdrop-blur-xl).

Top Bar: Identical to 'Explore' (height 64px, bg-[#1E1E24]/80, border-b border-gray-800), containing the global Search bar (bg-[#2A2A32]).

Main Content: flex-1 overflow-y-auto with px-8 py-8.

[ELEMENTS]

Page Header: h1 "My Saved Prompts" (text-white text-3xl) and p "All the prompts you've saved in one place" (text-gray-400).

Content Grid: A standard 3-column grid (not Masonry) displaying PromptCard components that the user has saved.

Empty State (Crucial): If no prompts are saved, display a centered empty state:

A large, faded <Star> icon (text-gray-600, size 64px).

h3 text below: "You haven't saved any prompts yet." (text-white).

p text below: "Click the save icon on a prompt to add it here." (text-gray-400).

[STATE]

In the LNB, the <Star> icon is 'active': It must have the bg-[#007AFF]/20 background and text-[#007AFF] color.

All other LNB icons (like <BookOpen>) are 'idle' (text-gray-400).
```

## Output
```
import { Search, Sparkles, BookOpen, Star, Zap, TrendingUp, User, Settings } from 'lucide-react';
import { PromptCard } from './components/PromptCard';

// Sample data - in a real app, this would come from a database or API
const savedPrompts: Array<{
  id: number;
  title: string;
  description: string;
  category: string;
  isPro: boolean;
  likes: number;
  saves: number;
}> = []; // Empty array to show empty state

export default function MySavedPrompts() {
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
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <BookOpen className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
          
          {/* Star icon is ACTIVE on this page */}
          <button className="w-10 h-10 rounded-xl bg-[#007AFF]/20 flex items-center justify-center transition-all">
            <Star className="w-5 h-5 text-[#007AFF]" strokeWidth={2} />
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

        {/* Main Content Area */}
        <main className="flex-1 overflow-y-auto px-8 py-8">
          {/* Page Header */}
          <div className="mb-6">
            <h1 className="text-white text-3xl mb-2">My Saved Prompts</h1>
            <p className="text-gray-400">All the prompts you've saved in one place</p>
          </div>

          {/* Content */}
          {savedPrompts.length > 0 ? (
            /* 3-Column Grid */
            <div className="grid grid-cols-3 gap-6">
              {savedPrompts.map((prompt) => (
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
            </div>
          ) : (
            /* Empty State */
            <div className="flex flex-col items-center justify-center py-32">
              <Star className="w-16 h-16 text-gray-600 mb-6" strokeWidth={1.5} />
              <h3 className="text-white mb-2">You haven't saved any prompts yet.</h3>
              <p className="text-gray-400">Click the save icon on a prompt to add it here.</p>
            </div>
          )}
        </main>
      </div>
    </div>
  );
}

```