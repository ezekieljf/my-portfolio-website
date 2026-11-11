<template>
    <div class="col-12 col-md-6 col-lg-3 mb-3">
        <div class="card h-100 border-secondary rounded-3 overflow-hidden card-change">
            <img
                :src="project.img_src"
                class="card-img-top"
                :alt="project.img_alt"
            >

            <div class="card-body p-3">


                <h6 class="fw-bold">{{project.title}}</h6>

                <p class="text-secondary small">
                    {{project.description}}
                </p>

                <a :href="project.view_product_link" class="text-info text-decoration-none small">
                    View Project &rarr;
                </a>

            </div>
        </div>

    </div>
</template>

<script setup>
    import {defineProps} from 'vue';

    defineProps({
        project: Object
    });
</script>