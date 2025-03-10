<script>
  // Enneagram type data
  const types = [
    {
      number: 1,
      name: "The Reformer",
      nickname: "The Perfectionist",
      description: "Ethical, dedicated and reliable, Ones are motivated by a desire to live the right way, improve the world, and avoid fault and blame.",
      characteristics: [
        "Conscientious and ethical",
        "Purposeful and self-controlled",
        "Perfectionistic and critical",
        "Principled and orderly",
        "Improvement-oriented"
      ],
      strengths: [
        "Honest and ethical",
        "Reliable and responsible",
        "Improvement-oriented",
        "Self-disciplined",
        "Fair-minded"
      ],
      weaknesses: [
        "Critical (of self and others)",
        "Perfectionistic",
        "Judgmental",
        "Overly serious",
        "Inflexible"
      ],
      growthPath: "Learning to accept imperfection and balancing high standards with self-compassion."
    },
    {
      number: 2,
      name: "The Helper",
      nickname: "The Giver",
      description: "Warm, caring and giving, Twos are motivated by a need to be loved and needed, and to avoid acknowledging their own needs.",
      characteristics: [
        "Empathetic and warm",
        "People-pleasing and generous",
        "Possessive and demonstrative",
        "Caring and interpersonal",
        "Supportive"
      ],
      strengths: [
        "Caring and nurturing",
        "Emotionally intuitive",
        "Supportive and giving",
        "Relationship-oriented",
        "Empathetic"
      ],
      weaknesses: [
        "Overly accommodating",
        "Intrusive and possessive",
        "Indirect about own needs",
        "Manipulative",
        "Prideful"
      ],
      growthPath: "Learning to acknowledge their own needs and give without expectation of return."
    },
    {
      number: 3,
      name: "The Achiever",
      nickname: "The Performer",
      description: "Success-oriented, pragmatic and adaptable, Threes are motivated by a need to be successful and to avoid failure.",
      characteristics: [
        "Ambitious and driven",
        "Image-conscious and adaptable",
        "Excelling and efficient",
        "Goal-oriented",
        "Self-assured"
      ],
      strengths: [
        "Ambitious and self-assured",
        "Adaptable and energetic",
        "Competent and efficient",
        "Goal-oriented",
        "Practical"
      ],
      weaknesses: [
        "Image-conscious",
        "Overly competitive",
        "Workaholic tendencies",
        "Validation-seeking",
        "Emotionally detached"
      ],
      growthPath: "Learning to value themselves apart from their achievements and connect with authentic feelings."
    },
    {
      number: 4,
      name: "The Individualist",
      nickname: "The Romantic",
      description: "Creative, sensitive and withdrawn, Fours are motivated by a need to be unique, express themselves and avoid being ordinary.",
      characteristics: [
        "Expressive and creative",
        "Self-aware and reserved",
        "Sensitive and emotional",
        "Authentic and introspective",
        "Individualistic"
      ],
      strengths: [
        "Creative and expressive",
        "Emotionally honest",
        "Self-aware and introspective",
        "Compassionate toward suffering",
        "Authentic"
      ],
      weaknesses: [
        "Moody and self-conscious",
        "Withdrawn and melancholic",
        "Envious of others",
        "Self-indulgent",
        "Overly dramatic"
      ],
      growthPath: "Learning to embrace the ordinary aspects of life and find value in the present rather than what's missing."
    },
    {
      number: 5,
      name: "The Investigator",
      nickname: "The Observer",
      description: "Perceptive, innovative and isolated, Fives are motivated by a need to gain knowledge, conserve energy and avoid relying on others.",
      characteristics: [
        "Analytical and perceptive",
        "Private and detached",
        "Innovative and insightful",
        "Cerebral and knowledgeable",
        "Independent"
      ],
      strengths: [
        "Analytical and perceptive",
        "Knowledgeable and innovative",
        "Independent and self-sufficient",
        "Objective and calm",
        "Insightful"
      ],
      weaknesses: [
        "Detached and isolated",
        "Overly private",
        "Intellectually arrogant",
        "Stingy with time/energy",
        "Emotionally disconnected"
      ],
      growthPath: "Learning to engage with the world and others rather than withdrawing and observing from a distance."
    },
    {
      number: 6,
      name: "The Loyalist",
      nickname: "The Questioner",
      description: "Committed, security-oriented and engaging, Sixes are motivated by fear and the need for security.",
      characteristics: [
        "Loyal and committed",
        "Anxious and suspicious",
        "Responsible and trustworthy",
        "Questioning and doubting",
        "Security-oriented"
      ],
      strengths: [
        "Loyal and committed",
        "Responsible and hardworking",
        "Anticipative of problems",
        "Cooperative and supportive",
        "Trustworthy"
      ],
      weaknesses: [
        "Anxious and fearful",
        "Suspicious and doubtful",
        "Indecisive",
        "Pessimistic",
        "Reactive"
      ],
      growthPath: "Learning to develop inner security and trust in themselves rather than looking for certainty outside."
    },
    {
      number: 7,
      name: "The Enthusiast",
      nickname: "The Epicure",
      description: "Busy, fun-loving and spontaneous, Sevens are motivated by a need to be happy, plan stimulating experiences and avoid pain.",
      characteristics: [
        "Enthusiastic and optimistic",
        "Versatile and spontaneous",
        "Scattered and distractible",
        "Adventure-seeking",
        "Future-oriented"
      ],
      strengths: [
        "Enthusiastic and optimistic",
        "Versatile and spontaneous",
        "Quick-thinking and productive",
        "Adventurous",
        "Fun-loving"
      ],
      weaknesses: [
        "Scattered and distractible",
        "Escapist tendencies",
        "Impulsive and undisciplined",
        "Commitment-phobic",
        "Self-centered"
      ],
      growthPath: "Learning to focus on the present moment and deal with pain and limitation rather than escaping."
    },
    {
      number: 8,
      name: "The Challenger",
      nickname: "The Protector",
      description: "Powerful, dominating and self-confident, Eights are motivated by a need to be strong and avoid vulnerability.",
      characteristics: [
        "Assertive and powerful",
        "Self-confident and decisive",
        "Protective and resourceful",
        "Confrontational and direct",
        "Independent"
      ],
      strengths: [
        "Strong and protective",
        "Decisive and assertive",
        "Direct and honest",
        "Resourceful and action-oriented",
        "Justice-seeking"
      ],
      weaknesses: [
        "Domineering and controlling",
        "Confrontational and intimidating",
        "Excessive and impulsive",
        "Vengeful",
        "Resistant to vulnerability"
      ],
      growthPath: "Learning to embrace vulnerability and use power to empower others rather than control."
    },
    {
      number: 9,
      name: "The Peacemaker",
      nickname: "The Mediator",
      description: "Easygoing, self-effacing and receptive, Nines are motivated by a need to keep the peace, merge with others and avoid conflict.",
      characteristics: [
        "Peaceful and easygoing",
        "Agreeable and accommodating",
        "Receptive and reassuring",
        "Complacent and stubborn",
        "Conflict-avoidant"
      ],
      strengths: [
        "Peaceful and calming",
        "Patient and accepting",
        "Supportive and stable",
        "Mediating",
        "Inclusive of others' perspectives"
      ],
      weaknesses: [
        "Conflict-avoidant",
        "Stubborn and resistant",
        "Self-forgetting",
        "Procrastinating",
        "Complacent"
      ],
      growthPath: "Learning to assert themselves and recognize the value of healthy conflict and personal priorities."
    }
  ];
</script>

<svelte:head>
  <title>Enneagram Types - Detailed Information</title>
  <meta name="description" content="Learn about all nine Enneagram personality types, their characteristics, strengths, weaknesses, and growth paths." />
</svelte:head>

<div class="max-w-4xl mx-auto">
  <h1 class="text-3xl font-bold text-center mb-8">The Nine Enneagram Types</h1>
  
  <p class="text-lg mb-8">
    The Enneagram is a powerful tool for personal and spiritual growth that describes nine distinct personality types and their interrelationships. Each type has its own set of motivations, fears, desires, and coping mechanisms.
  </p>
  
  <div class="grid grid-cols-1 gap-8">
    {#each types as type}
      <div class="bg-white rounded-lg shadow-lg overflow-hidden">
        <div class="bg-primary text-white p-4">
          <div class="flex items-center">
            <span class="text-4xl font-bold mr-4">{type.number}</span>
            <div>
              <h2 class="text-2xl font-bold">{type.name}</h2>
              <p class="text-primary-100">{type.nickname}</p>
            </div>
          </div>
        </div>
        
        <div class="p-6">
          <p class="mb-6">{type.description}</p>
          
          <div class="grid md:grid-cols-2 gap-6 mb-6">
            <div>
              <h3 class="font-bold text-lg mb-2 text-primary">Key Characteristics</h3>
              <ul class="list-disc pl-5 space-y-1">
                {#each type.characteristics as trait}
                  <li>{trait}</li>
                {/each}
              </ul>
            </div>
            
            <div>
              <h3 class="font-bold text-lg mb-2 text-green-600">Strengths</h3>
              <ul class="list-disc pl-5 space-y-1 text-green-800">
                {#each type.strengths as strength}
                  <li>{strength}</li>
                {/each}
              </ul>
            </div>
          </div>
          
          <div class="mb-6">
            <h3 class="font-bold text-lg mb-2 text-red-600">Growth Areas</h3>
            <ul class="list-disc pl-5 space-y-1 text-red-800">
              {#each type.weaknesses as weakness}
                <li>{weakness}</li>
              {/each}
            </ul>
          </div>
          
          <div class="bg-gray-100 p-4 rounded-lg">
            <h3 class="font-bold text-lg mb-2">Growth Path</h3>
            <p>{type.growthPath}</p>
          </div>
        </div>
      </div>
    {/each}
  </div>
  
  <div class="text-center mt-12 mb-8">
    <a href="/quiz" class="btn-primary text-lg py-3 px-8 rounded-lg shadow-lg hover:shadow-xl transition-all">
      Take the Quiz to Find Your Type
    </a>
  </div>
</div>