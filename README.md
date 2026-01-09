import React, { useState, useEffect } from 'react';
import { Github, Linkedin, Mail, MapPin, Phone, Code, Database, Server, Award, Briefcase, GraduationCap, ExternalLink, Menu, X, ChevronRight } from 'lucide-react';

export default function Portfolio() {
  const [activeSection, setActiveSection] = useState('home');
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [isVisible, setIsVisible] = useState({});

  useEffect(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          setIsVisible((prev) => ({
            ...prev,
            [entry.target.id]: entry.isIntersecting,
          }));
        });
      },
      { threshold: 0.1 }
    );

    document.querySelectorAll('section[id]').forEach((section) => {
      observer.observe(section);
    });

    return () => observer.disconnect();
  }, []);

  const skills = {
    frontend: ['HTML', 'CSS', 'JavaScript', 'React.js', 'Tailwind CSS', 'Bootstrap'],
    backend: ['Node.js', 'Express.js'],
    database: ['MongoDB', 'Mongoose', 'PostgreSQL'],
    tools: ['Git', 'GitHub', 'ThunderClient', 'Vite', 'Render', 'Vercel', 'REST APIs']
  };

  const projects = [
    {
      title: 'Smilesync PACS Integration',
      tech: 'React.js + Node.js',
      description: 'Medical imaging platform integrating Orthanc PACS with Stone and Osmosis Viewers for secure DICOM study access.',
      features: [
        'Advanced reporting with generate, print, export, and email options',
        'Dynamic report templates linked to patient records',
        'Scalable patient and user management with role-based access',
        'Modality Worklist (MWL) integration for hospital communication'
      ]
    },
    {
      title: 'Food Delivery System',
      tech: 'React.js + Node.js',
      description: 'Full-stack food delivery platform with real-time order processing and secure authentication.',
      features: [
        'Real-time order processing for seamless management',
        'JWT-based authentication and role-based authorization',
        'MongoDB, Express.js, React, and Node.js stack',
        'Dynamic and responsive user interface'
      ]
    },
    {
      title: 'Zerodha Trading Platform',
      tech: 'React.js + Node.js',
      description: 'Real-time trading platform for buying and selling stocks with live market data.',
      features: [
        'Live market data integration with Chart.js visualization',
        'JWT authentication and data encryption for secure transactions',
        'Dynamic dashboard with real-time stock updates',
        'Complete MERN stack implementation'
      ]
    }
  ];

  const experience = {
    role: 'Intern Developer',
    company: 'Subharti University',
    period: '2025 – Present',
    responsibilities: [
      'Contributing to full-stack development projects using React.js, Node.js, and PostgreSQL',
      'Collaborating with senior developers to implement new features and improve performance',
      'Writing clean, reusable code while learning deployment and version control best practices'
    ]
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 text-white">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-slate-900/80 backdrop-blur-lg z-50 border-b border-purple-500/20">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex items-center justify-between h-16">
            <div className="flex items-center">
              <span className="text-2xl font-bold bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
                SD
              </span>
            </div>
            
            <div className="hidden md:block">
              <div className="flex items-center space-x-8">
                {['Home', 'About', 'Skills', 'Projects', 'Experience', 'Contact'].map((item) => (
                  <a
                    key={item}
                    href={`#${item.toLowerCase()}`}
                    className="hover:text-purple-400 transition-colors duration-300 text-sm font-medium"
                  >
                    {item}
                  </a>
                ))}
              </div>
            </div>

            <button
              onClick={() => setIsMenuOpen(!isMenuOpen)}
              className="md:hidden p-2 rounded-md hover:bg-purple-500/20 transition-colors"
            >
              {isMenuOpen ? <X size={24} /> : <Menu size={24} />}
            </button>
          </div>
        </div>

        {/* Mobile menu */}
        {isMenuOpen && (
          <div className="md:hidden bg-slate-900 border-t border-purple-500/20">
            <div className="px-2 pt-2 pb-3 space-y-1">
              {['Home', 'About', 'Skills', 'Projects', 'Experience', 'Contact'].map((item) => (
                <a
                  key={item}
                  href={`#${item.toLowerCase()}`}
                  onClick={() => setIsMenuOpen(false)}
                  className="block px-3 py-2 rounded-md hover:bg-purple-500/20 transition-colors"
                >
                  {item}
                </a>
              ))}
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section id="home" className="min-h-screen flex items-center justify-center pt-16 px-4">
        <div className="text-center max-w-4xl mx-auto">
          <div className="mb-8 relative">
            <div className="w-40 h-40 mx-auto rounded-full bg-gradient-to-r from-purple-500 to-pink-500 p-1 animate-pulse">
              <div className="w-full h-full rounded-full bg-slate-900 flex items-center justify-center text-6xl font-bold">
                SD
              </div>
            </div>
          </div>
          
          <h1 className="text-5xl md:text-7xl font-bold mb-4 bg-gradient-to-r from-purple-400 via-pink-400 to-purple-400 bg-clip-text text-transparent animate-fade-in">
            Suhani Dhamania
          </h1>
          
          <p className="text-2xl md:text-3xl text-purple-300 mb-6">
            MERN Stack Developer | React Enthusiast 🚀
          </p>
          
          <p className="text-lg text-gray-300 mb-8 max-w-2xl mx-auto">
            Self-driven and passionate developer building responsive and scalable full-stack web applications
          </p>

          <div className="flex flex-wrap justify-center gap-4 mb-8">
            <a
              href="https://github.com/suhaniDhamania"
              target="_blank"
              rel="noopener noreferrer"
              className="flex items-center gap-2 px-6 py-3 bg-purple-600 hover:bg-purple-700 rounded-full transition-all duration-300 transform hover:scale-105"
            >
              <Github size={20} />
              GitHub
            </a>
            <a
              href="https://www.linkedin.com/in/suhanidhamania"
              target="_blank"
              rel="noopener noreferrer"
              className="flex items-center gap-2 px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded-full transition-all duration-300 transform hover:scale-105"
            >
              <Linkedin size={20} />
              LinkedIn
            </a>
            <a
              href="https://portfolio-app-726d.onrender.com"
              target="_blank"
              rel="noopener noreferrer"
              className="flex items-center gap-2 px-6 py-3 bg-pink-600 hover:bg-pink-700 rounded-full transition-all duration-300 transform hover:scale-105"
            >
              <ExternalLink size={20} />
              Portfolio
            </a>
          </div>

          <div className="flex flex-wrap justify-center gap-4 text-sm text-gray-400">
            <div className="flex items-center gap-2">
              <MapPin size={16} />
              Ellahabas, Noida, UP
            </div>
            <div className="flex items-center gap-2">
              <Phone size={16} />
              +91 8851648618
            </div>
            <div className="flex items-center gap-2">
              <Mail size={16} />
              suhanidhamania157@gmail.com
            </div>
          </div>

          <div className="mt-12 text-gray-400">
            <img 
              src="https://komarev.com/ghpvc/?username=suhaniDhamania&label=Profile%20views&color=0e75b6&style=flat" 
              alt="Profile views"
              className="inline-block"
            />
          </div>
        </div>
      </section>

      {/* About Section */}
      <section id="about" className="min-h-screen flex items-center justify-center py-20 px-4">
        <div className="max-w-4xl mx-auto">
          <h2 className="text-4xl md:text-5xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            About Me
          </h2>
          
          <div className="grid md:grid-cols-2 gap-8">
            <div className="bg-slate-800/50 backdrop-blur-lg p-8 rounded-2xl border border-purple-500/20 transform hover:scale-105 transition-all duration-300">
              <GraduationCap className="w-12 h-12 text-purple-400 mb-4" />
              <h3 className="text-2xl font-bold mb-4">Education</h3>
              <p className="text-gray-300 mb-2">
                <strong>Bachelor of Computer Applications (BCA)</strong>
              </p>
              <p className="text-gray-400 mb-4">PIIT College, Greater Noida | 2023 – Present</p>
              <p className="text-gray-300 mb-2">
                <strong>Senior Secondary Education</strong>
              </p>
              <p className="text-gray-400">Shaiffali Public School, Dadri | 2023</p>
            </div>

            <div className="bg-slate-800/50 backdrop-blur-lg p-8 rounded-2xl border border-purple-500/20 transform hover:scale-105 transition-all duration-300">
              <Award className="w-12 h-12 text-pink-400 mb-4" />
              <h3 className="text-2xl font-bold mb-4">Certifications</h3>
              <p className="text-gray-300 mb-2">
                <strong>MERN Stack Development</strong>
              </p>
              <p className="text-gray-400 mb-4">Sigma 4.0 Program - Apna College</p>
              <p className="text-sm text-gray-400">
                Completed full-stack development training including React.js, Node.js, MongoDB, API development, and deployment
              </p>
            </div>
          </div>

          <div className="mt-8 bg-slate-800/50 backdrop-blur-lg p-8 rounded-2xl border border-purple-500/20">
            <h3 className="text-2xl font-bold mb-6 flex items-center gap-2">
              <ChevronRight className="text-purple-400" />
              Current Focus
            </h3>
            <div className="grid md:grid-cols-2 gap-4">
              <div className="flex items-start gap-3">
                <div className="w-2 h-2 bg-purple-400 rounded-full mt-2"></div>
                <p className="text-gray-300">🌱 Currently learning MERN Stack</p>
              </div>
              <div className="flex items-start gap-3">
                <div className="w-2 h-2 bg-purple-400 rounded-full mt-2"></div>
                <p className="text-gray-300">💡 Interested in Backend + Dashboard UI</p>
              </div>
              <div className="flex items-start gap-3">
                <div className="w-2 h-2 bg-purple-400 rounded-full mt-2"></div>
                <p className="text-gray-300">💻 Love building real-world projects</p>
              </div>
              <div className="flex items-start gap-3">
                <div className="w-2 h-2 bg-purple-400 rounded-full mt-2"></div>
                <p className="text-gray-300">🎯 Goal: Freelancing & Open Source</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Skills Section */}
      <section id="skills" className="min-h-screen flex items-center justify-center py-20 px-4">
        <div className="max-w-6xl mx-auto w-full">
          <h2 className="text-4xl md:text-5xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Tech Stack
          </h2>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            <div className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-purple-500/20 transform hover:scale-105 transition-all duration-300">
              <Code className="w-10 h-10 text-purple-400 mb-4" />
              <h3 className="text-xl font-bold mb-4">Frontend</h3>
              <div className="flex flex-wrap gap-2">
                {skills.frontend.map((skill) => (
                  <span key={skill} className="px-3 py-1 bg-purple-500/20 rounded-full text-sm">
                    {skill}
                  </span>
                ))}
              </div>
            </div>

            <div className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-pink-500/20 transform hover:scale-105 transition-all duration-300">
              <Server className="w-10 h-10 text-pink-400 mb-4" />
              <h3 className="text-xl font-bold mb-4">Backend</h3>
              <div className="flex flex-wrap gap-2">
                {skills.backend.map((skill) => (
                  <span key={skill} className="px-3 py-1 bg-pink-500/20 rounded-full text-sm">
                    {skill}
                  </span>
                ))}
              </div>
            </div>

            <div className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-blue-500/20 transform hover:scale-105 transition-all duration-300">
              <Database className="w-10 h-10 text-blue-400 mb-4" />
              <h3 className="text-xl font-bold mb-4">Database</h3>
              <div className="flex flex-wrap gap-2">
                {skills.database.map((skill) => (
                  <span key={skill} className="px-3 py-1 bg-blue-500/20 rounded-full text-sm">
                    {skill}
                  </span>
                ))}
              </div>
            </div>

            <div className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-green-500/20 transform hover:scale-105 transition-all duration-300">
              <Award className="w-10 h-10 text-green-400 mb-4" />
              <h3 className="text-xl font-bold mb-4">Tools</h3>
              <div className="flex flex-wrap gap-2">
                {skills.tools.map((skill) => (
                  <span key={skill} className="px-3 py-1 bg-green-500/20 rounded-full text-sm">
                    {skill}
                  </span>
                ))}
              </div>
            </div>
          </div>

          <div className="mt-12 text-center">
            <img 
              src="https://skillicons.dev/icons?i=html,css,js,react,nodejs,express,mongodb,git,github" 
              alt="Tech Stack Icons"
              className="inline-block"
            />
          </div>
        </div>
      </section>

      {/* Projects Section */}
      <section id="projects" className="min-h-screen flex items-center justify-center py-20 px-4">
        <div className="max-w-6xl mx-auto w-full">
          <h2 className="text-4xl md:text-5xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Featured Projects
          </h2>

          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            {projects.map((project, index) => (
              <div
                key={index}
                className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-purple-500/20 transform hover:scale-105 transition-all duration-300 hover:shadow-2xl hover:shadow-purple-500/20"
              >
                <div className="mb-4">
                  <h3 className="text-2xl font-bold mb-2">{project.title}</h3>
                  <span className="text-sm text-purple-400">{project.tech}</span>
                </div>
                
                <p className="text-gray-300 mb-4">{project.description}</p>
                
                <div className="space-y-2">
                  {project.features.map((feature, idx) => (
                    <div key={idx} className="flex items-start gap-2">
                      <ChevronRight size={16} className="text-purple-400 mt-1 flex-shrink-0" />
                      <p className="text-sm text-gray-400">{feature}</p>
                    </div>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Experience Section */}
      <section id="experience" className="min-h-screen flex items-center justify-center py-20 px-4">
        <div className="max-w-4xl mx-auto w-full">
          <h2 className="text-4xl md:text-5xl font-bold mb-12 text-center bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Experience
          </h2>

          <div className="bg-slate-800/50 backdrop-blur-lg p-8 rounded-2xl border border-purple-500/20">
            <div className="flex items-start gap-4 mb-6">
              <Briefcase className="w-12 h-12 text-purple-400 flex-shrink-0" />
              <div>
                <h3 className="text-2xl font-bold mb-2">{experience.role}</h3>
                <p className="text-purple-400 text-lg mb-1">{experience.company}</p>
                <p className="text-gray-400 text-sm">{experience.period}</p>
              </div>
            </div>

            <div className="space-y-3">
              <h4 className="text-lg font-semibold text-gray-200">Key Responsibilities:</h4>
              {experience.responsibilities.map((resp, index) => (
                <div key={index} className="flex items-start gap-3">
                  <ChevronRight size={20} className="text-purple-400 mt-1 flex-shrink-0" />
                  <p className="text-gray-300">{resp}</p>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="min-h-screen flex items-center justify-center py-20 px-4">
        <div className="max-w-4xl mx-auto w-full text-center">
          <h2 className="text-4xl md:text-5xl font-bold mb-12 bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
            Let's Connect
          </h2>

          <div className="grid md:grid-cols-3 gap-6 mb-12">
            <a
              href="mailto:suhanidhamania157@gmail.com"
              className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-purple-500/20 hover:border-purple-400 transition-all duration-300 transform hover:scale-105"
            >
              <Mail className="w-12 h-12 text-purple-400 mx-auto mb-4" />
              <h3 className="font-bold mb-2">Email</h3>
              <p className="text-sm text-gray-400 break-all">suhanidhamania157@gmail.com</p>
            </a>

            <a
              href="https://www.linkedin.com/in/suhanidhamania"
              target="_blank"
              rel="noopener noreferrer"
              className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-blue-500/20 hover:border-blue-400 transition-all duration-300 transform hover:scale-105"
            >
              <Linkedin className="w-12 h-12 text-blue-400 mx-auto mb-4" />
              <h3 className="font-bold mb-2">LinkedIn</h3>
              <p className="text-sm text-gray-400">Connect with me</p>
            </a>

            <a
              href="https://github.com/suhaniDhamania"
              target="_blank"
              rel="noopener noreferrer"
              className="bg-slate-800/50 backdrop-blur-lg p-6 rounded-2xl border border-pink-500/20 hover:border-pink-400 transition-all duration-300 transform hover:scale-105"
            >
              <Github className="w-12 h-12 text-pink-400 mx-auto mb-4" />
              <h3 className="font-bold mb-2">GitHub</h3>
              <p className="text-sm text-gray-400">Check my repositories</p>
            </a>
          </div>

          <div className="bg-slate-800/50 backdrop-blur-lg p-8 rounded-2xl border border-purple-500/20">
            <p className="text-xl text-gray-300 mb-4">
              ✨ Thanks for visiting my profile!
            </p>
            <p className="text-gray-400">
              ⭐ Don't forget to check my repositories
            </p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-8 text-center text-gray-400 border-t border-purple-500/20">
        <p>© 2025 Suhani Dhamania. Built with React & Tailwind CSS</p>
      </footer>
    </div>
  );
}
