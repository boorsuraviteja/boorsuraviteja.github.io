# boorsuraviteja.github.io
# Salesforce Portfolio Website Code

Here's a complete code solution for creating a professional portfolio website based on your Salesforce expertise. I'll provide HTML, CSS, and JavaScript code that you can use to build your portfolio.

## Option 1: Simple HTML/CSS Portfolio (Single Page)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raviteja Boorsu - Salesforce Portfolio</title>
    <style>
        :root {
            --primary: #00a1e0; /* Salesforce blue */
            --secondary: #032d60; /* Dark blue */
            --accent: #ff6b35;
            --light: #f4f6f9;
            --dark: #2b2828;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--light);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--secondary), var(--primary));
            color: white;
            padding: 2rem 0;
            text-align: center;
        }
        
        .header-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid white;
            margin-bottom: 1rem;
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }
        
        .tagline {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 1rem;
        }
        
        .contact-info {
            display: flex;
            gap: 1.5rem;
            margin-bottom: 1rem;
        }
        
        .contact-info a {
            color: white;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        /* Navigation */
        nav {
            background-color: var(--primary);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            gap: 2rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        
        nav a:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }
        
        /* Section Styles */
        section {
            padding: 3rem 0;
        }
        
        section:nth-child(even) {
            background-color: white;
        }
        
        h2 {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--secondary);
            font-size: 2rem;
        }
        
        h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        /* About Section */
        .about-content {
            display: flex;
            gap: 2rem;
            align-items: center;
        }
        
        .about-text {
            flex: 2;
        }
        
        .skills {
            flex: 1;
            background-color: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .skills-list {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.5rem;
        }
        
        .skill-item {
            background-color: var(--light);
            padding: 0.5rem;
            border-radius: 4px;
            font-size: 0.9rem;
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .project-card:hover {
            transform: translateY(-5px);
        }
        
        .project-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }
        
        .tag {
            background-color: var(--light);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        
        /* Experience Section */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            width: 2px;
            background-color: var(--primary);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -1px;
        }
        
        .timeline-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            box-sizing: border-box;
        }
        
        .timeline-item:nth-child(odd) {
            left: 0;
        }
        
        .timeline-item:nth-child(even) {
            left: 50%;
        }
        
        .timeline-content {
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .timeline-date {
            font-weight: bold;
            color: var(--primary);
        }
        
        /* Certifications Section */
        .certs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
        }
        
        .cert-card {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .cert-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        /* Contact Section */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }
        
        input, textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        button {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            transition: background-color 0.3s;
        }
        
        button:hover {
            background-color: var(--secondary);
        }
        
        /* Footer */
        footer {
            background-color: var(--secondary);
            color: white;
            text-align: center;
            padding: 2rem 0;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 1rem 0;
        }
        
        .social-links a {
            color: white;
            font-size: 1.5rem;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .about-content {
                flex-direction: column;
            }
            
            .timeline::before {
                left: 31px;
            }
            
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            
            .timeline-item:nth-child(even) {
                left: 0;
            }
            
            nav ul {
                flex-direction: column;
                gap: 0.5rem;
                align-items: center;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Header Section -->
    <header>
        <div class="container header-content">
            <img src="https://via.placeholder.com/150" alt="Raviteja Boorsu" class="profile-img">
            <h1>Raviteja Boorsu</h1>
            <p class="tagline">Salesforce Administrator & Developer | 6+ Years Experience</p>
            <div class="contact-info">
                <a href="mailto:boorsuraviteja@gmail.com"><i class="fas fa-envelope"></i> boorsuraviteja@gmail.com</a>
                <a href="tel:9403444027"><i class="fas fa-phone"></i> (940) 344-4027</a>
                <a href="#"><i class="fas fa-map-marker-alt"></i> Open to Relocation (USA)</a>
            </div>
        </div>
    </header>
    
    <!-- Navigation -->
    <nav>
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#experience">Experience</a></li>
            <li><a href="#certifications">Certifications</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    
    <!-- About Section -->
    <section id="about">
        <div class="container">
            <h2>About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>I am a highly skilled and certified Salesforce Administrator and Developer with over 6+ years of experience in designing, developing, and managing Salesforce applications across diverse industries. With a Master's in Information Science and a Bachelor's in Electronics and Communication Engineering, I bring a strong technical foundation and a proven track record of delivering scalable, secure, and efficient Salesforce solutions.</p>
                    <p>My expertise spans Sales Cloud, Service Cloud, Marketing Cloud, CPQ, and Health Cloud implementations, with deep knowledge of Apex, Lightning Web Components, and integrations with AWS and other enterprise systems.</p>
                </div>
                <div class="skills">
                    <h3>Technical Skills</h3>
                    <div class="skills-list">
                        <span class="skill-item">Salesforce Admin</span>
                        <span class="skill-item">Apex Development</span>
                        <span class="skill-item">LWC/Aura</span>
                        <span class="skill-item">Sales Cloud</span>
                        <span class="skill-item">Service Cloud</span>
                        <span class="skill-item">Marketing Cloud</span>
                        <span class="skill-item">Salesforce CPQ</span>
                        <span class="skill-item">Health Cloud</span>
                        <span class="skill-item">SOQL/SOSL</span>
                        <span class="skill-item">Flows</span>
                        <span class="skill-item">REST/SOAP APIs</span>
                        <span class="skill-item">AWS Integration</span>
                        <span class="skill-item">Git/Version Control</span>
                        <span class="skill-item">Agile Methodology</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Projects Section -->
    <section id="projects">
        <div class="container">
            <h2>Featured Projects</h2>
            <div class="projects-grid">
                <!-- Project 1 -->
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x200?text=Lumen+CPQ" alt="Lumen CPQ Implementation" class="project-img">
                    <div class="project-content">
                        <h3>Lumen Technologies - CPQ Implementation</h3>
                        <p>Configured Salesforce CPQ for product bundling, pricing rules, and quote generation, improving sales efficiency by 30%.</p>
                        <div class="project-tags">
                            <span class="tag">Salesforce CPQ</span>
                            <span class="tag">Apex</span>
                            <span class="tag">LWC</span>
                            <span class="tag">AWS Lambda</span>
                        </div>
                        <a href="#" class="btn">View Details</a>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x200?text=NM+Medicaid" alt="New Mexico Medicaid" class="project-img">
                    <div class="project-content">
                        <h3>New Mexico Medicaid & Social Programs</h3>
                        <p>Built Salesforce solution for Medicaid, SNAP, LIHEAP programs with custom eligibility logic and AWS integration.</p>
                        <div class="project-tags">
                            <span class="tag">Health Cloud</span>
                            <span class="tag">Apex</span>
                            <span class="tag">Visualforce</span>
                            <span class="tag">AWS S3</span>
                        </div>
                        <a href="#" class="btn">View Details</a>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x200?text=Mondelez+Commerce" alt="Mondelez Commerce Cloud" class="project-img">
                    <div class="project-content">
                        <h3>Mondelez Commerce Cloud</h3>
                        <p>Implemented e-commerce solutions with payment gateway integration and automated KPI tracking.</p>
                        <div class="project-tags">
                            <span class="tag">Commerce Cloud</span>
                            <span class="tag">Apex Triggers</span>
                            <span class="tag">REST APIs</span>
                            <span class="tag">CI/CD</span>
                        </div>
                        <a href="#" class="btn">View Details</a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Experience Section -->
    <section id="experience">
        <div class="container">
            <h2>Professional Experience</h2>
            <div class="timeline">
                <!-- Experience 1 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Salesforce Admin/Developer</h3>
                        <p class="timeline-date">Apr 2024 - Present</p>
                        <p><strong>Lumen Technologies</strong></p>
                        <ul>
                            <li>Implemented Salesforce CPQ with pricing rules and quote generation</li>
                            <li>Integrated Marketing Cloud with Pardot and HubSpot</li>
                            <li>Developed AWS Lambda functions for automation</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Experience 2 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Salesforce Admin</h3>
                        <p class="timeline-date">Sep 2023 - Mar 2024</p>
                        <p><strong>Deloitte (Irving, TX)</strong></p>
                        <ul>
                            <li>Built Medicaid, SNAP, LIHEAP solutions on Salesforce</li>
                            <li>Created eligibility logic with Apex and LWC</li>
                            <li>Integrated with AWS for document storage</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Experience 3 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Salesforce Admin/Developer</h3>
                        <p class="timeline-date">Feb 2022 - Dec 2023</p>
                        <p><strong>Mondelez International (Hyderabad, India)</strong></p>
                        <ul>
                            <li>Implemented Commerce Cloud solutions</li>
                            <li>Automated KPI tracking with Apex</li>
                            <li>Integrated DocuSign for contracts</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Experience 4 -->
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Salesforce Admin</h3>
                        <p class="timeline-date">Jul 2019 - Jan 2022</p>
                        <p><strong>Pervacio Pvt. Ltd (Hyderabad, India)</strong></p>
                        <ul>
                            <li>Optimized Sales Cloud processes</li>
                            <li>Implemented Marketing Cloud campaigns</li>
                            <li>Created analytics with AWS QuickSight</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Certifications Section -->
    <section id="certifications">
        <div class="container">
            <h2>Certifications</h2>
            <div class="certs-grid">
                <div class="cert-card">
                    <div class="cert-icon"><i class="fab fa-salesforce"></i></div>
                    <h3>Salesforce Administrator</h3>
                    <p>Certified Salesforce Administrator with expertise in configuration and management</p>
                </div>
                
                <div class="cert-card">
                    <div class="cert-icon"><i class="fas fa-code"></i></div>
                    <h3>Salesforce Platform Developer I</h3>
                    <p>Certified in Apex, Visualforce, and Lightning component development</p>
                </div>
                
                <div class="cert-card">
                    <div class="cert-icon"><i class="fas fa-robot"></i></div>
                    <h3>Salesforce AI Associate</h3>
                    <p>Certified in Salesforce AI fundamentals and implementation</p>
                </div>
                
                <div class="cert-card">
                    <div class="cert-icon"><i class="fas fa-brain"></i></div>
                    <h3>Salesforce AI Specialist</h3>
                    <p>Advanced certification in Salesforce AI solutions</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2>Get In Touch</h2>
            <div class="contact-form">
                <form>
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" name="subject" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    
                    <button type="submit">Send Message</button>
                </form>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2024 Raviteja Boorsu. All rights reserved.</p>
            <div class="social-links">
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-trailhead"></i></a>
            </div>
            <p>Open to relocation anywhere in the USA</p>
        </div>
    </footer>
    
    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // Form submission handling
        const form = document.querySelector('form');
        form.addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I will get back to you soon.');
            form.reset();
        });
    </script>
</body>
</html>
```

## Option 2: React.js Portfolio (More Dynamic)

If you prefer a more modern approach with React, here's a starter template:

1. First, set up a React project:
```bash
npx create-react-app salesforce-portfolio
cd salesforce-portfolio
```

2. Replace the contents of `src/App.js` with:

```jsx
import React from 'react';
import { FaSalesforce, FaCode, FaRobot, FaBrain, FaEnvelope, FaPhone, FaMapMarkerAlt, FaLinkedin, FaGithub, FaTwitter } from 'react-icons/fa';
import { SiTrailhead } from 'react-icons/si';

function App() {
  const projects = [
    {
      title: "Lumen Technologies - CPQ Implementation",
      description: "Configured Salesforce CPQ for product bundling, pricing rules, and quote generation, improving sales efficiency by 30%.",
      tags: ["Salesforce CPQ", "Apex", "LWC", "AWS Lambda"],
      image: "https://via.placeholder.com/400x200?text=Lumen+CPQ"
    },
    {
      title: "New Mexico Medicaid & Social Programs",
      description: "Built Salesforce solution for Medicaid, SNAP, LIHEAP programs with custom eligibility logic and AWS integration.",
      tags: ["Health Cloud", "Apex", "Visualforce", "AWS S3"],
      image: "https://via.placeholder.com/400x200?text=NM+Medicaid"
    },
    {
      title: "Mondelez Commerce Cloud",
      description: "Implemented e-commerce solutions with payment gateway integration and automated KPI tracking.",
      tags: ["Commerce Cloud", "Apex Triggers", "REST APIs", "CI/CD"],
      image: "https://via.placeholder.com/400x200?text=Mondelez+Commerce"
    }
  ];

  const experience = [
    {
      role: "Salesforce Admin/Developer",
      company: "Lumen Technologies",
      period: "Apr 2024 - Present",
      details: [
        "Implemented Salesforce CPQ with pricing rules and quote generation",
        "Integrated Marketing Cloud with Pardot and HubSpot",
        "Developed AWS Lambda functions for automation"
      ]
    },
    {
      role: "Salesforce Admin",
      company: "Deloitte (Irving, TX)",
      period: "Sep 2023 - Mar 2024",
      details: [
        "Built Medicaid, SNAP, LIHEAP solutions on Salesforce",
        "Created eligibility logic with Apex and LWC",
        "Integrated with AWS for document storage"
      ]
    }
  ];

  const certifications = [
    {
      title: "Salesforce Administrator",
      icon: <FaSalesforce size={48} />,
      description: "Certified Salesforce Administrator with expertise in configuration and management"
    },
    {
      title: "Salesforce Platform Developer I",
      icon: <FaCode size={48} />,
      description: "Certified in Apex, Visualforce, and Lightning component development"
    },
    {
      title: "Salesforce AI Associate",
      icon: <FaRobot size={48} />,
      description: "Certified in Salesforce AI fundamentals and implementation"
    },
    {
      title: "Salesforce AI Specialist",
      icon: <FaBrain size={48} />,
      description: "Advanced certification in Salesforce AI solutions"
    }
  ];

  return (
    <div className="App">
      {/* Header Section */}
      <header className="bg-gradient-to-r from-blue-900 to-blue-500 text-white py-12 text-center">
        <div className="container mx-auto px-4">
          <div className="flex flex-col items-center">
            <img 
              src="https://via.placeholder.com/150" 
              alt="Raviteja Boorsu" 
              className="w-32 h-32 rounded-full border-4 border-white mb-4"
            />
            <h1 className="text-4xl font-bold mb-2">Raviteja Boorsu</h1>
            <p className="text-xl opacity-90 mb-4">Salesforce Administrator & Developer | 6+ Years Experience</p>
            <div className="flex gap-6 mb-4">
              <a href="mailto:boorsuraviteja@gmail.com" className="flex items-center gap-1">
                <FaEnvelope /> boorsuraviteja@gmail.com
              </a>
              <a href="tel:9403444027" className="flex items-center gap-1">
                <FaPhone /> (940) 344-4027
              </a>
              <span className="flex items-center gap-1">
                <FaMapMarkerAlt /> Open to Relocation (USA)
              </span>
            </div>
          </div>
        </div>
      </header>

      {/* Navigation */}
      <nav className="bg-blue-500 py-4 sticky top-0 z-50">
        <div className="container mx-auto px-4">
          <ul className="flex justify-center gap-8">
            <li><a href="#about" className="text-white font-bold hover:bg-white hover:bg-opacity-20 px-4 py-2 rounded">About</a></li>
            <li><a href="#projects" className="text-white font-bold hover:bg-white hover:bg-opacity-20 px-4 py-2 rounded">Projects</a></li>
            <li><a href="#experience" className="text-white font-bold hover:bg-white hover:bg-opacity-20 px-4 py-2 rounded">Experience</a></li>
            <li><a href="#certifications" className="text-white font-bold hover:bg-white hover:bg-opacity-20 px-4 py-2 rounded">Certifications</a></li>
            <li><a href="#contact" className="text-white font-bold hover:bg-white hover:bg-opacity-20 px-4 py-2 rounded">Contact</a></li>
          </ul>
        </div>
      </nav>

      {/* About Section */}
      <section id="about" className="py-12 bg-gray-50">
        <div className="container mx-auto px-4">
          <h2 className="text-3xl font-bold text-center text-blue-900 mb-8">About Me</h2>
          <div className="flex flex-col md:flex-row gap-8">
            <div className="md:w-2/3">
              <p className="mb-4">I am a highly skilled and certified Salesforce Administrator and Developer with over 6+ years of experience in designing, developing, and managing Salesforce applications across diverse industries. With a Master's in Information Science and a Bachelor's in Electronics and Communication Engineering, I bring a strong technical foundation and a proven track record of delivering scalable, secure, and efficient Salesforce solutions.</p>
              <p>My expertise spans Sales Cloud, Service Cloud, Marketing Cloud, CPQ, and Health Cloud implementations, with deep knowledge of Apex, Lightning Web Components, and integrations with AWS and other enterprise systems.</p>
            </div>
            <div className="md:w-1/3 bg-white p-6 rounded-lg shadow-md">
              <h3 className="text-xl font-bold text-blue-500 mb-4">Technical Skills</h3>
              <div className="grid grid-cols-2 gap-2">
                {[
                  "Salesforce Admin", "Apex Development", "LWC/Aura", "Sales Cloud", 
                  "Service Cloud", "Marketing Cloud", "Salesforce CPQ", "Health Cloud",
                  "SOQL/SOSL", "Flows", "REST/SOAP APIs", "AWS Integration",
                  "Git/Version Control", "Agile Methodology"
                ].map((skill, index) => (
                  <span key={index} className="bg-gray-100 px-3 py-1 rounded text-sm">
                    {skill}
                  </span>
                ))}
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Projects Section */}
      <section id="projects" className="py-12 bg-white">
        <div className="container mx-auto px-4">
          <h2 className="text-3xl font-bold text-center text-blue-900 mb-8">Featured Projects</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {projects.map((project, index) => (
              <div key={index} className="bg-white rounded-lg overflow-hidden shadow-lg hover:shadow-xl transition-shadow duration-300 hover:-translate-y-1">
                <img src={project.image} alt={project.title} className="w-full h-48 object-cover"/>
                <div className="p-6">
                  <h3 className="text-xl font-bold mb-2">{project.title}</h3>
                  <p className="text-gray-700 mb-4">{project.description}</p>
                  <div className="flex flex-wrap gap-2 mb-4">
                    {project.tags.map((tag, i) => (
                      <span key={i} className="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-xs">
                        {tag}
                      </span>
                    ))}
                  </div>
                  <button className="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded transition-colors">
                    View Details
                  </button>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Experience Section */}
      <section id="experience" className="py-12 bg-gray-50">
        <div className="container mx-auto px-4">
          <h2 className="text-3xl font-bold text-center text-blue-900 mb-8">Professional Experience</h2>
          <div className="relative max-w-3xl mx-auto">
            <div className="absolute left-1/2 w-1 h-full bg-blue-500 -ml-0.5"></div>
            {experience.map((exp, index) => (
              <div key={index} className={`mb-8 flex ${index % 2 === 0 ? 'justify-start' : 'justify-end'}`}>
                <div className={`w-5/6 p-6 rounded-lg shadow-md bg-white ${index % 2 === 0 ? 'mr-auto' : 'ml-auto'}`}>
                  <h3 className="text-xl font-bold">{exp.role}</h3>
                  <p className="text-blue-500 font-semibold">{exp.period}</p>
                  <p className="font-semibold mb-3">{exp.company}</p>
                  <ul className="list-disc pl-5">
                    {exp.details.map((detail, i) => (
                      <li key={i} className="mb-1">{detail}</li>
                    ))}
                  </ul>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Certifications Section */}
      <section id="certifications" className="py-12 bg-white">
        <div className="container mx-auto px-4">
          <h2 className="text-3xl font-bold text-center text-blue-900 mb-8">Certifications</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            {certifications.map((cert, index) => (
              <div key={index} className="bg-white p-6 rounded-lg shadow-md text-center hover:shadow-lg transition-shadow">
                <div className="text-blue-500 flex justify-center mb-4">
                  {cert.icon}
                </div>
                <h3 className="text-xl font-bold mb-2">{cert.title}</h3>
                <p className="text-gray-700">{cert.description}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-12 bg-gray-50">
        <div className="container mx-auto px-4">
          <h2 className="text-3xl font-bold text-center text-blue-900 mb-8">Get In Touch</h2>
          <div className="max-w-2xl mx-auto bg-white p-8 rounded-lg shadow-md">
            <form>
              <div className="mb-6">
                <label htmlFor="name" className="block font-bold mb-2">Name</label>
                <input 
                  type="text" 
                  id="name" 
                  className="w-full px-4 py-2 border rounded focus:outline-none focus:ring-2 focus:ring-blue-500"
                  required
                />
              </div>
              <div className="mb-6">
                <label htmlFor="email" className="block font-bold mb-2">Email</label>
                <input 
                  type="email" 
                  id="email" 
                  className="w-full px-4 py-2 border rounded focus:outline-none focus:ring-2 focus:ring-blue-500"
                  required
                />
              </div>
              <div className="mb-6">
                <label htmlFor="subject" className="block font-bold mb-2">Subject</label>
                <input 
                  type="text" 
                  id="subject" 
                  className="w-full px-4 py-2 border rounded focus:outline-none focus:ring-2 focus:ring-blue-500"
                  required
                />
              </div>
              <div className="mb-6">
                <label htmlFor="message" className="block font-bold mb-2">Message</label>
                <textarea 
                  id="message" 
                  rows="5" 
                  className="w-full px-4 py-2 border rounded focus:outline-none focus:ring-2 focus:ring-blue-500"
                  required
                ></textarea>
              </div>
              <button 
                type="submit" 
                className="bg-blue-500 hover:bg-blue-600 text-white font-bold py-3 px-6 rounded transition-colors"
              >
                Send Message
              </button>
            </form>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-blue-900 text-white py-8">
        <div className="container mx-auto px-4 text-center">
          <p>&copy; 2024 Raviteja Boorsu. All rights reserved.</p>
          <div className="flex justify-center gap-6 my-4">
            <a href="#" className="text-white hover:text-blue-300">
              <FaLinkedin size={24} />
            </a>
            <a href="#" className="text-white hover:text-blue-300">
              <FaGithub size={24} />
            </a>
            <a href="#" className="text-white hover:text-blue-300">
              <FaTwitter size={24} />
            </a>
            <a href="#" className="text-white hover:text-blue-300">
              <SiTrailhead size={24} />
            </a>
          </div>
          <p>Open to relocation anywhere in the USA</p>
        </div>
      </footer>
    </div>
