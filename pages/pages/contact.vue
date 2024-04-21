<template>
    <main class="main">
        <div v-if="loaded" class="loading-overlay">
            <div class="loading-spinner"></div>
        </div>
        <nav class="breadcrumb-nav border-0 mb-0">
            <div class="container">
                <ol class="breadcrumb">
                    <li class="breadcrumb-item">
                        <nuxt-link to="/">Home</nuxt-link>
                    </li>
                    <li class="breadcrumb-item">
                        <nuxt-link to="/pages">Pages</nuxt-link>
                    </li>
                    <li class="breadcrumb-item active">Contact us</li>
                </ol>
            </div>
        </nav>

        <div class="container">
            <div
                class="page-header page-header-big text-center"
                v-lazy:background-image="'./images/contact-header-bg.jpg'"
            >
                <h1 class="page-title text-white">
                    Contact us
                    <span class="text-white">keep in touch with us</span>
                </h1>
            </div>
        </div>

        <div class="page-content pb-0">
            <div class="container">
                <div class="row">
                    <div class="col-lg-6 mb-2 mb-lg-0">
                        <h2 class="title mb-1">Contact Information</h2>

                        <p
                            class="mb-3"
                        >Vestibulum volutpat, lacus a ultrices sagittis, mi neque euismod dui, eu pulvinar nunc sapien ornare nisl. Phasellus pede arcu, dapibus eu, fermentum et, dapibus sed, urna.</p>
                        <div class="row">
                            <div class="col-sm-7">
                                <div class="contact-info">
                                    <h3>The Office</h3>

                                    <ul class="contact-list">
                                        <li>
                                            <i class="icon-map-marker"></i>
                                            177 Tran Chien Streets, Le Binh Ward, Can Tho City, Viet Nam
                                        </li>
                                        <li>
                                            <i class="icon-phone"></i>
                                            <a href="tel:#">+84 423 567</a>
                                        </li>
                                        <li>
                                            <i class="icon-envelope"></i>
                                            <a href="mailto:#">info@QMien.com</a>
                                        </li>
                                    </ul>
                                </div>
                            </div>

                            <div class="col-sm-5">
                                <div class="contact-info">
                                    <h3>The Office</h3>

                                    <ul class="contact-list">
                                        <li>
                                            <i class="icon-clock-o"></i>
                                            <span class="text-dark">Monday-Saturday</span>
                                            <br />11am-7pm ET
                                        </li>
                                        <li>
                                            <i class="icon-calendar"></i>
                                            <span class="text-dark">Sunday</span>
                                            <br />11am-6pm ET
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-lg-6">
                        <h2 class="title mb-1">Got Any Questions?</h2>

                        <p class="mb-2">Use the form below to get in touch with the sales team</p>

                        <form submit.prevent="submitForm" action="#" class="contact-form mb-3">
                            <div class="row">
                                <div class="col-sm-6">
                                    <label for="cname" class="sr-only">Name</label>
                                    <input
                                        v-model="name"
                                        type="text"
                                        class="form-control"
                                        id="cname"
                                        placeholder="Name *"
                                        required
                                    />
                                </div>

                                <div class="col-sm-6">
                                    <label for="cemail" class="sr-only">Email</label>
                                    <input
                                        v-model="email"
                                        type="email"
                                        class="form-control"
                                        id="cemail"
                                        placeholder="Email *"
                                        required
                                    />
                                </div>
                            </div>

                            <div class="row">
                                <div class="col-sm-6">
                                    <label for="cphone" class="sr-only">Phone</label>
                                    <input
                                        v-model="phone"
                                        type="tel"
                                        class="form-control"
                                        id="cphone"
                                        placeholder="Phone"
                                    />
                                </div>

                                <div class="col-sm-6">
                                    <label for="csubject" class="sr-only">Subject</label>
                                    <input
                                        v-model="subject"
                                        type="text"
                                        class="form-control"
                                        id="csubject"
                                        placeholder="Subject"
                                    />
                                </div>
                            </div>

                            <label for="cmessage" class="sr-only">Message</label>
                            <textarea
                                v-model="message"
                                class="form-control"
                                cols="30"
                                rows="4"
                                id="cmessage"
                                required
                                placeholder="Message *"
                            ></textarea>

                            <button @click.prevent="submitForm" type="submit" class="btn btn-outline-primary-2 btn-minwidth-sm">
                                <span>SUBMIT</span>
                                <i class="icon-long-arrow-right"></i>
                            </button>
                        </form>
                    </div>
                </div>

                <hr class="mt-4 mb-5" />

                <div class="stores mb-4 mb-lg-5">
                    <h2 class="title text-center mb-3">Our Stores</h2>

                    <div class="row">
                        <div class="col-lg-6">
                            <div class="store">
                                <div class="row">
                                    <div class="col-sm-5 col-xl-6">
                                        <figure class="store-media mb-2 mb-lg-0">
                                            <img v-lazy="'./images/stores/img-1.jpg'" class="w-100" alt="image" />
                                        </figure>
                                    </div>

                                    <div class="col-sm-7 col-xl-6">
                                        <div class="store-content">
                                            <h3 class="store-title">QMien Game Store</h3>
                                            <address>177, Tran Chien Streets, Le Binh Ward, Can Tho City, Viet Nam</address>
                                            <div>
                                                <a href="tel:#">+84 987-876-6543</a>
                                            </div>

                                            <h4 class="store-subtitle">Store Hours:</h4>

                                            <div>Monday - Saturday 11am to 7pm</div>
                                            <div>Sunday 11am to 6pm</div>

                                            <a
                                                href="javascript:;"
                                                class="btn btn-link"
                                                target="_blank"
                                            >
                                                <span>View Map</span>
                                                <i class="icon-long-arrow-right"></i>
                                            </a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-6">
                            <div class="store">
                                <div class="row">
                                    <div class="col-sm-5 col-xl-6">
                                        <figure class="store-media mb-2 mb-lg-0">
                                            <img v-lazy="'./images/stores/img-2.jpg'" class="w-100" alt="image" />
                                        </figure>
                                    </div>

                                    <div class="col-sm-7 col-xl-6">
                                        <div class="store-content">
                                            <h3 class="store-title">QMien Game Store</h3>

                                            <address>177, Tran Chien Streets, Le Binh Ward, Can Tho City, Viet Nam</address>
                                            <div>
                                                <a href="tel:#">+84 987-876-6543</a>
                                            </div>

                                            <h4 class="store-subtitle">Store Hours:</h4>

                                            <div>Monday - Friday 9am to 8pm</div>
                                            <div>Saturday - 9am to 2pm</div>
                                            <div>Sunday - Closed</div>

                                            <a
                                                href="javascript:;"
                                                class="btn btn-link"
                                                target="_blank"
                                            >
                                                <span>View Map</span>
                                                <i class="icon-long-arrow-right"></i>
                                            </a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="map">
                <gmap-map
                    :center="{lat:10, lng:10}"
                    :zoom="7"
                    map-type-id="terrain"
                    style="width: 500px; height: 300px"
                ></gmap-map>
            </div>
            <!-- End #map -->
        </div>
    </main>
</template>

<script>
import Vue from 'vue'
import * as VueGoogleMaps from 'vue2-google-maps'
import Repository, { baseUrl } from '~/repositories/repository.js';
Vue.use(VueGoogleMaps, {
  load: {
    key: 'AIzaSyBzlLYISGjL_ovJwAehh6ydhB56fCCpPQw',
    libraries: 'places', // This is required if you use the Autocomplete plugin
    // OR: libraries: 'places,drawing'
    // OR: libraries: 'places,drawing,visualization'
    // (as you require)
  }
})
export default {
    data: function() {
        return {
            loaded : false,
            name: '',
            email: '',
            phone: '',
            subject: '',
            message: '',
            
        };
    },
    computed: {},
    methods: {

        async submitForm() {

            const contactData = {
                name: this.name,
                email: this.email,
                phone: this.phone,
                subject: this.subject,
                message: this.message,

            };

            try {
                this.loaded = true
                const response = await Repository.post(`${baseUrl}/contacts`, contactData);
                this.loaded = false
                return response.data;
            } catch (error) {
                console.error('Error posting products:', error);
                throw error;
            }
        }
    }
}
</script>

</script>

<style>
.loading-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 255, 0.8); /* Màu nền với độ trong suốt */
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999; /* Đảm bảo hiển thị trên các phần tử khác */
}

.loading-spinner {
    border: 4px solid #f3f3f3; /* Màu nền của spinner */
    border-top: 4px solid #202022; /* Màu của spinner */
    border-radius: 50%;
    width: 50px;
    height: 50px;
    animation: spin 1s linear infinite; /* Animation */
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}   
</style>