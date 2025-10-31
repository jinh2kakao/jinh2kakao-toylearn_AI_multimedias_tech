## Prompts
```
Create a low-fidelity wireframe for a desktop dashboard.
It must have:
1. A thin, icon-only left navigation bar (LNB).
2. A global search bar at the top.
3. A main content area using a **simple 3-column card grid**.
4. A 'filter' button next to the search bar.
Keep it purely structural, no colors or images.

Please generate a single HTML file.
Put all the CSS code inside a <style> tag within the <head> section.
Put all the HTML content inside the <body> section.
```

## Output
```
import { Search, Home, FileText, BarChart3, Settings, User, Filter } from 'lucide-react';

export default function App() {
  return (
    <div className="flex h-screen bg-white">
      {/* Left Navigation Bar - Icon Only */}
      <nav className="w-16 border-r-2 border-gray-400 flex flex-col items-center py-6 gap-8">
        <div className="w-10 h-10 border-2 border-gray-400 flex items-center justify-center">
          <Home className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
        </div>
        <div className="w-10 h-10 border-2 border-gray-400 flex items-center justify-center">
          <FileText className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
        </div>
        <div className="w-10 h-10 border-2 border-gray-400 flex items-center justify-center">
          <BarChart3 className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
        </div>
        <div className="w-10 h-10 border-2 border-gray-400 flex items-center justify-center">
          <Settings className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
        </div>
        <div className="mt-auto w-10 h-10 border-2 border-gray-400 flex items-center justify-center">
          <User className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
        </div>
      </nav>

      {/* Main Content Area */}
      <div className="flex-1 flex flex-col">
        {/* Top Search Bar */}
        <header className="h-16 border-b-2 border-gray-400 flex items-center px-6 gap-4">
          <div className="flex-1 h-10 border-2 border-gray-400 flex items-center px-4 gap-2">
            <Search className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
            <span className="text-gray-400">Search</span>
          </div>
          <button className="h-10 px-6 border-2 border-gray-400 flex items-center gap-2 hover:bg-gray-50">
            <Filter className="w-5 h-5 stroke-gray-400" strokeWidth={2} />
            <span className="text-gray-400">Filter</span>
          </button>
        </header>

        {/* Main Content - 3 Column Card Grid */}
        <main className="flex-1 p-6 overflow-auto">
          <div className="grid grid-cols-3 gap-6">
            {Array.from({ length: 12 }).map((_, index) => (
              <div key={index} className="border-2 border-gray-400 p-6 h-48">
                <div className="h-6 w-3/4 border-2 border-gray-300 mb-4"></div>
                <div className="h-4 w-full border border-gray-300 mb-2"></div>
                <div className="h-4 w-5/6 border border-gray-300 mb-2"></div>
                <div className="h-4 w-4/6 border border-gray-300"></div>
              </div>
            ))}
          </div>
        </main>
      </div>
    </div>
  );
}

```