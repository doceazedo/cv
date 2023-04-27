<script lang="ts">
  import {
    CapacitorIcon,
    ChaiIcon,
    CodeIgniterIcon,
    DockerIcon,
    EmailIcon,
    GithubIcon, 
    JestIcon, 
    LocationIcon,
    MochaIcon,
    MySQLIcon,
    NextjsIcon,
    NodejsIcon,
    PhoneIcon,
    PostgresIcon,
    PuppeteerIcon,
    ReactIcon,
    SassIcon,
    StorybookIcon, 
    StyledComponentsIcon,
    SvelteIcon,
    TypeScriptIcon,
    UnrealIcon,
    WordPressIcon
  } from './lib/components/icons';
  import './sass/minireset.sass';
  import './sass/global.sass';

  const name = 'Doce Fernandes';
  const role = 'Fullstack Developer';
  const bio = 'I am a curiosity-driven fullstack developer with a focus on frontend and nearly 5 years of professional experience building web apps with Svelte, React, Sass, Node.js and Capacitor. I also do regular live coding streams on [Twitch] and occasionally write on [my blog].';
  const socials = [
    {
      icon: LocationIcon,
      label: 'São Paulo, Brazil',
    },
    {
      icon: GithubIcon,
      label: 'github.com/doceazedo',
      href: 'https://github.com/doceazedo',
      target: '_blank'
    },
    {
      icon: EmailIcon,
      label: 'me@doceazedo.com',
      href: 'mailto:me@doceazedo.com'
    },
    {
      icon: PhoneIcon,
      label: '+55 31 98869-6043',
      href: 'tel:5531988696043'
    },
  ];

  const experience = [
    {
      company: 'Datawrapper',
      role: 'Fullstack Developer',
      date: {
        start: 'Aug 2022',
        end: 'Apr 2023',
      },
      description: [
        'Enhanced app stability by migrating Svelte 2 to Svelte 3 components in the app charts and maps editor',
        'Contributed to a micro frontend architecture by maintaining multiple plugins',
        'Reduced errors by extensively testing Svelte components using Mocha and Chai'
      ],
      image: 'datawrapper.jpeg',
      stack: [
        {
          icon: SvelteIcon,
          label: 'Svelte',
        },
        {
          icon: SassIcon,
          label: 'Sass',
        },
        {
          icon: NodejsIcon,
          label: 'Node',
        },
        {
          icon: ChaiIcon,
          label: 'Chai'
        },
        {
          icon: MochaIcon,
          label: 'Mocha'
        },
        {
          icon: DockerIcon,
          label: 'Docker'
        },
      ]
    },
    {
      company: 'Ferreri',
      role: 'Frontend Developer',
      date: {
        start: 'Oct 2021',
        end: 'Present',
      },
      description: [
        'Implemented and maintained design systems with React and Storybook, organized in presentational and container components',
        'Worked with a team of 5 developers to reduce paperwork of a insurance company',
        'Automated code formatting and linting with GitLab CI and Git hooks',
        'Tested React components with Jest'
      ],
      image: 'ferreri.jpg',
      stack: [
        {
          icon: ReactIcon,
          label: 'React',
        },
        {
          icon: NextjsIcon,
          label: 'Next.js',
        },
        {
          icon: TypeScriptIcon,
          label: 'TypeScript'
        },
        {
          icon: StorybookIcon,
          label: 'Storybook'
        },
        {
          icon: StyledComponentsIcon,
          label: 'styled-components'
        },
        {
          icon: JestIcon,
          label: 'Jest'
        },
        {
          icon: DockerIcon,
          label: 'Docker'
        },
      ]
    },
    {
      company: 'WAS Software',
      role: 'Fullstack Developer',
      date: {
        start: 'Oct 2018',
        end: 'Sep 2021',
      },
      description: [
        'Introduced Svelte to deploy a delivery app with over a month in advance of the deadline',
        'Published a Capacitor mobile app with offline support and push notifications',
        'Assisted in building a fully-fledged ERP with CodeIgniter 3',
      ],
      image: 'wasoftware.png',
      stack: [
        {
          icon: SvelteIcon,
          label: 'Svelte',
        },
        {
          icon: SassIcon,
          label: 'Sass',
        },
        {
          icon: CapacitorIcon,
          label: 'Capacitor',
        },
        {
          icon: CodeIgniterIcon,
          label: 'CodeIgniter',
        },
        {
          icon: WordPressIcon,
          label: 'WordPress',
        },
        {
          icon: MySQLIcon,
          label: 'MySQL',
        },
      ]
    },
  ];

  const projects = [
    {
      name: 'Live coding',
      description: 'I do live coding streams regularly on Twitch, with custom commands and visuals powered by Svelte.',
      url: 'https://twitch.tv/doceazedo911',
      source: 'https://github.com/doceazedo/overlay',
      image: 'overlay.jpg',
      stack: [
        SvelteIcon,
        TypeScriptIcon
      ],
    },
    {
      name: 'Fazendoca',
      description: 'A social game about taking care of your farm, made on UE5 with a SvelteKit REST API and Prisma ORM.',
      source: 'https://github.com/doceazedo/fazendoca-ue5',
      image: 'fazendoca.jpg',
      stack: [
        UnrealIcon,
        NodejsIcon,
        TypeScriptIcon,
        PostgresIcon,
      ],
    },
  ]
</script>

<h1 class="name">{name}</h1>
<div class="description">
  <div class="left">
    <p class="left-item role">{role}</p>
    <ul class="socials">
      {#each socials as social}
        <li>
          {#if !!social.href}
            <a href={social.href} target={social.target}>
              <span class="icon">
                <svelte:component this={social.icon} />
              </span>
              {social.label}
            </a>
          {:else}
            <span class="icon">
              <svelte:component this={social.icon} />
            </span>
            {social.label}
          {/if}
        </li>
      {/each}
    </ul>
  </div>
  <div class="right">
    {@html bio
      .replace('[Twitch]', '<a href="https://twitch.tv/doceazedo911">Twitch</a>')
      .replace('[my blog]', '<a href="https://doceazedo.com">my blog</a>')
    }
  </div>
</div>

<h1 class="section-title">Work Experience</h1>

<ul class="work">
  {#each experience as work}
    <li>
      <img src="/img/{work.image}" alt="" class="logo" />
      <div class="work-details">
        <div class="work-title">
          <h1 class="company">{work.company}</h1>
          <div class="position">
            <p>{work.role}</p>
            <p>{work.date.start} - {work.date.end}</p>
          </div>
        </div>
        <ul class="work-description">
          {#each work.description as point}
            <li>{point}</li>
          {/each}
        </ul>
        <ul class="stack">
          {#each work.stack as tech}
            <li>
              <svelte:component this={tech.icon} /> {tech.label}
            </li>
          {/each}
        </ul>
      </div>
    </li>
  {/each}
</ul>

<h1 class="section-title">Projects</h1>

<ul class="projects">
  {#each projects as project}
    <li>
      <img src="/img/{project.image}" alt="" class="screenshot">
      <div class="project-details">
        <h1 class="project-title">
          {project.name}
          <div class="stack">
            {#each project.stack as tech}
              <svelte:component this={tech} />
            {/each}
          </div>
        </h1>
        <p class="project-description">
          {project.description}
        </p>
        <div class="links">
          {#if !!project.url}
            <a href={project.url} target="_blank">Visit</a>
            <span>/</span>
          {/if}
          <a href={project.source} target="_blank">Source code</a>
        </div>
      </div>
    </li>
  {/each}
</ul>

<style lang="sass">
  $primary: #6930c3

  .name
    font-size: 32px
    font-weight: 900
    line-height: 1
    margin-bottom: 1rem
  
  .role
    font-size: 20px
    font-weight: 600
    margin-bottom: .5rem

  .description
    display: flex
    gap: 2rem

    .left
      flex-shrink: 0

    .right
      font-size: .9rem
      line-height: 1.35

      :global(a)
        color: inherit

  .socials
    display: flex
    flex-direction: column
    gap: 4px

    li,
    a
      display: flex
      align-items: center
      gap: 6px
      color: #000
      font-size: .9rem

      .icon
        display: flex
        justify-content: center
        align-items: center
        width: 24px
        height: 24px
        color: #333
        background-color: #eee
        border-radius: 50%

        :global(svg)
          width: 16px
          height: 16px

  .section-title
    display: flex
    align-items: center
    gap: 1.5rem
    font-size: 24px
    font-weight: 700
    color: $primary
    margin: 2rem 0

    &::after
      content: ''
      display: flex
      flex-grow: 1
      height: 3px
      background-color: $primary
      print-color-adjust: exact

  .work
    display: flex
    flex-direction: column
    gap: 3rem

    >li
      display: flex
      gap: 16px

      .logo
        flex-shrink: 0
        height: 50px
        border-radius: .25rem

      .work-details
        display: flex
        flex-direction: column
        gap: .75rem
        flex-grow: 1
        line-height: 1

      .work-title
        display: flex
        justify-content: space-between
        align-items: center

        .company,
        .position
          font-weight: 600

        .position
          display: flex
          gap: 1.5rem
          font-size: .9rem

      .work-description
        padding-left: 2rem
        font-size: .9rem
        line-height: 1.35
        list-style: disc

      .stack
        display: flex
        flex-wrap: wrap
        gap: .75rem 0
        font-size: .9rem

        li
          display: flex
          align-items: center
          gap: .25rem

          :global(svg)
            height: 16px
            width: 16px

          &:not(:last-child)::after
            content: "/"
            margin: 0 12px 0 8px
            opacity: .5

  .projects
    display: flex
    justify-content: space-between
    gap: 1.5rem

    li
      display: flex
      align-items: flex-start
      gap: .5rem
      width: 50%

      .screenshot
        width: 8rem
        aspect-ratio: 4 / 3
        border-radius: .5rem

      .project-title
        display: flex
        gap: .5rem
        align-items: center
        font-weight: 600

        .stack
          display: flex
          gap: .25rem

          :global(svg)
            width: 16px
            height: 16px

      .project-description
        font-size: .9rem

      .links
        a
          color: #000

        span
          margin: 0 6px
          opacity: .5
</style>