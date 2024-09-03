import { Bell, Home, Menu, MessageCircle, Search, Users } from "lucide-react"
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar"
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
import { Textarea } from "@/components/ui/textarea"

export default function FacebookClone() {
  return (
    <div className="min-h-screen bg-gray-100">
      <header className="bg-primary text-primary-foreground p-4 flex items-center justify-between">
        <div className="flex items-center space-x-4">
          <h1 className="text-2xl font-bold">facebook</h1>
          <div className="relative">
            <Search className="absolute left-2 top-1/2 transform -translate-y-1/2 text-gray-400" />
            <Input className="pl-8 bg-primary-foreground text-primary" placeholder="Search Facebook" />
          </div>
        </div>
        <nav className="flex items-center space-x-4">
          <Button variant="ghost" size="icon">
            <Home className="h-5 w-5" />
          </Button>
          <Button variant="ghost" size="icon">
            <Users className="h-5 w-5" />
          </Button>
          <Button variant="ghost" size="icon">
            <MessageCircle className="h-5 w-5" />
          </Button>
          <Button variant="ghost" size="icon">
            <Bell className="h-5 w-5" />
          </Button>
          <Avatar>
            <AvatarImage src="/placeholder.svg?height=32&width=32" alt="User" />
            <AvatarFallback>U</AvatarFallback>
          </Avatar>
        </nav>
      </header>
      <main className="container mx-auto mt-4 grid grid-cols-[250px_1fr] gap-4">
        <aside>
          <nav className="space-y-2">
            <Button variant="ghost" className="w-full justify-start">
              <Home className="mr-2 h-4 w-4" />
              Home
            </Button>
            <Button variant="ghost" className="w-full justify-start">
              <Users className="mr-2 h-4 w-4" />
              Friends
            </Button>
            <Button variant="ghost" className="w-full justify-start">
              <Menu className="mr-2 h-4 w-4" />
              More
            </Button>
          </nav>
        </aside>
        <section>
          <div className="bg-background p-4 rounded-lg shadow mb-4">
            <Textarea placeholder="What's on your mind?" />
            <div className="mt-2 flex justify-end">
              <Button>Post</Button>
            </div>
          </div>
          <div className="space-y-4">
            {[1, 2, 3].map((post) => (
              <div key={post} className="bg-background p-4 rounded-lg shadow">
                <div className="flex items-center space-x-2 mb-2">
                  <Avatar>
                    <AvatarImage src={`/placeholder.svg?height=32&width=32&text=User${post}`} alt={`User ${post}`} />
                    <AvatarFallback>U{post}</AvatarFallback>
                  </Avatar>
                  <div>
                    <p className="font-semibold">User {post}</p>
                    <p className="text-sm text-gray-500">2 hours ago</p>
                  </div>
                </div>
                <p>This is a sample post content. It can be much longer and include more details.</p>
                <div className="mt-2 flex items-center space-x-2">
                  <Button variant="ghost" size="sm">Like</Button>
                  <Button variant="ghost" size="sm">Comment</Button>
                  <Button variant="ghost" size="sm">Share</Button>
                </div>
              </div>
            ))}
          </div>
        </section>
      </main>
    </div>
  )
}
