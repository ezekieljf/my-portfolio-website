<script setup>
    import {ref, onMounted, onBeforeUnmount} from 'vue';
    import axios from 'axios';

    import {Notyf} from 'notyf';
    import 'notyf/notyf.min.css';

    const notyf = new Notyf();


    const WEB3FORMS_ACCESS_KEY = '51243e38-16b4-470e-916c-2f43c88752f4';
    const SITE_KEY = "6LcophouAAAAAKkiL8gYzIEGg2QmlbCDnAy2BYK8";

    const subject = "New message from Portfolio Contact Form";

    const name = ref("");
    const email = ref("");
    const message = ref("");

    const isLoading = ref(false);


    const submitForm =  async() => {
        if (!recaptchaToken.value) {
            notyf.error('Please verify that you are not a robot.');
            return;
        }

        isLoading.value = true;

        try {
            const response = await axios.post("https://api.web3forms.com/submit", {
                access_key: WEB3FORMS_ACCESS_KEY,
                subject: subject,
                name: name.value,
                email: email.value,
                message: message.value
            }, {
                headers: {
                    'Content-type': "application/json",
                    Accept: "application/json"
                }
            })
            console.log(response)
            const result = response.data

            if(result.success) {
                notyf.success("Message Sent!");

                name.value = "";
                email.value = "";
                message.value = "";
            }
        } catch(e) {
            console.log(e)
            notyf.error("Failed to send email!");
        } finally {
            isLoading.value = false;
        }
    }

    const recaptchaContainer = ref(null);
    const recaptchaWidgetId = ref(null);
    const recaptchaToken = ref('');

    function onRecaptchaSuccess(token) {
      recaptchaToken.value = token;
    }

    function onRecaptchaExpired() {
      recaptchaToken.value = '';
    }

    function renderRecaptcha() {
      if (!window.grecaptcha) {
        console.error('reCAPTCHA not loaded');
        return;
      }

      recaptchaWidgetId.value = window.grecaptcha.render(recaptchaContainer.value, {
        sitekey: SITE_KEY,
        size: 'normal',
        callback: onRecaptchaSuccess,
        'expired-callback': onRecaptchaExpired,
      });
    }

    function resetRecaptcha() {
      if (recaptchaWidgetId.value !== null) {
        window.grecaptcha.reset(recaptchaWidgetId.value);
        recaptchaToken.value = '';
      }
    }



    onMounted(() => {
      const interval = setInterval(() => {
        if (window.grecaptcha && window.grecaptcha.render) {
          renderRecaptcha();
          clearInterval(interval);
        }
      }, 100);

      onBeforeUnmount(() => {
        clearInterval(interval);
      });
    });
</script>

<template>
    <div class="text-center mb-4">
        <span class="badge bg-dark text-info border border-secondary p-2">
            CONTACT
        </span>
    </div>

    <div class="row justify-content-center">

        <div class="d-none col-lg-5 d-lg-block mb-3">

            <div class="h-100 border-secondary rounded-3 overflow-hidden">

                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d61775.93987722886!2d120.93828363804528!3d14.599289836861347!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3397ca03571ec38b%3A0x69d1d5751069c11f!2sManila%2C%20Metro%20Manila!5e0!3m2!1sen!2sph!4v1790671459950!5m2!1sen!2sph" width="600" height="450" id="map" allowfullscreen="" loading="lazy" referrerpolicy="strict-origin-when-cross-origin"></iframe>

            </div>

        </div>


        <div class="col-12 col-lg-5 mb-3">

            <div class="card h-100 border-secondary rounded-3 card-change">

                <div class="card-body p-4">

                    <form @submit.prevent="submitForm">

                        <div class="mb-3">
                            <label for="name" class="form-label text-info small fw-bold">
                                ◆ FULL NAME
                            </label>

                            <input
                                type="text"
                                class="form-control bg-dark text-light border-secondary"
                                id="name"
                                name="name"
                                placeholder="Jane Doe"
                                required
                                v-model="name"
                            >
                        </div>

                        <div class="mb-3">
                            <label for="email" class="form-label text-info small fw-bold">
                                ◆ YOUR EMAIL
                            </label>

                            <input
                                type="email"
                                class="form-control bg-dark text-light border-secondary"
                                id="email"
                                name="email"
                                placeholder="jane@example.com"
                                required
                                v-model="email"
                            >
                        </div>

                        <div class="mb-4">
                            <label for="message" class="form-label text-info small fw-bold">
                                ◆ MESSAGE
                            </label>

                            <textarea
                                class="form-control bg-dark text-light border-secondary"
                                id="message"
                                name="message"
                                rows="5"
                                placeholder="message"
                                required
                                v-model="message"
                            ></textarea>
                        </div>

                        <button type="submit" class="btn btn-info btn-sm fw-bold px-4" :disabled="isLoading">
                            {{isLoading ? "Sending . . ." : "Submit &rarr;"}}
                        </button>
                        
                        <!-- recaptcha checkbox -->
                        <div class="d-flex justify-content-end mt-2">
                            <div ref="recaptchaContainer"></div>
                        </div>

                    </form>

                </div>
            </div>

        </div>

    </div>
</template>