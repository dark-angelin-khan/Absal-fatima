<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Absal Khan | Premium Web Solutions</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    
    <style>
        :root {
            --primary: #00acc1;
            --primary-glow: rgba(0, 172, 193, 0.4);
            --dark-bg: #050505;
            --glass: rgba(255, 255, 255, 0.03);
            --glass-border: rgba(255, 255, 255, 0.08);
            --text-main: #ffffff;
            --text-dim: #b0b0b0;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }
        body { background-color: var(--dark-bg); color: var(--text-main); overflow-x: hidden; scroll-behavior: smooth; }

        /* Scrollbar */
        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-track { background: #000; }
        ::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 10px; }

        /* Typography & Global */
        .section-padding { padding: 120px 8%; }
        .section-title { font-size: 3.5rem; font-weight: 800; margin-bottom: 60px; line-height: 1.2; }
        .section-title span { color: var(--primary); }
        .highlight { color: var(--primary); }
        
        .btn { 
            padding: 18px 40px; border-radius: 50px; text-decoration: none; font-weight: 600; 
            transition: 0.4s; display: inline-block; cursor: pointer; border: none;
            letter-spacing: 1px; text-transform: uppercase; font-size: 0.8rem;
        }
        .btn-primary { background: var(--primary); color: #000; box-shadow: 0 10px 20px var(--primary-glow); }
        .btn-primary:hover { transform: translateY(-5px); box-shadow: 0 15px 30px var(--primary); }

        /* Navbar */
        nav {
            display: flex; justify-content: space-between; align-items: center;
            padding: 30px 8%; position: fixed; width: 100%; top: 0;
            background: rgba(5, 5, 5, 0.7); backdrop-filter: blur(15px);
            z-index: 2000; border-bottom: 1px solid var(--glass-border); transition: 0.4s;
        }
        .logo { font-size: 1.5rem; font-weight: 800; letter-spacing: 3px; color: #fff; }
        .logo span { color: var(--primary); }
        .nav-links { display: flex; list-style: none; gap: 30px; }
        .nav-links a { text-decoration: none; color: var(--text-dim); font-size: 0.8rem; font-weight: 500; transition: 0.3s; }
        .nav-links a:hover { color: var(--primary); }

        /* Hero */
        .hero {
            height: 100vh; display: flex; align-items: center; position: relative;
            padding: 0 8%; overflow: hidden;
        }
        #hero-canvas { position: absolute; top: 0; left: 0; width: 100%; height: 100%; opacity: 0.5; }
        .hero-content { position: relative; z-index: 10; max-width: 900px; }
        .hero-content h4 { letter-spacing: 8px; color: var(--primary); font-weight: 400; margin-bottom: 20px; }
        .hero-content h1 { font-size: 6rem; font-weight: 800; line-height: 1; margin-bottom: 30px; }
        
        /* Stats Section */
        .stats-bar { 
            display: flex; justify-content: space-between; padding: 60px 8%;
            background: var(--glass); border-top: 1px solid var(--glass-border); border-bottom: 1px solid var(--glass-border);
        }
        .stat-item h2 { font-size: 3rem; color: var(--primary); }
        .stat-item p { color: var(--text-dim); font-size: 0.9rem; }

        /* Bento Services Grid */
        .services-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
        .service-card {
            background: var(--glass); border: 1px solid var(--glass-border);
            padding: 40px; border-radius: 20px; transition: 0.4s;
        }
        .service-card:hover { border-color: var(--primary); background: rgba(0, 172, 193, 0.05); transform: translateY(-10px); }
        .service-card i { font-size: 2.5rem; color: var(--primary); margin-bottom: 20px; }
        .large-card { grid-column: span 2; display: flex; gap: 30px; align-items: center; }

        /* Tech Marquee */
        .tech-marquee { padding: 40px 0; background: #080808; overflow: hidden; white-space: nowrap; border-bottom: 1px solid var(--glass-border); }
        .marquee-content { display: inline-block; animation: marquee 20s linear infinite; }
        .marquee-content span { font-size: 1.5rem; font-weight: 700; color: #222; margin: 0 40px; text-transform: uppercase; letter-spacing: 5px; }
        @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }

        /* Process Section */
        .process-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; }
        .process-item { position: relative; padding: 30px; border-left: 1px solid var(--primary); }
        .process-number { font-size: 4rem; font-weight: 800; color: rgba(0,172,193,0.1); position: absolute; top: 0; left: 10px; z-index: -1; }

        /* Portfolio */
        .work-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(400px, 1fr)); gap: 30px; }
        .work-box {
            border-radius: 24px; overflow: hidden; position: relative; height: 400px;
            background: #111; border: 1px solid var(--glass-border);
        }
        .work-box img { width: 100%; height: 100%; object-fit: cover; opacity: 0.6; transition: 0.5s; }
        .work-box:hover img { transform: scale(1.1); opacity: 0.3; }
        .work-overlay {
            position: absolute; inset: 0; padding: 40px; display: flex; flex-direction: column; justify-content: flex-end;
            background: linear-gradient(to top, rgba(0,0,0,0.9), transparent);
        }

        /* Skills Section Styles */
        .skill-bar-container { margin-bottom: 25px; }
        .skill-label { display: flex; justify-content: space-between; margin-bottom: 10px; font-weight: 600; font-size: 0.9rem; }
        .skill-progress { background: var(--glass); height: 8px; border-radius: 10px; overflow: hidden; border: 1px solid var(--glass-border); }
        .skill-fill { background: var(--primary); height: 100%; border-radius: 10px; box-shadow: 0 0 15px var(--primary-glow); }

        /* Contact Form Styles */
        .input-group { margin-bottom: 20px; }
        .input-group input, .input-group textarea {
            width: 100%; padding: 15px 20px; background: var(--glass); border: 1px solid var(--glass-border);
            border-radius: 12px; color: #fff; outline: none; transition: 0.3s;
        }
        .input-group input:focus, .input-group textarea:focus { border-color: var(--primary); background: rgba(255,255,255,0.05); }

        /* FAQ Section */
        .faq-container { max-width: 800px; margin: 0 auto; }
        .faq-item { background: var(--glass); margin-bottom: 15px; border-radius: 12px; overflow: hidden; border: 1px solid var(--glass-border); }
        .faq-question { padding: 20px; cursor: pointer; display: flex; justify-content: space-between; font-weight: 600; }
        .faq-answer { padding: 0 20px; max-height: 0; overflow: hidden; transition: 0.4s; color: var(--text-dim); }
        .faq-item.active .faq-answer { padding: 0 20px 20px; max-height: 200px; }

        /* Footer */
        footer { padding: 100px 8% 50px; background: #020202; border-top: 1px solid var(--glass-border); }
        .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 50px; margin-bottom: 80px; }
        .footer-logo { font-size: 2rem; font-weight: 800; margin-bottom: 20px; }
        .footer-links h4 { margin-bottom: 20px; color: var(--primary); font-size: 1.1rem; }
        .footer-links ul { list-style: none; }
        .footer-links li { margin-bottom: 10px; color: var(--text-dim); font-size: 0.9rem; cursor: pointer; transition: 0.3s; }
        .footer-links li:hover { color: #fff; transform: translateX(5px); }

        @media (max-width: 992px) {
            .hero-content h1 { font-size: 3.5rem; }
            .services-grid { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
            .large-card { flex-direction: column; align-items: flex-start; }
        }
    </style>
</head>
<body>

    <nav id="navbar">
        <div class="logo">ABSAL<span>KHAN</span></div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#work">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <a href="https://wa.me/9230003556756" class="btn btn-primary" style="padding: 12px 30px;">Get Started</a>
    </nav>

    <section class="hero" id="home">
        <canvas id="hero-canvas"></canvas>
        <div class="hero-content" data-aos="fade-up">
            <h4>DIGITAL ARTISAN</h4>
            <h1>Turning Code Into <span class="highlight">Masterpieces.</span></h1>
            <p style="color: var(--text-dim); font-size: 1.2rem; margin-bottom: 40px; max-width: 700px;">
                Main Absal hoon—Karachi-based Web Developer & UI Designer. Main modern brands ke liye fast, aesthetic aur high-converting digital products banata hoon.
            </p>
            <div class="hero-btns">
                <a href="#work" class="btn btn-primary">View My Work</a>
                <a href="#contact" style="color: #fff; margin-left: 30px; text-decoration: none; font-weight: 600;">Contact Me →</a>
            </div>
        </div>
    </section>

    <div class="tech-marquee">
        <div class="marquee-content">
            <span>HTML5</span> <span>CSS3</span> <span>JAVASCRIPT</span> <span>REACT.JS</span> <span>WORDPRESS</span> <span>FIGMA</span> <span>UI/UX</span> <span>SEO</span>
            <span>HTML5</span> <span>CSS3</span> <span>JAVASCRIPT</span> <span>REACT.JS</span> <span>WORDPRESS</span> <span>FIGMA</span> <span>UI/UX</span> <span>SEO</span>
        </div>
    </div>

    <div class="stats-bar">
        <div class="stat-item" data-aos="zoom-in">
            <h2>50+</h2>
            <p>Projects Done</p>
        </div>
        <div class="stat-item" data-aos="zoom-in" data-aos-delay="100">
            <h2>30+</h2>
            <p>Happy Clients</p>
        </div>
        <div class="stat-item" data-aos="zoom-in" data-aos-delay="200">
            <h2>2Y+</h2>
            <p>Industry Exp.</p>
        </div>
        <div class="stat-item" data-aos="zoom-in" data-aos-delay="300">
            <h2>99%</h2>
            <p>Success Rate</p>
        </div>
    </div>

    <section class="section-padding" id="services">
        <h2 class="section-title" data-aos="fade-right">Premium <span>Services</span></h2>
        <div class="services-grid">
            <div class="service-card large-card" data-aos="fade-up">
                <i class="fas fa-code"></i>
                <div>
                    <h3>Custom Web Development</h3>
                    <p style="color: var(--text-dim); margin-top: 10px;">React.js aur Modern JS ES6+ ka use karkay high-speed web apps build karna meri specialty hai. No slow code, just performance.</p>
                </div>
            </div>
            <div class="service-card" data-aos="fade-up" data-aos-delay="100">
                <i class="fab fa-wordpress"></i>
                <h3>WordPress Expert</h3>
                <p style="color: var(--text-dim);">Custom themes, Elementor Pro customization aur WooCommerce store setup.</p>
            </div>
            <div class="service-card" data-aos="fade-up">
                <i class="fas fa-search-dollar"></i>
                <h3>SEO & Analytics</h3>
                <p style="color: var(--text-dim);">Google Search Console integration aur Indexing taakay aapki site rank kare.</p>
            </div>
            <div class="service-card large-card" data-aos="fade-up" data-aos-delay="100">
                <i class="fas fa-paint-brush"></i>
                <div>
                    <h3>UI/UX & Branding</h3>
                    <p style="color: var(--text-dim); margin-top: 10px;">Figma designs se lekar real-world packaging tak, main har cheez ko luxury look deta hoon.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="section-padding" id="skills" style="background: #020202;">
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 80px; align-items: center;">
            <div data-aos="fade-right">
                <h2 class="section-title">Technical <br><span>Expertise.</span></h2>
                <p style="color: var(--text-dim); margin-bottom: 30px;">Har line of code ko optimized aur har design ko pixel-perfect banana hi meri pehchan hai.</p>
                <a href="#contact" class="btn btn-primary">Hire Me Now</a>
            </div>
            <div data-aos="fade-left">
                <div class="skill-bar-container">
                    <div class="skill-label"><span>Frontend Development</span><span>95%</span></div>
                    <div class="skill-progress"><div class="skill-fill" style="width: 95%;"></div></div>
                </div>
                <div class="skill-bar-container">
                    <div class="skill-label"><span>WordPress & CMS</span><span>90%</span></div>
                    <div class="skill-progress"><div class="skill-fill" style="width: 90%;"></div></div>
                </div>
                <div class="skill-bar-container">
                    <div class="skill-label"><span>UI/UX Design (Figma)</span><span>85%</span></div>
                    <div class="skill-progress"><div class="skill-fill" style="width: 85%;"></div></div>
                </div>
                <div class="skill-bar-container">
                    <div class="skill-label"><span>SEO & Performance</span><span>80%</span></div>
                    <div class="skill-progress"><div class="skill-fill" style="width: 80%;"></div></div>
                </div>
            </div>
        </div>
    </section>

    <section class="section-padding" id="process" style="background: #050505;">
        <h2 class="section-title" data-aos="fade-up">My <span>Process</span></h2>
        <div class="process-grid">
            <div class="process-item" data-aos="fade-up">
                <div class="process-number">01</div>
                <h3>Discovery</h3>
                <p style="color: var(--text-dim);">Main aapke business goals ko samajhta hoon taakay sahi strategy ban sake.</p>
            </div>
            <div class="process-item" data-aos="fade-up" data-aos-delay="100">
                <div class="process-number">02</div>
                <h3>Design</h3>
                <p style="color: var(--text-dim);">Aesthetic UI designs bante hain Figma par jo aapke brand ko suit karein.</p>
            </div>
            <div class="process-item" data-aos="fade-up" data-aos-delay="200">
                <div class="process-number">03</div>
                <h3>Development</h3>
                <p style="color: var(--text-dim);">Clean code ke saath aapki website live environment mein build hoti hai.</p>
            </div>
            <div class="process-item" data-aos="fade-up" data-aos-delay="300">
                <div class="process-number">04</div>
                <h3>Launch</h3>
                <p style="color: var(--text-dim);">Testing aur SEO indexing ke baad project ko final launch kiya jata hai.</p>
            </div>
        </div>
    </section>

    <section class="section-padding" id="work" style="background: #080808;">
        <h2 class="section-title" data-aos="fade-up">Featured <span>Projects</span></h2>
        <div class="work-container">
            <div class="work-box" data-aos="zoom-in">
                <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?auto=format&fit=crop&w=800&q=80" alt="Amada Perfumes">
                <div class="work-overlay">
                    <span style="color: var(--primary); font-size: 0.8rem; font-weight: 600;">BRANDING</span>
                    <h3>legend Identity</h3>
                    <p style="color: var(--text-dim); font-size: 0.9rem;">Luxury packaging and digital store design.</p>
                </div>
            </div>
            <div class="work-box" data-aos="zoom-in" data-aos-delay="100">
                <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&w=800&q=80" alt="E-com">
                <div class="work-overlay">
                    <span style="color: var(--primary); font-size: 0.8rem; font-weight: 600;">DEVELOPMENT</span>
                    <h3>Modern E-Commerce Engine</h3>
                    <p style="color: var(--text-dim); font-size: 0.9rem;">Built with custom JS cart system & Responsive UI.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="section-padding" style="background: #020202;">
        <h2 class="section-title" style="text-align: center;" data-aos="fade-up">Trusted By <span>Clients</span></h2>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;">
            <div class="service-card" data-aos="fade-up">
                <i class="fas fa-quote-left" style="font-size: 1.5rem; opacity: 0.2;"></i>
                <p style="margin: 20px 0; color: var(--text-dim); font-style: italic;">"Absal ne hamari brand identity ko completely change kar diya. Design sense kafi modern hai."</p>
                <h4>Bussif Rashid Boss</h4>
                <small style="color: var(--primary);">Premium Client</small>
            </div>
            <div class="service-card" data-aos="fade-up" data-aos-delay="100">
                <i class="fas fa-quote-left" style="font-size: 1.5rem; opacity: 0.2;"></i>
                <p style="margin: 20px 0; color: var(--text-dim); font-style: italic;">"Work speed aur communication kafi behtar thi. Highly recommended for E-commerce projects."</p>
                <h4>Alish</h4>
                <small style="color: var(--primary);">Founder</small>
            </div>
        </div>
    </section>

    <section class="section-padding">
        <h2 class="section-title" style="text-align: center;">Frequently Asked <span>Questions</span></h2>
        <div class="faq-container">
            <div class="faq-item" data-aos="fade-up">
                <div class="faq-question">What technologies do you use? <i class="fas fa-plus"></i></div>
                <div class="faq-answer">I work with HTML5, CSS3, JavaScript (ES6+), React.js, WordPress, and Figma.</div>
            </div>
            <div class="faq-item" data-aos="fade-up" data-aos-delay="100">
                <div class="faq-question">Do you offer SEO services? <i class="fas fa-plus"></i></div>
                <div class="faq-answer">Yes! Every website I build is SEO-optimized and indexed via Google Search Console.</div>
            </div>
        </div>
    </section>

    <section class="section-padding" id="contact" style="background: #080808;">
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 50px;">
            <div data-aos="fade-right">
                <h2 class="section-title">Let's Build <br><span>Together.</span></h2>
                <p style="color: var(--text-dim); margin-bottom: 30px;">Aapka project mere liye sirf aik kaam nahi, aik masterpiece hai. Rabta karein aur aaj hi start karein.</p>
                <div style="display: flex; gap: 20px;">
                    <a href="https://wa.me/9230003556756" class="btn btn-primary">WhatsApp Me</a>
                </div>
            </div>
            <div data-aos="fade-left">
                <form action="#">
                    <div class="input-group"><input type="text" placeholder="Full Name" required></div>
                    <div class="input-group"><input type="email" placeholder="Email Address" required></div>
                    <div class="input-group"><textarea rows="5" placeholder="Project Details"></textarea></div>
                    <button type="submit" class="btn btn-primary" style="width: 100%;">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-grid">
            <div>
                <div class="footer-logo">ABSAL<span>.</span></div>
                <p style="color: var(--text-dim);">Karachi-based expert delivering high-performance web solutions for the modern age.</p>
            </div>
            <div class="footer-links">
                <h4>Navigation</h4>
                <ul>
                    <li>Home</li>
                    <li>Services</li>
                    <li>Projects</li>
                    <li>Contact</li>
                </ul>
            </div>
            <div class="footer-links">
                <h4>Legal</h4>
                <ul>
                    <li>Privacy Policy</li>
                    <li>Terms of Service</li>
                </ul>
            </div>
        </div>
        <p style="text-align: center; color: #444; font-size: 0.8rem; border-top: 1px solid #111; padding-top: 30px;">
            © 2026 Absal Khan. All Rights Reserved. Built with <i class="fas fa-heart" style="color: var(--primary);"></i> in Karachi.
        </p>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1000, once: true });

        const canvas = document.getElementById('hero-canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];
        function resize() { canvas.width = window.innerWidth; canvas.height = window.innerHeight; }
        window.addEventListener('resize', resize); resize();

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2;
                this.spX = Math.random() * 1 - 0.5;
                this.spY = Math.random() * 1 - 0.5;
            }
            update() {
                this.x += this.spX; this.y += this.spY;
                if (this.x > canvas.width || this.x < 0) this.spX *= -1;
                if (this.y > canvas.height || this.y < 0) this.spY *= -1;
            }
            draw() { ctx.fillStyle = '#00acc1'; ctx.beginPath(); ctx.arc(this.x, this.y, this.size, 0, Math.PI*2); ctx.fill(); }
        }
        function init() { for(let i=0; i<80; i++) particles.push(new Particle()); }
        function animate() { ctx.clearRect(0,0,canvas.width,canvas.height); particles.forEach(p=>{p.update(); p.draw();}); requestAnimationFrame(animate); }
        init(); animate();

        document.querySelectorAll('.faq-question').forEach(item => {
            item.addEventListener('click', () => {
                const parent = item.parentElement;
                parent.classList.toggle('active');
            });
        });

        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if(window.scrollY > 50) {
                nav.style.padding = '15px 8%';
                nav.style.background = 'rgba(5, 5, 5, 0.95)';
            } else {
                nav.style.padding = '30px 8%';
                nav.style.background = 'rgba(5, 5, 5, 0.7)';
            }
        });
    </script>
</body>
</html>
