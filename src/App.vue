<template>
  <div id="app">
    <!-- Navigation -->
    <nav class="navbar border-bottom navbar-expand-lg navbar-light sticky-top navbar-custom">
      <div class="container">
        <a class="navbar-brand d-flex align-items-center" href="#home">
          <img :src="kanuruLogo" alt="Kanuru Infosystems" width="32" height="32" class="me-2">
          <span class="fw-bold text-dark">Kanuru<span class="red">Tech</span></span>
        </a>
        
        <button 
          class="navbar-toggler" 
          type="button" 
          data-bs-toggle="collapse" 
          data-bs-target="#navbarNav"
          @click="toggleMobileMenu"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="#home">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#services">Services</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#about">About</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#contact">Contact</a>
            </li>
            <li class="nav-item">
              <!-- <button class="btn gradient-bg text-white ms-2">Get Started</button> -->
              
              <a  class="btn gradient-bg text-white ms-2" href="#contact">Get Started</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero-section">
      <div class="container">
        <div class="row justify-content-center text-center pt-1">
          <div class="col-lg-10">
            <h1 class="display-4 fw-bold mb-4  fade-in">
              Welcome to 
              <span class="gradient-text">Kanuru Infosystems</span>
            </h1>
            
            <div class="h4 text-muted mb-4 fade-in">
              Innovating at the Intersection of 
              <span class="gradient-text fw-bold">{{ currentDynamicText }}</span>
            </div>

            <p class="lead text-muted mb-5 fade-in">
              Kanuru Infosystems is a forward-thinking company delivering analytics-driven solutions, 
              technical training, and multi-domain consulting. We serve private enterprises, institutions, 
              government bodies, and healthcare institutions with a mission to empower decision-making, 
              build capacity, and drive operational excellence.
            </p>

            <div class="d-flex flex-column flex-sm-row gap-3 justify-content-center mb-5 fade-in">
         
              <a  class="btn btn-lg gradient-bg text-white px-4" href="#services">Explore Our Services    <i class="bi bi-arrow-right ms-2"></i></a>

              <!-- <a href="#contact" class="btn gradient-bg text-white ms-2">
                Contact Us
              </a> -->
            </div>

            <!-- Stats Section -->
            <div class="row g-4 mt-5 fade-in">
              <div class="col-6 col-md-3" v-for="stat in stats" :key="stat.label">
                <div class="text-center">
                  <div class="h2 fw-bold text-danger mb-2">{{ stat.number }}</div>
                  <div class="text-muted">{{ stat.label }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-5 bg-white">
      <div class="container">
        <div class="row justify-content-center text-center mb-5">
          <div class="col-lg-8">
            <h2 class="display-5 fw-bold mb-4 mt-3">
              Our Core <span class="gradient-text">Verticals</span>
            </h2>
            <p class="lead text-muted">
              Comprehensive solutions across multiple domains to drive your organization's success
            </p>
          </div>
        </div>

        <div class="row g-4">
          <div 
            class="col-lg-4 col-md-6" 
            v-for="(service, index) in services" 
            :key="index"
          >
            <div class="card h-100 border-0 shadow card-hover slide-up">
              <div v-if="service.image" class="position-relative overflow-hidden">
                <img 
                  :src="service.image" 
                  :alt="service.title"
                  class="card-img-top"
                  style="height: 200px; object-fit: cover;"
                >
              </div>
              
              <div class="card-body">
                <div class="d-flex align-items-center mb-3">
                  <div class="service-icon gradient-bg me-3">
                    <i :class="service.icon"></i>
                  </div>
                  <span class="badge bg-danger bg-opacity-10 text-danger">Core Service</span>
                </div>
                
                <h5 class="card-title fw-bold">{{ service.title }}</h5>
                <p class="card-text text-muted">{{ service.description }}</p>
                
                <ul class="list-unstyled">
                  <li 
                    v-for="feature in service.features" 
                    :key="feature"
                    class="d-flex align-items-center mb-2"
                  >
                    <i class="bi bi-arrow-right text-danger me-2"></i>
                    <small class="text-muted">{{ feature }}</small>
                  </li>
                </ul>
                
                <button class="btn btn-outline-danger w-100 mt-3">
                  Learn More
                  <i class="bi bi-arrow-right ms-2"></i>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section class="py-5" style="background: linear-gradient(135deg, #e3f2fd 0%, #f3e5f5 100%);">
      <div class="container">
        <div class="row justify-content-center text-center mb-5">
          <div class="col-lg-8">
            <h2 class="display-6 fw-bold mb-4 mt-3 fade-in">
              Why Choose <span class="gradient-text">Kanuru Infosystems</span>
            </h2>
          </div>
        </div>

        <div class="row g-4">
          <div 
            class="col-lg-3 col-md-6 text-center fade-in-left" 
            v-for="(feature, index) in features" 
            :key="index"
          >
            <div class="feature-icon gradient-bg">
              <i :class="feature.icon"></i>
            </div>
            <h5 class="fw-bold mb-3">{{ feature.title }}</h5>
            <p class="text-muted">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-5 bg-white">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-lg-6">
            <h2 class="display-5 fw-bold mb-4 fade-in">
              About <span class="gradient-text">Kanuru Infosystems</span>
            </h2>
            <p class="lead text-muted mb-4">
              We are a team of passionate professionals dedicated to transforming organizations 
              through data-driven insights and innovative technology solutions.
            </p>
            <p class="text-muted mb-4">
              Our expertise spans across multiple domains including healthcare, finance, government, 
              and private enterprises. We believe in the power of data to drive meaningful change 
              and create lasting impact.
            </p>
            <div class="row g-3">
              <div class="col-6">
                <div class="d-flex align-items-center">
                  <i class="bi bi-check-circle-fill text-success me-2"></i>
                  <span>Expert Team</span>
                </div>
              </div>
              <div class="col-6">
                <div class="d-flex align-items-center">
                  <i class="bi bi-check-circle-fill text-success me-2"></i>
                  <span>Proven Results</span>
                </div>
              </div>
              <div class="col-6">
                <div class="d-flex align-items-center">
                  <i class="bi bi-check-circle-fill text-success me-2"></i>
                  <span>24/7 Support</span>
                </div>
              </div>
              <div class="col-6">
                <div class="d-flex align-items-center">
                  <i class="bi bi-check-circle-fill text-success me-2"></i>
                  <span>Innovation Focus</span>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-6">
            <img 
              :src="dashboardImg" 
              alt="About Kanuru Infosystems" 
              class="img-fluid rounded shadow"
            >
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
     <section id="contact" class="py-5 bg-dark1 text-white">
  <div class="container">
    <div class="row justify-content-center text-center mb-5 fade-in">
      <div class="col-lg-8">
        <h2 class="display-6 fw-bold mb-4 mt-3">
          Let's Build <span class="gradient-text">Smarter Systems</span> Together
        </h2>
        <p class="lead">
          Whether you're launching a healthcare initiative, training your workforce, 
          or digitizing operations — Kanuru Infosystems is your trusted partner.
        </p>
      </div>
    </div>

    <div class="row align-items-center">
      <!-- Left Column -->
      <div class="col-lg-6 mb-4 fade-in-left">
        <h4 class="fw-bold mb-4">Get in Touch</h4>
        <p class="mb-3">
          <i class="bi bi-envelope text-danger me-2"></i>
          nageshkanuruinfosystems@gmail.com
        </p>
        <p class="mb-3">
          <i class="bi bi-telephone text-danger me-2"></i>
          Contact us : 91+ 7019123548
        </p>
        <p>
          <i class="bi bi-globe text-danger me-2"></i>
          www.kanurutech.com
        </p>
      </div>

      <!-- Right Column -->
      <div class="col-lg-6 fade-in-right">
        <div class="p-4 bg-gray-800 rounded-4">
          <h5 class="fw-bold mb-3">Ready to Start?</h5>
          <p class="mb-4">
            Transform your organization with our comprehensive solutions. 
            Let's discuss how we can help you achieve your goals.
          </p>
          <a class="btn btn-lg gradient-bg text-white px-4" href="https://wa.me/917019123548?text=Welcome%20to%20Kanuru%20Info%20Team.%20Hi%20Kanuru%20Team%2C%20How%20may%20we%20help%20you%3F" 
   target="_blank" 
   rel="noopener noreferrer">
  <i class="bi bi-whatsapp mr-2 p-2"></i>Chat with us on WhatsApp
</a>
        </div>
      </div>
    </div>
  </div>
</section>

    <!-- <section id="contact" class="py-5 bg-dark1 text-white">
      <div class="container">
        <div class="row justify-content-center text-center mb-5">
          <div class="col-lg-8">
            <h2 class="display-6 fw-bold mb-4 mt-3">
              Let's Build <span class="gradient-text">Smarter Systems</span> Together
            </h2>
            <p class="lead">
              Whether you're launching a healthcare initiative, training your workforce, 
              or digitizing operations—Kanuru Infosystems is your trusted partner.
            </p>
          </div>
        </div>

        <div class="row g-4">
          <div class="col-lg-4 col-md-6">
            <div class="text-center">
              <div class="feature-icon gradient-bg mb-3">
                <i class="bi bi-envelope"></i>
              </div>
              <h5>Email Us</h5>
              <p class="text-light">info@kanuruinfosystems.com</p>
            </div>
          </div>
          <div class="col-lg-4 col-md-6">
            <div class="text-center">
              <div class="feature-icon gradient-bg mb-3">
                <i class="bi bi-telephone"></i>
              </div>
              <h5>Call Us</h5>
              <p class="text-light">+91 (XXX) XXX-XXXX</p>
            </div>
          </div>
          <div class="col-lg-4 col-md-6">
            <div class="text-center">
              <div class="feature-icon gradient-bg mb-3">
                <i class="bi bi-geo-alt"></i>
              </div>
              <h5>Visit Us</h5>
              <p class="text-light">Hyderabad, India</p>
            </div>
          </div>
        </div>

        <div class="row justify-content-center">
          <div class="col-lg-8 ">
            <div class="card bg-light text-dark">
              <div class="card-body p-4">
                <h5 class="card-title text-center mb-4 mt-3">Get In Touch</h5>
                <form>
                  <div class="row g-3">
                    <div class="col-md-6">
                      <input type="text" class="form-control" placeholder="Your Name" required>
                    </div>
                    <div class="col-md-6">
                      <input type="email" class="form-control" placeholder="Your Email" required>
                    </div>
                    <div class="col-12">
                      <input type="text" class="form-control" placeholder="Subject" required>
                    </div>
                    <div class="col-12">
                      <textarea class="form-control" rows="4" placeholder="Your Message" required></textarea>
                    </div>
                    <div class="col-12 text-center">
                      <button type="submit" class="btn gradient-bg text-white px-5">
                        Send Message
                        <i class="bi bi-send ms-2"></i>
                      </button>
                    </div>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section> -->

    <!-- Footer -->
    <footer class="bg-black text-white py-4">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-md-12">
            <div class="d-flex align-items-center">
              <img :src="kanuruLogo" alt="Kanuru Infosystems" width="24" height="24" class="me-2">
              <span>&copy; 2024 Kanuru Infosystems pvt ltd. All rights reserved.</span>
            </div>
          </div>
          <!-- <div class="col-md-6 text-md-end">
            <div class="d-flex justify-content-md-end gap-3">
              <a href="#" class="text-white-50 text-decoration-none">Privacy Policy</a>
              <a href="#" class="text-white-50 text-decoration-none">Terms of Service</a>
            </div>
          </div> -->
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'

// Import images
import dashboardImg from './assets/ZLAJh6djUlY9.webp'
import healthcareImg from './assets/VUCdgzaBBO70.jpg'
import trainingImg from './assets/YpNTO1dKkajc.jpg'
import kanuruLogo from './assets/kanuru-logo.png'

export default {
  name: 'App',
  setup() {
    const currentTextIndex = ref(0)
    const isMenuOpen = ref(false)
    
    const dynamicTexts = [
      "Data Analytics",
      "Training Solutions", 
      "Technology Innovation",
      "Public Impact"
    ]
    
    const currentDynamicText = ref(dynamicTexts[0])
    
    const stats = [
      { number: "500+", label: "Projects Completed" },
      { number: "50+", label: "Happy Clients" },
      { number: "10+", label: "Years Experience" },
      { number: "24/7", label: "Support Available" }
    ]
    
    const services = [
      {
        icon: "bi bi-bar-chart",
        title: "Data & Analytics Services",
        description: "From Raw Data to Real Insights",
        features: ["Business Intelligence & Reporting", "Predictive Analytics & ML", "Custom Dashboards", "Healthcare & Finance Analytics"],
        image: dashboardImg
      },
      {
        icon: "bi bi-person-check",
        title: "Training & Capacity Building",
        description: "Upskill for the Data-Driven Era",
        features: ["Data Science Bootcamp", "Machine Learning Mastery", "Analytics for Managers", "Custom Workshops"],
        image: trainingImg
      },
      {
        icon: "bi bi-heart",
        title: "Healthcare & Diagnostics Technology",
        description: "Strengthening Public Health Infrastructure",
        features: ["Health Data Analysis", "Mobile Laboratory Technology", "AI/ML for Disease Surveillance", "Training for Health Officers"],
        image: healthcareImg
      },
      {
        icon: "bi bi-gear",
        title: "Project Operations & Execution",
        description: "From Strategy to Delivery",
        features: ["Field Deployment & Monitoring", "Stakeholder Coordination", "Compliance & Quality Assurance", "Health-Tech Projects"],
        image: null
      },
      {
        icon: "bi bi-people",
        title: "Human Resources & Staffing",
        description: "Talent Solutions for Smart Organizations",
        features: ["Contract Staffing", "Talent Acquisition", "HR Analytics", "Workforce Planning"],
        image: null
      },
      {
        icon: "bi bi-globe",
        title: "Web Design & Digital Services",
        description: "Crafting Digital Experiences That Work",
        features: ["Responsive & SEO-Friendly", "Analytics Integration", "Government & Healthcare Portals", "UI/UX Consulting"],
        image: null
      }
    ]
    
    const features = [
      { icon: "bi bi-database", title: "Data-Driven", description: "Analytics-powered solutions for informed decision making" },
      { icon: "bi bi-graph-up", title: "Scalable", description: "Solutions that grow with your organization's needs" },
      { icon: "bi bi-shield-check", title: "Reliable", description: "Proven track record with government and enterprise clients" },
      { icon: "bi bi-lightning", title: "Innovative", description: "Cutting-edge technology and methodologies" }
    ]
    
    let textInterval = null
    
    const toggleMobileMenu = () => {
      isMenuOpen.value = !isMenuOpen.value
    }
    
    onMounted(() => {
      // Dynamic text rotation
      textInterval = setInterval(() => {
        currentTextIndex.value = (currentTextIndex.value + 1) % dynamicTexts.length
        currentDynamicText.value = dynamicTexts[currentTextIndex.value]
      }, 3000)
      
      // Smooth scrolling for navigation links
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
          e.preventDefault()
          const target = document.querySelector(this.getAttribute('href'))
          if (target) {
            target.scrollIntoView({
              behavior: 'smooth',
              block: 'start'
            })
          }
        })
      })
    })
    
    onUnmounted(() => {
      if (textInterval) {
        clearInterval(textInterval)
      }
    })
    
    return {
      currentDynamicText,
      isMenuOpen,
      stats,
      services,
      features,
      toggleMobileMenu,
      dashboardImg,
      healthcareImg,
      trainingImg,
      kanuruLogo
    }
  }
}
</script>

<style scoped>
/* Component-specific styles can be added here */
</style>

