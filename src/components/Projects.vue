<template>
    <section id="projects">
        <div class="text-center mb-4">
            <span class="badge bg-dark text-info border border-secondary p-2">
                PROJECTS
            </span>
        </div>
        <div class="row justify-content-center">
            <ProjectCard 
            v-for="project in projects" 
            :key="project.id" 
            :project="project"
            />
        </div>
    </section>
</template>

<script setup>
    import ProjectCard from './ProjectCard.vue';
    import projects from '../data/projects.json';
</script>