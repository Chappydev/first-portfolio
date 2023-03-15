<script>
  import Project from "./Project.svelte";


  const projects = [
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
      img: 'https://picsum.photos/id/36/400/600',
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
  section {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>