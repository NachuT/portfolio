<template>
  <div id="app">
    <header class="header">
      <h1>Nachiappan Thenappan Portfolio</h1>
    </header>
    <main class="main">
      <section id="about-you" class="section about-you" data-aos="fade-up" style="margin-top: 200px;">
        <h2>About Me</h2>
        <img :src="profilePicture" alt="Your photograph" class="profile-picture">
        <p>{{ aboutDescription }}</p>
        <div class="contact-info">
          <p>{{ shortContact }}</p>
          <p>{{ skills }}</p>
        </div>
        <div class="narrative">
          <div class="narrative">
            <p>{{ narrative1 }}</p>
            <p>{{ narrative2 }}</p>
            <p>{{ narrative3 }}</p>
          </div>
        </div>
      </section>
      <section id="resume-work-experience" class="section resume-work-experience" data-aos="fade-up">
          <h2>Resume/Work Experience</h2>
          <a href="https://docs.google.com/document/d/1xzpji8AdoVru8PSadVv1VqyrRV6q1Vk6oWgQLi0OGto/edit?usp=sharing" target="_blank" class="resume-link">View Resume (Google Doc)</a>
          <div class="narrative">
              <!-- Narrative content goes here -->
          </div>
      </section>

      
      <section id="projects" class="section projects">
        <h2>Projects</h2>
        <div v-for="project in projects" :key="project.id" class="project" data-aos="fade-up">
          <h3>{{ project.name }}</h3>
          <p v-if="project.course"><strong>Course:</strong> {{ project.course }}</p>
          <p><strong>Date:</strong> {{ project.date }}</p>
          <p>{{ project.description }}</p>
          <p><strong>Role:</strong> {{ project.role }}</p>
          <p><strong>Challenges:</strong> {{ project.challenges }}</p>
          <p><strong>Skills:</strong> {{ project.skills }}</p>
          <div v-if="project.image">
            <img :src="project.image" alt="Project image" class="project-image">
          </div>
          <div v-else>
            <p class="no-image-text">You are looking at it right now!</p>
          </div>
          <a :href="project.documentationLink" target="_blank" class="doc-link">Full Project Documentation</a>
        </div>
      </section>
      
      <section id="contact-me" class="section contact-me" data-aos="fade-up">
        <h2>Contact Me</h2>
        <p>{{ location }}</p>
        <p>{{ email }}</p>
        <p>{{ phone }}</p>
      </section>
    </main>
  </div>
</template>

<script>
import AOS from 'aos';
import 'aos/dist/aos.css';

import profilePicture from '@/assets/photp.jpeg';
import projectImage1 from '@/assets/Daltoneyes.png';

export default {
  data() {
    return {
      profilePicture,
      aboutDescription: 'Current freshman CSE student at Emerald High School.',
      shortContact: 'Located in Dublin California; contact thenappan4920@mydusd.org.',
      skills: 'Python, Flask, Numpy, Tensorflow, Vue.js, Chrome Extensions',
      narrative1: 'Innovation and Ambition have stained humans for all of existence andnow we have finally found what we were looking for aritificial intelligence. The only thing we need for AI is to figure out how to bring out its full potential. In the future I plan to be a computer engineer focusing on utilizing Artificial In to help others.I plan to study extensively on the mathematics of neural networks and tensorflow in college and high school in order to achieve this.This is my career choice because I have a deep intrest in neural networks and really enjoy building AI.',
      narrative2: 'I feel that I posses the charachterisics of persistence, determination and tolerence. One experience that can speak for my persistence in this class is when me and my partner were working on this one assignment we found a big challenge using this one function that was very poorly documented in python. However instead of giving up I continued to work on my assignment and test different options in order to get the assignment done on time. An experience I have had where I really exemplified my determination is when Ihad a very challenging taekwondo competition to compete in and at that time I felt like just going home but instead I pushed through and was determined to suceed and give my best at the competition. Lastly I am also tolerant as I live by the motto "It is what it is" meaning that if something happens to me which I am not proud of I should know that I tried my best and there is not anything I could have done about it. For example, if I do not do the best on a test I should learn from it instead of regretting it.',
      resumePdfLink: 'path/to/your/resume.pdf',
      narrative3:'One of my greatest skills is Taekwondo. I have won many awards in Taekwondo forms and like practicing movements and being physically active overall. The skills that came with this is good communication skills as one of the main requirements to suceed in Taekwondo is to be able to communicate effectively with others. My other skill is being able to adapt to new situations as I like the exitement, unknowns and adventure it brings. Lastly one of my greatest achievements was being able to learn calculus and AI on my own. I pride this because it taught me that I too have the ability to learn.',
      projects: [
        {
          id: 1,
          name: 'Daltoneyes',
          course: null,
          date: '4/7/2024',
          description: 'Color correction algorithm to aid the viewing experience of the colorblind.',
          role: 'Created the flask server that was set up in order to connect to the JS frontend.',
          challenges: 'Finding reliable matrices and loss calculation algorithms for the best results.',
          skills: 'Algorithm Creation, Flask, Numpy.',
          image: projectImage1, 
          documentationLink: 'https://github.com/neilmenon13/DaltonEyes'
        },
        {
          id: 2,
          name: 'Personal Portfolio',
          course: 'CSE',
          date: '5/22/2024',
          description: 'Creation of a portfolio to showcase my accomplishments and to share with the world more about myself.',
          role: 'Designed the entire webpage by learning Vue.js.',
          challenges: 'Learning Vue.js syntax and get the aos animations to work',
          skills: 'JavaScript, Vue.JS, UI.',
          image: null, 
          documentationLink: 'https://github.com/NachuT/portfolio'
        }
      ],
      location: 'Dublin, Ca',
      email: 'thenappan4920@mydusd.org',
      
      phone: 'Phone number to be added later(18)'
        };
          },
          mounted() {
            AOS.init();
          }
        };
        </script>

        <style>
        body {
            font-family: 'Roboto', sans-serif;
            color: #fff;
            background-color: #121212; 
            margin: 0;
            padding: 0;
            line-height: 1.6;
          }

          .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #b71c1c; 
            color: #fff;
            padding: 20px;
            text-align: center;
            z-index: 1000; 
          }

          h1 {
            font-size: 3rem;
            text-transform: uppercase;
            letter-spacing: 5px;
            color: #ff6f00; 
            margin: 0; 
          }

          .main {
            padding: 20px 0; 
            width: 100%; 
            max-width: 1200px;
            margin: 2000px auto 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center; 
          }

          .section {
            margin-bottom: 60px;
          }

          .project {
            margin-bottom: 40px;
            padding: 20px 0;
            transition: transform 0.3s;
            border-bottom: 1px solid #ddd; 
          }

 
          .project p {
            text-align: left;
          }

          .profile-picture {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            display: block;
            margin: 20px auto;
            border: 3px solid #ff6f00; 
            transition: transform 0.3s;
          }

          .profile-picture:hover {
            transform: scale(1.1);
          }

          .contact-info, .narrative {
            margin-top: 20px;
            font-size: 1.rem;
          }

          .project {
            margin-bottom: 40px;
            padding: 20px 0;
            transition: transform 0.3s;
          }

          .project:hover {
            transform: translateY(-10px);
          }

          .project-image {
            max-width: 100%;
            height: auto;
            margin-top: 10px;
            transition: transform 0.3s;
            border: 2px solid #ff6f00; 
          }

          .project-image:hover {
            transform: scale(1.05);
          }

          .no-image-text {
            font-size: 1.25rem;
            color: #ff6f00; 
            text-align: center;
            padding: 20px;
            border: 2px solid #ff6f00;
            border-radius: 5px;
          }

          a {
            color: #ff6f00; 
            text-decoration: none;
            font-size: 1.25rem;
            transition: color 0.3s;
          }

          a:hover {
            color: #ffcc00; 
            text-decoration: underline;
          }

          .resume-link, .doc-link {
            display: inline-block;
            margin-top: 10px;
            background-color: #b71c1c; 
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            transition: background-color 0.3s;
          }

          .resume-link:hover, .doc-link:hover {
            background-color: #ff6f00; 
          }

          .contact-me p {
            font-size: 1.25rem;
            margin: 10px 0;
          }
        </style>

