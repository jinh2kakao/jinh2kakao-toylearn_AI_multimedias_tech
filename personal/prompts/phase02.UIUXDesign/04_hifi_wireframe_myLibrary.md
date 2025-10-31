
## Prompts

```
[SCENE] A high-resolution UI mockup for the 'My Prompt Library' page. This page is for user-created prompts. Dark mode.

[DESIGN SYSTEM CONTEXT] Must strictly adhere to the established design system (Dark mode #1E1E24, Accent #007AFF, LNB Glassmorphism, Top Bar blur, Input style bg-[#2A2A32]).

[LAYOUT] Identical LNB, Top Bar, and Main Content padding (px-8 py-8) as the 'Explore' page.

[ELEMENTS]

Page Header: A flex row with justify-between and items-center.

Left: h1 "My Prompt Library" (text-white text-3xl) and p "Create, edit, and manage your custom prompts" (text-gray-400).

Right: A Primary CTA Button. Text: "Create New Prompt". Style: bg-[#007AFF], text-white, rounded-xl, py-2 px-4, hover:bg-[#007AFF]/90.

Content Grid: A standard 3-column grid displaying user-created PromptCard components.

Card Variants: The PromptCards in this grid should have 'Edit' and 'Delete' icons visible on hover (using text-gray-400).

Empty State: If no prompts are created, display a centered empty state:

A large, faded <Zap> icon (text-gray-600, size 64px).

h3 text below: "Your library is empty." (text-white).

A Primary CTA Button below: "Create New Prompt" (matching the header button style).

[STATE]

In the LNB, the <Zap> icon is 'active': bg-[#007AFF]/20 background and text-[#007AFF] color.

All other LNB icons are 'idle' (text-gray-400).
```

## Output

I'll create the "My Prompt Library" page with the user-created prompts functionality, edit/delete controls, and proper empty state.

Perfect! I've created the complete "My Prompt Library" page with all the requested features:



✅ Design System - Matches the Explore page:

Background: Deep charcoal (#1E1E24)
Primary accent: Intelligent blue (#007AFF)
Consistent glassmorphism LNB and top bar styling


✅ Page Header with flex row layout:

Left side: "My Prompt Library" (text-white text-3xl) with subtitle "Create, edit, and manage your custom prompts"
Right side: "Create New Prompt" primary CTA button (bg-[#007AFF], hover:bg-[#007AFF]/90)


✅ Content Grid:

Standard 3-column grid layout
Custom `LibraryPromptCard` component with Edit and Delete icons that appear on hover (text-gray-400)


✅ Empty State:

Large faded Zap icon (w-16 h-16, text-gray-600)
h3 "Your library is empty."
"Create New Prompt" primary CTA button


✅ Navigation State:

Zap icon in LNB is active (bg-[#007AFF]/20, text-[#007AFF]) when on the Library page
All other icons are idle (text-gray-400)


The implementation includes:

`/myLibrary.tsx` - Standalone page with full layout
`/components/MyLibrary.tsx` - Reusable component for App.tsx integration
`/components/LibraryPromptCard.tsx` - Card variant with Edit/Delete functionality
Updated `/App.tsx` - Now supports three pages: Explore, Saved, and Library


Click the Zap icon in the navigation to view the My Prompt Library page!

```
import { Search, Sparkles, BookOpen, Star, Zap, TrendingUp, User, Settings } from 'lucide-react';
import { LibraryPromptCard } from './components/LibraryPromptCard';

// Sample data - in a real app, this would come from a database or API
const userPrompts: Array<{
  id: number;
  title: string;
  description: string;
  category: string;
  isPro: boolean;
  likes: number;
  saves: number;
}> = []; // Empty array to show empty state

export default function MyLibrary() {
  const handleCreatePrompt = () => {
    console.log('Create new prompt');
    // Add create prompt logic here
  };

  const handleEditPrompt = (id: number) => {
    console.log('Edit prompt:', id);
    // Add edit logic here
  };

  const handleDeletePrompt = (id: number) => {
    console.log('Delete prompt:', id);
    // Add delete logic here
  };

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
          
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <Star className="w-5 h-5 text-gray-400" strokeWidth={2} />
          </button>
          
          {/* Zap icon is ACTIVE on this page */}
          <button className="w-10 h-10 rounded-xl bg-[#007AFF]/20 flex items-center justify-center transition-all">
            <Zap className="w-5 h-5 text-[#007AFF]" strokeWidth={2} />
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
          <div className="flex items-center justify-between mb-6">
            <div>
              <h1 className="text-white text-3xl mb-2">My Prompt Library</h1>
              <p className="text-gray-400">Create, edit, and manage your custom prompts</p>
            </div>
            <button
              onClick={handleCreatePrompt}
              className="bg-[#007AFF] text-white rounded-xl py-2 px-4 hover:bg-[#007AFF]/90 transition-colors"
            >
              Create New Prompt
            </button>
          </div>

          {/* Content */}
          {userPrompts.length > 0 ? (
            /* 3-Column Grid */
            <div className="grid grid-cols-3 gap-6">
              {userPrompts.map((prompt) => (
                <LibraryPromptCard
                  key={prompt.id}
                  title={prompt.title}
                  description={prompt.description}
                  category={prompt.category}
                  isPro={prompt.isPro}
                  likes={prompt.likes}
                  saves={prompt.saves}
                  onEdit={() => handleEditPrompt(prompt.id)}
                  onDelete={() => handleDeletePrompt(prompt.id)}
                />
              ))}
            </div>
          ) : (
            /* Empty State */
            <div className="flex flex-col items-center justify-center py-32">
              <Zap className="w-16 h-16 text-gray-600 mb-6" strokeWidth={1.5} />
              <h3 className="text-white mb-4">Your library is empty.</h3>
              <button
                onClick={handleCreatePrompt}
                className="bg-[#007AFF] text-white rounded-xl py-2 px-4 hover:bg-[#007AFF]/90 transition-colors"
              >
                Create New Prompt
              </button>
            </div>
          )}
        </main>
      </div>
    </div>
  );
}

```