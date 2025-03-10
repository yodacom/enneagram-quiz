<script>
  // Home page component
</script>

<svelte:head>
  <title>Enneagram Quiz - Discover Your Type</title>
  <meta name="description" content="Take our free Enneagram personality test to discover your type and learn more about yourself." />
</svelte:head>

<section class="py-12">
  <div class="text-center mb-12">
    <h1 class="text-4xl md:text-5xl font-bold mb-4">Discover Your Enneagram Type</h1>
    <p class="text-xl max-w-2xl mx-auto">Take our comprehensive quiz to uncover your Enneagram personality type and gain valuable insights into your core motivations, fears, and desires.</p>
    <div class="mt-8">
      <a href="/quiz" class="btn-primary text-lg py-3 px-8 rounded-lg shadow-lg hover:shadow-xl transition-all">
        Start Quiz
      </a>
    </div>
  </div>
  
  <div class="grid md:grid-cols-3 gap-8 mt-16">
    <div class="bg-white p-6 rounded-lg shadow-md">
      <div class="text-primary text-4xl mb-4">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-12 w-12 mx-auto">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z" />
        </svg>
      </div>
      <h3 class="text-xl font-semibold text-center mb-2">Self-Discovery</h3>
      <p class="text-gray-600 text-center">Gain deep insights into your personality, strengths, weaknesses, and core motivations.</p>
    </div>
    
    <div class="bg-white p-6 rounded-lg shadow-md">
      <div class="text-secondary text-4xl mb-4">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-12 w-12 mx-auto">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" />
        </svg>
      </div>
      <h3 class="text-xl font-semibold text-center mb-2">Better Relationships</h3>
      <p class="text-gray-600 text-center">Understand how you relate to others and improve your personal and professional relationships.</p>
    </div>
    
    <div class="bg-white p-6 rounded-lg shadow-md">
      <div class="text-accent text-4xl mb-4">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-12 w-12 mx-auto">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
        </svg>
      </div>
      <h3 class="text-xl font-semibold text-center mb-2">Personal Growth</h3>
      <p class="text-gray-600 text-center">Learn about your growth path and how to become the best version of yourself.</p>
    </div>
  </div>
</section>

<section class="py-12 bg-gray-100 rounded-lg">
  <div class="text-center mb-12">
    <h2 class="text-3xl font-bold mb-4">The Nine Enneagram Types</h2>
    <p class="max-w-2xl mx-auto">The Enneagram describes nine distinct personality types and maps each type's core motivations, fears, desires, and strengths.</p>
  </div>
  
  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 1: The Reformer</h3>
      <p class="text-gray-700">Principled, purposeful, self-controlled, and perfectionistic</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 2: The Helper</h3>
      <p class="text-gray-700">Generous, people-pleasing, and possessive</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 3: The Achiever</h3>
      <p class="text-gray-700">Adaptable, excelling, driven, and image-conscious</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 4: The Individualist</h3>
      <p class="text-gray-700">Expressive, dramatic, self-absorbed, and temperamental</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 5: The Investigator</h3>
      <p class="text-gray-700">Perceptive, innovative, secretive, and isolated</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 6: The Loyalist</h3>
      <p class="text-gray-700">Engaging, responsible, anxious, and suspicious</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 7: The Enthusiast</h3>
      <p class="text-gray-700">Spontaneous, versatile, acquisitive, and scattered</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 8: The Challenger</h3>
      <p class="text-gray-700">Self-confident, decisive, willful, and confrontational</p>
    </div>
    
    <div class="p-4">
      <h3 class="font-bold text-xl mb-2">Type 9: The Peacemaker</h3>
      <p class="text-gray-700">Receptive, reassuring, complacent, and resigned</p>
    </div>
  </div>
  
  <div class="text-center mt-8">
    <a href="/types" class="btn-secondary inline-block">Learn More About Each Type</a>
  </div>
</section>

<section class="py-12">
  <div class="text-center">
    <h2 class="text-3xl font-bold mb-6">Ready to Discover Your Type?</h2>
    <p class="text-xl mb-8 max-w-2xl mx-auto">Our comprehensive quiz will help you identify your Enneagram type and provide insights into your personality.</p>
    <a href="/quiz" class="btn-primary text-lg py-3 px-8 rounded-lg shadow-lg hover:shadow-xl transition-all">
      Take the Quiz Now
    </a>
  </div>
</section>