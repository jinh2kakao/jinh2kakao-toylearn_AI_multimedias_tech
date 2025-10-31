
## Prompts
```
[SCENE] A high-resolution UI mockup for the 'Settings' page. Dark mode.

[DESIGN SYSTEM CONTEXT] Must strictly adhere to the established design system (Dark mode #1E1E24, Accent #007AFF, LNB Glassmorphism, Top Bar blur).

[LAYOUT]

Identical LNB and Top Bar.

Main Content: px-8 py-8.

Page Layout: A two-column layout.

Left Column (Sub-navigation): w-1/4. A vertical list of navigation items.

Right Column (Content Area): w-3/4. Displays the content for the selected sub-nav item.

[ELEMENTS]

Page Header: h1 "Settings" (text-white text-3xl).

Sub-navigation (Left Column):

Items: "Appearance", "API Keys", "Notifications".

'Idle' Style: text-gray-400, hover:text-white, py-2 px-3 rounded-lg.

'Active' Style (e.g., 'Appearance'): text-white, bg-[#2A2A32].

Content Area (Right Column - for 'Appearance'):

Section Title: h3 "Appearance" (text-white).

Option: "Theme".

Option Controls: Show two cards for 'Light Mode' (disabled) and 'Dark Mode' (active). The active card has a blue border border-[#007AFF].

[STATE]

In the LNB, the <Settings> icon is 'active': bg-[#007AFF]/20 background and text-[#007AFF] color.

All other LNB icons are 'idle' (text-gray-400).
```

## Output

I'll create the "Settings" page with a two-column layout, sub-navigation, and appearance settings with theme cards.

Perfect! I've successfully created the "Settings" page with all the requested features:



✅ Design System - Matches existing pages:

Background: Deep charcoal (#1E1E24)
Primary accent: Intelligent blue (#007AFF)
Consistent glassmorphism LNB and top bar styling
Identical padding (px-8 py-8)


✅ Two-Column Layout:

Left column (w-1/4): Sub-navigation menu
Right column (w-3/4): Content area


✅ Sub-navigation (Left Column):

Three items: "Appearance", "API Keys", "Notifications"
Idle style: text-gray-400, hover:text-white
Active style: text-white, bg-[#2A2A32] (defaulted to "Appearance")


✅ Content Area - Appearance Section:

Section title: "Appearance" (h3, text-white)
Theme option with two cards:
Light Mode: Disabled/grayed out with "Coming soon" label
Dark Mode: Active with blue border (border-[#007AFF]) and check icon


✅ Navigation State:

Settings icon in LNB is active (bg-[#007AFF]/20, text-[#007AFF]) when on Settings page
All other icons are idle (text-gray-400)


The implementation includes:

`/setting.tsx` - Standalone page with full layout
`/components/Settings.tsx` - Reusable component for App.tsx integration
Updated `/App.tsx` - Now supports five pages: Explore, Saved, Library, Trending, and Settings


Click the Settings icon (gear) in the bottom navigation to view the Settings page with the appearance controls and sub-navigation tabs!

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
import { Settings as SettingsPage } from "./components/Settings";
import { useState } from "react";

export default function App() {
  const [currentPage, setCurrentPage] = useState<
    "explore" | "saved" | "library" | "trending" | "settings"
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
          <button
            onClick={() => setCurrentPage("settings")}
            className={`w-10 h-10 rounded-xl flex items-center justify-center transition-all ${
              currentPage === "settings"
                ? "bg-[#007AFF]/20"
                : "hover:bg-white/10"
            }`}
          >
            <Settings
              className={`w-5 h-5 ${currentPage === "settings" ? "text-[#007AFF]" : "text-gray-400"}`}
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
          ) : currentPage === "settings" ? (
            <SettingsPage />
          ) : (
            <MyLibrary userPrompts={userPrompts} />
          )}
        </main>
      </div>
    </div>
  );
}
```