<!DOCTYPE html>
<!--
  Vaishnavi Akilla — personal site
  One file, no animation. Edit the text between the tags.
  Order below: STYLES, HEADER, MENU, HERO, PRACTICE, WORK,
  WORK SAMPLES (commented out), EXPERIENCE, CONTACT, FOOTER, SCRIPT.
-->
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Vaishnavi Akilla — Climate resilience, urban design, learning</title>
<meta name="description" content="Independent consultant working across climate research, nature-based urban design, and youth and community learning.">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">

<style>
/* ============ STYLES ============ */

:root{
  --forest:#1C3B2E;              /* primary — text, dark section */
  --umber:#8B6F47;              /* accent — thread, small marks */
  --paper:#F7F6F2;              /* background */
  --line:rgba(28,59,46,.16);    /* thin dividing lines */
  --gutter:clamp(1.5rem, 6vw, 6rem);
  --thread:clamp(.75rem, 2.6vw, 2.6rem);   /* how far in the thread line sits */

  --display:"Cormorant Garamond",Garamond,Georgia,serif;
  --body:"Inter",system-ui,-apple-system,"Helvetica Neue",Arial,sans-serif;
}

*{box-sizing:border-box}
html{scroll-behavior:smooth}

body{
  position:relative; margin:0; color:var(--forest);
  font-family:var(--body); font-weight:400;
  font-size:clamp(.98rem,.94rem + .2vw,1.06rem); line-height:1.68;
  letter-spacing:-.011em;
  overflow-x:hidden; -webkit-font-smoothing:antialiased;

  /* background: a faint field of + marks */
  background-color:var(--paper);
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='64' height='64'%3E%3Cpath d='M27 32h10M32 27v10' stroke='%238B6F47' stroke-width='0.9' opacity='0.3'/%3E%3C/svg%3E");
}

/* ---- the thread: one continuous line down the left edge of the whole page ---- */
body::before{
  content:""; position:absolute; z-index:5;
  top:0; bottom:0; left:var(--thread); width:1px;
  background:var(--umber); opacity:.55;
}

a{color:inherit}
:focus-visible{outline:2px solid var(--forest); outline-offset:4px}

/* ---- header ---- */
.head{
  position:fixed; top:0; left:0; right:0; z-index:60;
  display:flex; justify-content:space-between; align-items:baseline;
  padding:1.15rem var(--gutter);
  font-family:var(--body); font-weight:500;
  font-size:clamp(.95rem,2.2vw,1.02rem); letter-spacing:-.005em;
}
.head a{text-decoration:none}
.menu-btn{border:0; background:none; padding:0; margin:0; color:inherit; font:inherit; cursor:pointer}
.open .head{color:var(--paper)}

/* ---- menu ---- */
.menu{
  position:fixed; inset:0; z-index:50; display:none;
  background:var(--forest); color:var(--paper);
  flex-direction:column; justify-content:center;
  padding:6rem var(--gutter) 3rem;
}
.open .menu{display:flex}
.menu ol{list-style:none; margin:0; padding:0}
.menu li{border-top:1px solid rgba(247,246,242,.22)}
.menu li:last-child{border-bottom:1px solid rgba(247,246,242,.22)}
.menu a{
  display:block; padding:clamp(.5rem,2vw,1rem) 0; text-decoration:none;
  font-family:var(--display); font-weight:300;
  font-size:clamp(2.2rem,7.5vw,5rem); line-height:1.12;
}
.menu a:hover{color:#C9B896}
.menu p{margin-top:2.5rem; font-size:.9rem; color:rgba(247,246,242,.75)}

/* ---- hero ---- */
.hero{
  min-height:100svh; display:flex; flex-direction:column; justify-content:flex-end;
  padding:8rem var(--gutter) clamp(2.5rem,7vh,4.5rem);
}
h1{
  margin:0; font-family:var(--display); font-weight:300;
  font-size:clamp(3.2rem,13vw,11rem); line-height:.92; letter-spacing:-.015em;
}
h1 b{display:block; font-weight:inherit}
h1 em{font-style:italic; font-weight:400}
.note{
  margin:clamp(1.6rem,4vw,2.6rem) 0 0; max-width:46ch;
  font-size:clamp(1rem,1.6vw,1.15rem); line-height:1.6; font-weight:300;
}
.avail{margin:1.1rem 0 0; font-size:.88rem; color:var(--umber); letter-spacing:0}

/* ---- sections ---- */
section{scroll-margin-top:5rem}
.band{
  position:relative; border-top:1px solid var(--line);
  padding:clamp(4rem,11vh,8rem) var(--gutter);
}
.band::before{                     /* a knot on the thread at each division */
  content:"+"; position:absolute; top:0; left:var(--thread);
  transform:translate(-50%,-52%); padding:.15em .3em; line-height:1;
  font-family:var(--body); font-size:.95rem;
  color:var(--umber); background:var(--paper);
}
h2{
  margin:0 0 2.4rem; font-family:var(--display); font-weight:400; max-width:20ch;
  font-size:clamp(2rem,5vw,3.4rem); line-height:1.12; letter-spacing:-.01em;
}
.intro{max-width:62ch}
.intro p{margin:0 0 1.2rem; font-weight:300; font-size:1.04em}

/* ---- work rows ---- */
.row{
  display:grid; gap:1.3rem clamp(2rem,6vw,5rem);
  padding:clamp(2.2rem,5vw,3.6rem) 0;
  border-bottom:1px solid var(--line);
}
.row:first-of-type{border-top:1px solid var(--line)}
h3{
  margin:0; font-family:var(--display); font-weight:400;
  font-size:clamp(1.7rem,4vw,2.7rem); line-height:1.1; letter-spacing:-.01em;
}
.row p{margin:0 0 1.4rem; max-width:58ch; font-weight:300}
.tags{list-style:none; display:flex; flex-wrap:wrap; gap:.45rem .5rem; margin:0; padding:0}
.tags li{
  font-size:.82rem; line-height:1; letter-spacing:0;
  padding:.5rem .75rem; border:1px solid var(--line); border-radius:999px;
  color:var(--forest); background:var(--paper);
}

/* ---- experience ---- */
table{width:100%; border-collapse:collapse; text-align:left}
th{
  font-weight:500; font-size:.8rem; letter-spacing:.01em; color:var(--umber);
  padding:0 0 .75rem; border-bottom:1px solid var(--line);
}
td{padding:1.25rem 1.5rem 1.25rem 0; border-bottom:1px solid var(--line); vertical-align:top}
.role{font-weight:500; font-size:1.02rem; max-width:28ch}
.org{font-weight:300}
.when{padding-right:0; text-align:right; white-space:nowrap; font-size:.88rem; color:var(--umber)}
th:last-child{text-align:right}

/* ---- contact + footer ---- */
.contact{
  border-top:0; color:var(--paper);
  background-color:var(--forest);
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='64' height='64'%3E%3Cpath d='M27 32h10M32 27v10' stroke='%23F7F6F2' stroke-width='0.9' opacity='0.16'/%3E%3C/svg%3E");
}
.contact::before{background:var(--forest); color:#C9B896}
.contact p{max-width:48ch; color:rgba(247,246,242,.85); font-weight:300}
.links{list-style:none; margin:2.8rem 0 0; padding:0}
.links li{border-top:1px solid rgba(247,246,242,.24)}
.links li:last-child{border-bottom:1px solid rgba(247,246,242,.24)}
.links a{
  display:block; padding:clamp(.7rem,2.2vw,1.15rem) 0; text-decoration:none;
  font-family:var(--display); font-weight:300;
  font-size:clamp(1.5rem,5.5vw,3.4rem); line-height:1.15; word-break:break-word;
}
.links a:hover{color:#C9B896}
footer{
  background:var(--forest); color:rgba(247,246,242,.6);
  font-size:.82rem; padding:0 var(--gutter) 2.5rem;
  display:flex; flex-wrap:wrap; gap:.4rem 1.5rem; justify-content:space-between;
}

/* ---- responsive ---- */
@media (min-width:800px){
  .row{grid-template-columns:.9fr 1.5fr}
}
@media (max-width:560px){
  table,tbody,tr,td{display:block; width:100%}
  thead{display:none}
  tr{border-bottom:1px solid var(--line); padding:1.25rem 0}
  td{border:0; padding:0 0 .25rem}
  .role{max-width:none}
  .when{text-align:left; padding-top:.35rem}
}
@media (prefers-reduced-motion:reduce){
  html{scroll-behavior:auto}
}
</style>
</head>

<body>

<!-- ============ HEADER ============ -->
<header class="head">
  <a href="#top">Vaishnavi Akilla</a>
  <button class="menu-btn" id="btn" aria-expanded="false" aria-controls="menu">
    <span id="sign" aria-hidden="true">+</span> Menu
  </button>
</header>

<!-- ============ MENU ============ -->
<nav class="menu" id="menu" aria-label="Main">
  <ol>
    <li><a href="#work">Work</a></li>
    <li><a href="#practice">Practice</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
  <p><a href="mailto:akilla.vaish@gmail.com">akilla.vaish@gmail.com</a></p>
</nav>

<main id="top">

<!-- ============ HERO ============ -->
<section class="hero">
  <h1><b>Vaishnavi</b><b>Akilla</b></h1>
  <p class="note">Independent consultant working where climate risk meets the everyday life of a city — through research, nature-based design, and learning built with communities.</p>
  <p class="avail">Taking on contract work with organisations worldwide.</p>
</section>

<!-- ============ PRACTICE ============ -->
<section class="band" id="practice">
  <div class="intro">
    <h2>How I work</h2>
    <p>I work with governments, UN bodies, non-profits, design studios, and private sector partners on projects where water, heat, and risk shape how people live. My training is in urban design and environmental conservation education, and the practice moves between the two: spatial evidence on one side, the workshops and toolkits that put it to use on the other.</p>
    <p>Most engagements start with a question a team can't answer with the data they have, or a plan that needs the people it affects in the room. I can take a project from first analysis through design to the programme that keeps it running.</p>
  </div>
</section>

<!-- ============ WORK ============ -->
<section class="band" id="work">
  <h2>Three ways to bring me in</h2>

  <article class="row">
    <h3>Research and analysis</h3>
    <div>
      <p>Policy research built from numbers and lived experience together. I run mixed-method studies — spatial data, surveys, mapping, focus groups, participatory methods — and turn them into evidence that holds up in a planning meeting. Much of this work has looked at how climate change lands on cities: flooding, drought, heat, and disaster risk reduction.</p>
      <ul class="tags">
        <li>GIS and spatial analysis</li>
        <li>Economic and demographic studies</li>
        <li>Climate resilience assessment</li>
        <li>Evidence-based research</li>
      </ul>
    </div>
  </article>

  <article class="row">
    <h3>Design development</h3>
    <div>
      <p>Nature-based design for cities under pressure. I develop responses to urban flooding and the heat island effect at the scale of a street, a park, or a district — shaped with the people who will live with them, through participatory design and sustained community engagement.</p>
      <ul class="tags">
        <li>Master planning</li>
        <li>Streetscape and public space design</li>
        <li>Urban code development</li>
        <li>Green and blue infrastructure</li>
        <li>Community engagement</li>
      </ul>
    </div>
  </article>

  <article class="row">
    <h3>Education and engagement strategies</h3>
    <div>
      <p>Capacity building with young people and communities across regions, on sustainable development and climate resilience. I design learning that travels — toolkits, workshops, curricula, digital programmes — and support the frameworks and partnerships that keep it running, working with international organisations, non-profits, and private sector actors.</p>
      <ul class="tags">
        <li>Toolkit design</li>
        <li>Climate action planning</li>
        <li>Global framework design and implementation</li>
        <li>Stakeholder workshops</li>
        <li>Digital learning</li>
      </ul>
    </div>
  </article>
</section>

<!-- ============ WORK SAMPLES ============
     When you have a case study, delete this comment marker and the one at the
     end of the block, then copy the <article> once per project.
     Also add <li><a href="#samples">Work samples</a></li> to the menu above.

<section class="band" id="samples">
  <h2>Work samples</h2>
  <article class="row">
    <h3><a href="work/project-name/">Project name</a></h3>
    <div>
      <p>One or two sentences on the question, your role, and what changed as a result.</p>
      <ul class="tags"><li>Client</li><li>2025</li><li>Flood resilience</li></ul>
    </div>
  </article>
</section>

============ END WORK SAMPLES ============ -->

<!-- ============ EXPERIENCE ============ -->
<section class="band" id="experience">
  <h2>Selected experience</h2>
  <table>
    <thead>
      <tr><th>Role</th><th>Organisation</th><th>Years</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="role">Youth Engagement Specialist</td>
        <td class="org">Global Kids</td>
        <td class="when">Jul 2024 — Present</td>
      </tr>
      <tr>
        <td class="role">Executive Committee Member, and Chair of the Climate Action &amp; Sustainability Working Group</td>
        <td class="org">International Commission for Equity and Peace</td>
        <td class="when">Jul 2025 — Present</td>
      </tr>
      <tr>
        <td class="role">Program Support Officer</td>
        <td class="org">United Nations Major Group for Children and Youth</td>
        <td class="when">May 2025 — Present</td>
      </tr>
      <tr>
        <td class="role">Urban Design Consultant</td>
        <td class="org">eStudioOCA</td>
        <td class="when">Nov 2023 — Jan 2024</td>
      </tr>
      <tr>
        <td class="role">Research Assistant, Climate Risk Communication &amp; Policy</td>
        <td class="org">New York University</td>
        <td class="when">Feb 2023 — May 2023</td>
      </tr>
    </tbody>
  </table>
</section>

<!-- ============ CONTACT ============ -->
<section class="band contact" id="contact">
  <h2>Tell me about the project</h2>
  <p>Send a short note about what you're working on, the timeline, and where you're stuck. I'll reply with whether I'm the right fit and how I'd approach it.</p>
  <ul class="links">
    <li><a href="mailto:akilla.vaish@gmail.com">akilla.vaish@gmail.com</a></li>
    <li><a href="https://www.linkedin.com/in/vaishnavi-akilla/" target="_blank" rel="noopener">LinkedIn</a></li>
  </ul>
</section>

</main>

<footer>
  <span>Vaishnavi Akilla</span>
  <span>Brooklyn, New York — working globally</span>
</footer>

<!-- ============ SCRIPT ============ opens and closes the menu -->
<script>
  var btn = document.getElementById('btn');
  var sign = document.getElementById('sign');
  function set(open){
    document.body.classList.toggle('open', open);
    btn.setAttribute('aria-expanded', open);
    sign.textContent = open ? '\u00D7' : '+';
  }
  btn.onclick = function(){ set(!document.body.classList.contains('open')); };
  document.getElementById('menu').onclick = function(e){
    if(e.target.tagName === 'A') set(false);
  };
  document.onkeydown = function(e){ if(e.key === 'Escape') set(false); };
</script>

</body>
</html>
