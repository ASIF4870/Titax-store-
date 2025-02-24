import React from "react";
import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Search, ShoppingCart, Bot, Shield } from "lucide-react";

const TitaxStore = () => {
  const [darkMode, setDarkMode] = useState(false);
  const [searchQuery, setSearchQuery] = useState("");
  const [isSecure, setIsSecure] = useState(true);

  const handleAIAssistant = () => {
    alert("AI Assistant is coming soon!");
  };

  const enableSecurity = () => {
    alert("Security Enabled: Protection against hacking activated!");
    setIsSecure(true);
  };

  return (
    <div className={darkMode ? "bg-gray-900 text-white" : "bg-white text-black"}>
      <header className="p-4 flex justify-between items-center border-b">
        <h1 className="text-2xl font-bold">Welcome to Titax Store</h1>
        <div className="flex gap-2">
          <Input
            type="text"
            placeholder="Search..."
            value={searchQuery}
            onChange={(e) => setSearchQuery(e.target.value)}
            className="border rounded p-2"
          />
          <Button variant="outline">
            <Search size={20} />
          </Button>
          <Button variant="outline">
            <ShoppingCart size={20} />
          </Button>
          <Button onClick={() => setDarkMode(!darkMode)}>Toggle Theme</Button>
          <Button variant="outline" onClick={handleAIAssistant}>
            <Bot size={20} /> AI Assistant
          </Button>
          <Button variant="outline" onClick={enableSecurity}>
            <Shield size={20} /> Enable Security
          </Button>
        </div>
      </header>
      <main className="p-4">
        <h2 className="text-xl font-semibold">Featured Products</h2>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-4 mt-4">
          {/* Product Cards Placeholder */}
          <div className="p-4 border rounded-lg">Product 1</div>
          <div className="p-4 border rounded-lg">Product 2</div>
          <div className="p-4 border rounded-lg">Product 3</div>
          <div className="p-4 border rounded-lg">Product 4</div>
        </div>
      </main>
    </div>
  );
};

export default TitaxStore;
