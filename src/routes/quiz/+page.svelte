<script>
  import { onMount } from 'svelte';
  
  // Define the quiz questions
  const questions = [
    {
      id: 1,
      text: "I tend to be highly organized and prefer having a structured plan.",
      type: 1
    },
    {
      id: 2,
      text: "I often put others' needs before my own and enjoy helping people.",
      type: 2
    },
    {
      id: 3,
      text: "I am driven to achieve success and recognition for my accomplishments.",
      type: 3
    },
    {
      id: 4,
      text: "I value authenticity and often feel different from others.",
      type: 4
    },
    {
      id: 5,
      text: "I prefer to observe and analyze before engaging with others or situations.",
      type: 5
    },
    {
      id: 6,
      text: "I tend to be loyal and value security and stability.",
      type: 6
    },
    {
      id: 7,
      text: "I seek new experiences and try to avoid negative emotions.",
      type: 7
    },
    {
      id: 8,
      text: "I am assertive and comfortable taking control of situations.",
      type: 8
    },
    {
      id: 9,
      text: "I avoid conflict and try to maintain harmony in my relationships.",
      type: 9
    },
    {
      id: 10,
      text: "I have high standards for myself and others and notice when things aren't done correctly.",
      type: 1
    },
    {
      id: 11,
      text: "I am sensitive to others' feelings and needs.",
      type: 2
    },
    {
      id: 12,
      text: "I adapt my behavior to be successful in different situations.",
      type: 3
    },
    {
      id: 13,
      text: "I often experience emotions deeply and am drawn to what's missing in my life.",
      type: 4
    },
    {
      id: 14,
      text: "I value my privacy and need time alone to recharge.",
      type: 5
    },
    {
      id: 15,
      text: "I tend to anticipate problems and worry about what could go wrong.",
      type: 6
    },
    {
      id: 16,
      text: "I am optimistic and enjoy planning fun activities.",
      type: 7
    },
    {
      id: 17,
      text: "I am direct and straightforward in my communication.",
      type: 8
    },
    {
      id: 18,
      text: "I can see multiple perspectives and often mediate conflicts.",
      type: 9
    }
    // More questions would be added in a real implementation
  ];
  
  // Initialize scores for each type
  let scores = {
    1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0, 7: 0, 8: 0, 9: 0
  };
  
  let currentQuestionIndex = 0;
  let quizCompleted = false;
  let primaryType = null;
  let secondaryType = null;
  
  // Handle answer selection
  function handleAnswer(score) {
    const currentQuestion = questions[currentQuestionIndex];
    scores[currentQuestion.type] += score;
    
    if (currentQuestionIndex < questions.length - 1) {
      currentQuestionIndex++;
    } else {
      completeQuiz();
    }
  }
  
  // Calculate results when quiz is completed
  function completeQuiz() {
    quizCompleted = true;
    
    // Find primary and secondary types
    let sortedTypes = Object.entries(scores)
      .sort((a, b) => b[1] - a[1])
      .map(entry => ({ type: parseInt(entry[0]), score: entry[1] }));
    
    primaryType = sortedTypes[0].type;
    secondaryType = sortedTypes[1].type;
  }
  
  // Get type descriptions
  function getTypeDescription(type) {
    const descriptions = {
      1: {
        name: "The Reformer",
        description: "Principled, purposeful, self-controlled, and perfectionistic. Ones are conscientious and ethical, with a strong sense of right and wrong.",
        strengths: "Honest, responsible, improvement-oriented, ethical, fair, reliable",
        weaknesses: "Critical, perfectionist, judgmental, self-righteous, inflexible"
      },
      2: {
        name: "The Helper",
        description: "Generous, demonstrative, people-pleasing, and possessive. Twos are empathetic, sincere, and warm-hearted.",
        strengths: "Caring, interpersonal, warm, helpful, supportive, giving",
        weaknesses: "Prideful, overly accommodating, intrusive, manipulative"
      },
      3: {
        name: "The Achiever",
        description: "Adaptable, excelling, driven, and image-conscious. Threes are self-assured, attractive, and charming.",
        strengths: "Ambitious, competent, adaptable, energetic, self-assured",
        weaknesses: "Overly concerned with image, workaholic, competitive"
      },
      4: {
        name: "The Individualist",
        description: "Expressive, dramatic, self-absorbed, and temperamental. Fours are sensitive, introspective, and reserved.",
        strengths: "Creative, intuitive, sensitive, compassionate, authentic",
        weaknesses: "Moody, self-conscious, withdrawn, melancholic"
      },
      5: {
        name: "The Investigator",
        description: "Perceptive, innovative, secretive, and isolated. Fives are alert, insightful, and curious.",
        strengths: "Analytical, perceptive, innovative, objective, knowledgeable",
        weaknesses: "Detached, isolated, overly private, intellectually arrogant"
      },
      6: {
        name: "The Loyalist",
        description: "Engaging, responsible, anxious, and suspicious. Sixes are committed, security-oriented, and trustworthy.",
        strengths: "Loyal, responsible, trustworthy, anticipative, cooperative",
        weaknesses: "Anxious, suspicious, doubtful, reactive, pessimistic"
      },
      7: {
        name: "The Enthusiast",
        description: "Spontaneous, versatile, distractible, and scattered. Sevens are extroverted, optimistic, and spontaneous.",
        strengths: "Enthusiastic, optimistic, versatile, spontaneous, productive",
        weaknesses: "Scattered, impulsive, undisciplined, self-centered"
      },
      8: {
        name: "The Challenger",
        description: "Self-confident, decisive, willful, and confrontational. Eights are protective, resourceful, and decisive.",
        strengths: "Powerful, decisive, protective, resourceful, straightforward",
        weaknesses: "Domineering, confrontational, intimidating, controlling"
      },
      9: {
        name: "The Peacemaker",
        description: "Receptive, reassuring, agreeable, and complacent. Nines are accepting, trusting, and stable.",
        strengths: "Peaceful, easygoing, receptive, supportive, accepting",
        weaknesses: "Complacent, stubborn, conflict-avoidant, self-forgetting"
      }
    };
    
    return descriptions[type];
  }
  
  // Reset quiz
  function resetQuiz() {
    scores = { 1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0, 7: 0, 8: 0, 9: 0 };
    currentQuestionIndex = 0;
    quizCompleted = false;
    primaryType = null;
    secondaryType = null;
  }
</script>

<svelte:head>
  <title>Enneagram Quiz - Find Your Type</title>
  <meta name="description" content="Take our comprehensive Enneagram quiz to discover your personality type." />
</svelte:head>

<div class="max-w-3xl mx-auto">
  {#if !quizCompleted}
    <div class="bg-white rounded-lg shadow-lg p-8">
      <h1 class="text-3xl font-bold text-center mb-8">Enneagram Personality Quiz</h1>
      
      <div class="mb-6">
        <div class="flex justify-between mb-2">
          <span>Question {currentQuestionIndex + 1} of {questions.length}</span>
          <span>{Math.round((currentQuestionIndex / questions.length) * 100)}% Complete</span>
        </div>
        <div class="w-full bg-gray-200 rounded-full h-2.5">
          <div class="bg-primary h-2.5 rounded-full" style="width: {(currentQuestionIndex / questions.length) * 100}%"></div>
        </div>
      </div>
      
      <div class="mb-8">
        <h2 class="text-xl font-semibold mb-6">{questions[currentQuestionIndex].text}</h2>
        
        <div class="grid grid-cols-1 gap-3">
          <button on:click={() => handleAnswer(5)} class="bg-primary text-white py-3 px-4 rounded-lg hover:bg-primary/90 transition-colors">
            Strongly Agree
          </button>
          <button on:click={() => handleAnswer(4)} class="bg-primary/80 text-white py-3 px-4 rounded-lg hover:bg-primary/70 transition-colors">
            Agree
          </button>
          <button on:click={() => handleAnswer(3)} class="bg-gray-500 text-white py-3 px-4 rounded-lg hover:bg-gray-600 transition-colors">
            Neutral
          </button>
          <button on:click={() => handleAnswer(2)} class="bg-gray-400 text-white py-3 px-4 rounded-lg hover:bg-gray-500 transition-colors">
            Disagree
          </button>
          <button on:click={() => handleAnswer(1)} class="bg-gray-300 text-gray-800 py-3 px-4 rounded-lg hover:bg-gray-400 transition-colors">
            Strongly Disagree
          </button>
        </div>
      </div>
    </div>
  {:else}
    <div class="bg-white rounded-lg shadow-lg p-8">
      <h1 class="text-3xl font-bold text-center mb-6">Your Enneagram Results</h1>
      
      {#if primaryType}
        <div class="mb-8">
          <div class="text-center mb-6">
            <span class="inline-block bg-primary text-white text-5xl font-bold rounded-full w-20 h-20 flex items-center justify-center mb-2">
              {primaryType}
            </span>
            <h2 class="text-2xl font-bold">Type {primaryType}: {getTypeDescription(primaryType).name}</h2>
          </div>
          
          <p class="mb-4">{getTypeDescription(primaryType).description}</p>
          
          <div class="grid md:grid-cols-2 gap-4 mb-6">
            <div class="bg-green-50 p-4 rounded-lg">
              <h3 class="font-semibold text-green-800 mb-2">Strengths</h3>
              <p>{getTypeDescription(primaryType).strengths}</p>
            </div>
            <div class="bg-red-50 p-4 rounded-lg">
              <h3 class="font-semibold text-red-800 mb-2">Growth Areas</h3>
              <p>{getTypeDescription(primaryType).weaknesses}</p>
            </div>
          </div>
        </div>
        
        {#if secondaryType}
          <div class="mb-8">
            <h3 class="text-xl font-semibold mb-3">Your Secondary Type: {secondaryType} - {getTypeDescription(secondaryType).name}</h3>
            <p>{getTypeDescription(secondaryType).description}</p>
          </div>
        {/if}
        
        <div class="mt-8 text-center">
          <button on:click={resetQuiz} class="btn-secondary mr-4">
            Retake Quiz
          </button>
          <a href="/types" class="btn-primary">
            Learn More About All Types
          </a>
        </div>
      {/if}
    </div>
  {/if}
</div>