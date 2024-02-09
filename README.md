Passionate coder and tech enthusiast on a perpetual journey of learning and innovation. With a background in the MERN stack, I thrive on turning complex challenges into elegant solutions. My GitHub repositories reflect my commitment to clean code, collaborative development, and a relentless pursuit of improvement. Let's connect and collaborate to build something great!



import { useState, useEffect } from 'react';

import Navbar from './components/Navbar';
import Hero from './components/Hero';
import Service from './components/Service';
import About from './components/About';
import Accomplishments from './components/Accomplishments';
import Projects from './components/Projects';
import Footer from './components/Footer';

import Cursor from './components/Cursor';
import ScrollToTop from './components/ScrollToTop';
import Preloader from './components/Preloader';

import AOS from 'aos';
import 'aos/dist/aos.css';

const App = () => {
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const handleLoad = () => {
      setLoading(false);
    };

    if (document.readyState === 'complete') {
      // If the document is already complete, trigger handleLoad immediately
      handleLoad();
    } else {
      // If the document is not yet complete, add an event listener for the 'load' event
      window.addEventListener('load', handleLoad);
    }

    return () => {
      window.removeEventListener('load', handleLoad);
    };
  }, []);

  useEffect(() => {
    AOS.init();
  }, []);

  return loading ? <Preloader /> : (
    <>
      <Cursor />
      <Navbar />
      <Hero />
      <Service />
      <About />
      <Accomplishments />
      <Projects />
      <Footer />
      <ScrollToTop />
    </>
  );
};

export default App;


<!---
ThatYoungEngineer/ThatYoungEngineer is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
