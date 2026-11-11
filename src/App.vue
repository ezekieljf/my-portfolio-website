<script setup>
    import Navbar from './components/Navbar.vue';
    import About from './components/About.vue';
    import Projects from './components/Projects.vue';
    import Tools from './components/Tools.vue';
    import Contact from './components/Contact.vue';
    import FooterComponent from './components/FooterComponent.vue';
</script>

<template>
    <Navbar />
    <div class="container-fluid px-4 px-lg-5 py-5">
        <About />
    </div>
    <div class="container-fluid px-4 px-lg-5 py-4">
        <Projects />
    </div>
    <div class="container-fluid px-4 px-lg-5 py-5">
        <Tools />
    </div>
    <div class="container-fluid px-4 px-lg-5 py-5">
        <Contact />
    </div>
    <div class="container-fluid border-top border-secondary px-4 px-lg-5 py-4 mt-5 bg-dark">
        <FooterComponent />
    </div>
</template>
