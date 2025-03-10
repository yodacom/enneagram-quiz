<script>
  import '../app.css';
</script>

<div class="min-h-screen flex flex-col">
  <header class="bg-primary text-white p-4 shadow-md">
    <div class="container mx-auto flex justify-between items-center">
      <a href="/" class="text-2xl font-bold">Enneagram Quiz</a>
      <nav>
        <ul class="flex space-x-6">
          <li><a href="/" class="hover:text-accent">Home</a></li>
          <li><a href="/quiz" class="hover:text-accent">Take Quiz</a></li>
          <li><a href="/types" class="hover:text-accent">Enneagram Types</a></li>
          <li><a href="/about" class="hover:text-accent">About</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="flex-grow container mx-auto py-8 px-4">
    <slot />
  </main>

  <footer class="bg-gray-800 text-white p-6">
    <div class="container mx-auto">
      <div class="flex flex-col md:flex-row justify-between">
        <div class="mb-4 md:mb-0">
          <h3 class="text-xl font-bold mb-2">Enneagram Quiz</h3>
          <p class="text-gray-300">Discover your personality type</p>
        </div>
        <div>
          <h4 class="font-semibold mb-2">Quick Links</h4>
          <ul class="space-y-1">
            <li><a href="/" class="text-gray-300 hover:text-accent">Home</a></li>
            <li><a href="/quiz" class="text-gray-300 hover:text-accent">Take Quiz</a></li>
            <li><a href="/types" class="text-gray-300 hover:text-accent">Enneagram Types</a></li>
            <li><a href="/about" class="text-gray-300 hover:text-accent">About</a></li>
          </ul>
        </div>
      </div>
      <div class="mt-6 pt-6 border-t border-gray-700 text-center text-gray-400">
        <p>&copy; {new Date().getFullYear()} Enneagram Quiz. All rights reserved.</p>
      </div>
    </div>
  </footer>
</div>