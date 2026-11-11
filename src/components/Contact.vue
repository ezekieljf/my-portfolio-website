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

                    <form action="#" method="post">

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
                            ></textarea>
                        </div>

                        <button type="submit" class="btn btn-info btn-sm fw-bold px-4">
                            Send Message &rarr;
                        </button>

                    </form>

                </div>
            </div>

        </div>

    </div>
</template>