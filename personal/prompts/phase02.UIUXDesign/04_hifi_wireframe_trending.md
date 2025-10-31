
## Prompts
```
[SCENE] A high-resolution UI mockup for the 'Trending Prompts' page. Dark mode.

[DESIGN SYSTEM CONTEXT] Must strictly adhere to the established design system (Dark mode #1E1E24, Accent #007AFF, LNB Glassmorphism, Top Bar blur, Card styles).

[LAYOUT] Identical LNB, Top Bar, and Main Content padding (px-8 py-8) as the 'Explore' page. The content area must use the Masonry Grid just like the 'Explore' page.

[ELEMENTS]

Page Header: h1 "Trending Now" (text-white text-3xl) and p "The most popular and fastest-growing prompts" (text-gray-400).

Filter Tabs: Below the header, show a row of filter pills:

Options: "Today", "This Week", "This Month", "All Time".

'Idle' Style: bg-[#2A2A32], text-gray-400, rounded-full, py-1 px-3.

'Active' Style (e.g., 'This Week'): bg-[#007AFF]/20, text-[#007AFF].

Content Grid: A 3-column Masonry Grid (identical to 'Explore') filled with PromptCard components. The cards should prominently display stats (likes, saves).

[STATE]

In the LNB, the <TrendingUp> icon is 'active': bg-[#007AFF]/20 background and text-[#007AFF] color.

All other LNB icons are 'idle' (text-gray-400).
```

## Output
```
import {
  Search,
  Sparkles,
  BookOpen,
  Star,
  Zap,
  TrendingUp,
  User,
  Settings,
} from "lucide-react";
import { ExplorePage } from "./components/ExplorePage";
import { SavedPrompts } from "./components/SavedPrompts";
import { MyLibrary } from "./components/MyLibrary";
import { Trending } from "./components/Trending";
import { useState } from "react";

export default function App() {
  const [currentPage, setCurrentPage] = useState<
    "explore" | "saved" | "library" | "trending"
  >("explore");
  const [savedPrompts] = useState<any[]>([]); // Empty for demo - can add prompts here
  const [userPrompts] = useState<any[]>([]); // Empty for demo - user created prompts

  return (
    <div className="flex h-screen bg-[#1E1E24] overflow-hidden">
      {/* Glassmorphism Sidebar */}
      <nav className="w-[60px] relative flex flex-col items-center py-6 gap-6 backdrop-blur-xl bg-white/5 border-r border-white/10">
        {/* Glass effect overlay */}
        <div className="absolute inset-0 bg-gradient-to-br from-white/10 to-transparent pointer-events-none"></div>

        <div className="relative z-10 flex flex-col items-center gap-6 w-full">
          {/* Logo */}
          <div className="w-10 h-10 rounded-xl bg-[#007AFF] flex items-center justify-center">
            <Sparkles
              className="w-5 h-5 text-white"
              strokeWidth={2}
            />
          </div>

          {/* Navigation Icons */}
          <button
            onClick={() => setCurrentPage("explore")}
            className={`w-10 h-10 rounded-xl flex items-center justify-center transition-all ${
              currentPage === "explore"
                ? "bg-[#007AFF]/20"
                : "hover:bg-white/10"
            }`}
          >
            <BookOpen
              className={`w-5 h-5 ${currentPage === "explore" ? "text-[#007AFF]" : "text-gray-400"}`}
              strokeWidth={2}
            />
          </button>

          <button
            onClick={() => setCurrentPage("saved")}
            className={`w-10 h-10 rounded-xl flex items-center justify-center transition-all ${
              currentPage === "saved"
                ? "bg-[#007AFF]/20"
                : "hover:bg-white/10"
            }`}
          >
            <Star
              className={`w-5 h-5 ${currentPage === "saved" ? "text-[#007AFF]" : "text-gray-400"}`}
              strokeWidth={2}
            />
          </button>

          <button
            onClick={() => setCurrentPage("library")}
            className={`w-10 h-10 rounded-xl flex items-center justify-center transition-all ${
              currentPage === "library"
                ? "bg-[#007AFF]/20"
                : "hover:bg-white/10"
            }`}
          >
            <Zap
              className={`w-5 h-5 ${currentPage === "library" ? "text-[#007AFF]" : "text-gray-400"}`}
              strokeWidth={2}
            />
          </button>

          <button
            onClick={() => setCurrentPage("trending")}
            className={`w-10 h-10 rounded-xl flex items-center justify-center transition-all ${
              currentPage === "trending"
                ? "bg-[#007AFF]/20"
                : "hover:bg-white/10"
            }`}
          >
            <TrendingUp
              className={`w-5 h-5 ${currentPage === "trending" ? "text-[#007AFF]" : "text-gray-400"}`}
              strokeWidth={2}
            />
          </button>
        </div>

        {/* Bottom Icons */}
        <div className="relative z-10 mt-auto flex flex-col items-center gap-4 w-full">
          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <Settings
              className="w-5 h-5 text-gray-400"
              strokeWidth={2}
            />
          </button>

          <button className="w-10 h-10 rounded-xl flex items-center justify-center hover:bg-white/10 transition-all">
            <User
              className="w-5 h-5 text-gray-400"
              strokeWidth={2}
            />
          </button>
        </div>
      </nav>

      {/* Main Content */}
      <div className="flex-1 flex flex-col overflow-hidden">
        {/* Top Bar */}
        <header className="h-16 flex items-center px-8 border-b border-gray-800 backdrop-blur-sm bg-[#1E1E24]/80">
          <div className="flex-1 max-w-2xl">
            <div className="relative">
              <Search
                className="absolute left-4 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-500"
                strokeWidth={2}
              />
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
          {currentPage === "explore" ? (
            <ExplorePage />
          ) : currentPage === "saved" ? (
            <SavedPrompts savedPrompts={savedPrompts} />
          ) : currentPage === "trending" ? (
            <Trending />
          ) : (
            <MyLibrary userPrompts={userPrompts} />
          )}
        </main>
      </div>
    </div>
  );
}
```