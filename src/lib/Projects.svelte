<script>
  import Project from "./Project.svelte";


  const projects = [
    {
      name: 'AI-Chan',
      technologies: [
        'Next.js', 'SASS', 'OpenAI', 'React Joyride'
      ],
      description: "AI-Chan is a language assistant that helps japanese learners' overcome challenges that are beyond the capabilities of other tools such as dictionaries.",
      challenges: [
        // Something about the openai api,
        'While the gpt-3.5 model is incredibly powerful, getting consistently helpful responses required a lot of careful tuning of the prompts.',
        // Managing chat state,
        // Something about react-joyride
        'I ran into confusion when trying to implement some more complex features for my application tour using React Joyride. The documentation did not have a great explanation of how to achieve what I wanted. However, I was able to reference the code for the official demo to work out how they managed to achieve a similar feature and replicate that in my own application.'
      ],
      img: '/AIChan.png',
      github: 'https://github.com/Chappydev/AIChan',
      link: 'https://aichan.vercel.app/'
    },
    {
      name: 'GoalTree!',
      technologies: [
        'React', 'React-Query', 'SASS', 'Express', 'MongoDB'
      ],
      description: 'Manage goals/tasks in a tree structure by breaking a goal into its tasks, then breaking those tasks into their subtasks, and so on.',
      challenges: [
        'I had no experience with tree structures before this project, so I learned a lot about how to work with trees. Representing the tree structure in the database proved especially challenging, requiring a lot of thought and iteration before landing on a working solution.',
        'The lines between tree nodes gave me a lot of trouble throughout the project. When trying to animate the color change of the line, I found a limitation in the capabilities of CSS, so I implemented the animation by combining a custom hook with the svg \'linearGradient\' element'
      ],
      img: '/GoalTree.png',
      github: 'https://github.com/Chappydev/goal-tree',
      link: 'https://goaltree.onrender.com'
    }
  ];
</script>

<section id="projects">
  <h2>My <span class="orange">Projects</span></h2>

  {#each projects as project}
    <Project {project}/>
  {/each}
</section>

<style lang="scss">
  @use './partials/mixins' as m;

  section {
    display: flex;
    flex-direction: column;
    align-items: center;
    @include m.for-size(m-up) {

    }
  }
</style>