<template>
    <main class="main">
        <div v-if="loaded" class="loading-overlay">
            <div class="loading-spinner"></div>
        </div>
        <page-header title="Checkout" subtitle="Shop"></page-header>
        <nav class="breadcrumb-nav">
            <div class="container">
                <ol class="breadcrumb">
                    <li class="breadcrumb-item">
                        <nuxt-link to="/">Home</nuxt-link>
                    </li>
                    <li class="breadcrumb-item">
                        <nuxt-link to="/shop/sidebar/list">Shop</nuxt-link>
                    </li>
                    <li class="breadcrumb-item active">Checkout</li>
                </ol>
            </div>
        </nav>

        <div class="page-content">
            <div class="checkout">
                <div class="container">
                    <div class="checkout-discount">
                        <form action="#">
                            <input
                                type="text"
                                class="form-control"
                                required
                                id="checkout-discount-input"
                                @click="clickCoupon($event)"
                            />
                            <label for="checkout-discount-input" class="text-truncate">
                                Have a coupon?
                                <span>Click here to enter your code</span>
                            </label>
                        </form>
                    </div>

                    <form @submit.prevent="submitForm" action="#">

                        <div class="row" >
                            <div class="col-lg-9">
                                <h2 class="checkout-title">Billing Details</h2>

                                <div class="row">
                                    <div class="col-sm-6">
                                        <label>First Name *</label>
                                        <input type="text" class="form-control" v-model="firstName" required />
                                    </div>

                                    <div class="col-sm-6">
                                        <label>Last Name *</label>
                                        <input type="text" class="form-control"  v-model="lastName" required />
                                    </div>
                                </div>

                                <!-- <label>Company Name (Optional)</label>
                                <input type="text" class="form-control" /> -->

                                <label>Country *</label>
                                <input type="text" class="form-control"  v-model="country" required />

                                <label>Address *</label>
                                <input
                                    type="text"
                                    class="form-control"
                                    placeholder="House number and Street name"
                                    v-model="address"
                                    required
                                />
                                <!-- <input
                                    type="text"
                                    class="form-control"
                                    placeholder="Appartments, suite, unit etc ..."
                                    required
                                /> -->

                                <div class="row">
                                    <!-- <div class="col-sm-6">
                                        <label>Town / City *</label>
                                        <input type="text" class="form-control" required />
                                    </div>

                                    <div class="col-sm-6">
                                        <label>State / County *</label>
                                        <input type="text" class="form-control" required />
                                    </div>
                                </div>

                                <div class="row">
                                    <div class="col-sm-6">
                                        <label>Postcode / ZIP *</label>
                                        <input type="text" class="form-control" required />
                                    </div> -->

                                    <div class="col-12">
                                        <label>Phone *</label>
                                        <input type="tel" class="form-control"  v-model="phone" required />
                                    </div>
                                </div>

                                <label>Email *</label>
                                <input type="email" class="form-control"  v-model="email" required />

                                <!-- <div class="custom-control custom-checkbox">
                                    <input
                                        type="checkbox"
                                        class="custom-control-input"
                                        id="checkout-create-acc"
                                    />
                                    <label
                                        class="custom-control-label"
                                        for="checkout-create-acc"
                                    >Create an account?</label>
                                </div>

                                <div class="custom-control custom-checkbox">
                                    <input
                                        type="checkbox"
                                        class="custom-control-input"
                                        id="checkout-diff-address"
                                    />
                                    <label
                                        class="custom-control-label"
                                        for="checkout-diff-address"
                                    >Ship to a different address?</label>
                                </div> -->

                                <label>Order notes (optional)</label>
                                <textarea
                                    class="form-control"
                                    cols="30"
                                    rows="4"
                                    v-model="notes"
                                    placeholder="Notes about your order, e.g. special notes for delivery"
                                ></textarea>
                            </div>

                            <aside class="col-lg-3">
                                <div class="summary">
                                    <h3 class="summary-title">Your Order</h3>

                                    <table class="table table-summary">
                                        <thead>
                                            <tr>
                                                <th>Product</th>
                                                <th>Total</th>
                                            </tr>
                                        </thead>

                                        <tbody>
                                            <tr v-for="(product, index) in cartList" :key="index">
                                                <td>
                                                    <nuxt-link
                                                        :to="'/product/default/' + product.slug"
                                                    >{{ product.name }}</nuxt-link>
                                                </td>
                                                <td>${{ product.sum }}</td>
                                            </tr>

                                            <tr class="summary-subtotal">
                                                <td>Subtotal:</td>
                                                <td>${{ priceTotal }}</td>
                                            </tr>

                                            <tr>
                                                <td>Shipping:</td>
                                                <td>Free shipping</td>
                                            </tr>
                                            <tr class="summary-total">
                                                <td>Total:</td>
                                                <td>${{ priceTotal }}</td>
                                            </tr>
                                        </tbody>
                                    </table>

                                    <div class="accordion-summary">
                                        <div class="card">
                                            <div class="card-header">
                                                <h2 class="card-title">
                                                    <a
                                                        class="toggle-button"
                                                        :class="{expanded: toggleState[0], collapsed: !toggleState[0]}"
                                                        @click.prevent="changeToggle(0)"
                                                        href="#"
                                                    >Direct bank transfer</a>
                                                </h2>
                                            </div>

                                            <vue-slide-toggle :open="toggleState[0]">
                                                <div
                                                    class="card-body"
                                                >Make your payment directly into our bank account. Please use your Order ID as the payment reference. Your order will not be shipped until the funds have cleared in our account.</div>
                                            </vue-slide-toggle>
                                        </div>

                                        <div class="card">
                                            <div class="card-header">
                                                <h2 class="card-title">
                                                    <a
                                                        class="toggle-button"
                                                        :class="{expanded: toggleState[1], collapsed: !toggleState[1]}"
                                                        @click.prevent="changeToggle(1)"
                                                        href="#"
                                                    >Check payments</a>
                                                </h2>
                                            </div>

                                            <vue-slide-toggle :open="toggleState[1]">
                                                <div
                                                    class="card-body"
                                                >Ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros. Nullam malesuada erat ut turpis.</div>
                                            </vue-slide-toggle>
                                        </div>

                                        <div class="card">
                                            <div class="card-header">
                                                <h2 class="card-title">
                                                    <a
                                                        class="toggle-button"
                                                        :class="{expanded: toggleState[2], collapsed: !toggleState[2]}"
                                                        @click.prevent="changeToggle(2)"
                                                        href="#"
                                                    >Cash on delivery</a>
                                                </h2>
                                            </div>

                                            <vue-slide-toggle :open="toggleState[2]">
                                                <div
                                                    class="card-body"
                                                >Quisque volutpat mattis eros. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros.</div>
                                            </vue-slide-toggle>
                                        </div>

                                        <div class="card">
                                            <div class="card-header">
                                                <h2 class="card-title">
                                                    <a
                                                        class="toggle-button"
                                                        :class="{expanded: toggleState[3], collapsed: !toggleState[3]}"
                                                        @click.prevent="changeToggle(3)"
                                                        href="#"
                                                    >
                                                        PayPal
                                                        <small
                                                            class="float-right paypal-link"
                                                        >What is PayPal?</small>
                                                    </a>
                                                </h2>
                                            </div>

                                            <vue-slide-toggle :open="toggleState[3]">
                                                <div
                                                    class="card-body"
                                                >Nullam malesuada erat ut turpis. Suspendisse urna nibh, viverra non, semper suscipit, posuere a, pede. Donec nec justo eget felis facilisis fermentum.</div>
                                            </vue-slide-toggle>
                                        </div>

                                        <div class="card">
                                            <div class="card-header">
                                                <h2 class="card-title">
                                                    <a
                                                        class="toggle-button"
                                                        :class="{expanded: toggleState[4], collapsed: !toggleState[4]}"
                                                        @click.prevent="changeToggle(4)"
                                                        href="#"
                                                    >
                                                        Credit Card (Stripe)
                                                        <img
                                                            v-lazy="'./images/payments-summary.png'"
                                                            alt="payments cards"
                                                            class="bg-white"
                                                        />
                                                    </a>
                                                </h2>
                                            </div>

                                            <vue-slide-toggle :open="toggleState[4]">
                                                <div
                                                    class="card-body"
                                                >Donec nec justo eget felis facilisis fermentum.Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros. Lorem ipsum dolor sit ame.</div>
                                            </vue-slide-toggle>
                                        </div>
                                    </div>

                                    <button
                                        @click.prevent="submitForm"
                                        class="btn btn-outline-primary-2 btn-order btn-block"
                                    >
                                        <span class="btn-text">Place Order</span>
                                        <span class="btn-hover-text">Proceed to Checkout</span>
                                    </button>
                                </div>
                            </aside>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </main>
</template>
<script>
import { mapGetters } from 'vuex';
import { VueSlideToggle } from 'vue-slide-toggle';
import PageHeader from '~/components/elements/PageHeader';
import Repository, { baseUrl } from '~/repositories/repository.js';


export default {
    components: {
        VueSlideToggle,
        PageHeader
    },
    data: function() {
        return {
            toggleState: [true, false, false, false, false],
            loaded: false,
            lastName: '',
            country: '',
            address: '',
            phone: '',
            email: '',
            notes: '',  
        };
    },
    computed: {
        ...mapGetters('cart', ['cartList', 'priceTotal', 'qtyTotal'])
    },
    methods: {
        updateCart: function() {
            this.updateCart(this.cartItems);
        },
        clickCoupon(event) {
            event.currentTarget.parentElement.querySelector('label').style =
                'opacity: 0';
        },
        changeToggle: function(index1) {
            this.toggleState = this.toggleState.reduce((acc, cur, index) => {
                if (index == index1) return [...acc, !cur];
                return [...acc, false];
            }, []);
        },

        async submitForm() {
            const orderItems = this.cartList.map(product => {
                return {
                    name: product.name,
                    sum: product.sum,
                };
            });


            const orderData = {
                
                // Tạo một đối tượng chứa thông tin đơn hàng từ các biến trong data
                firstName: this.firstName,
                lastName: this.lastName,
                country: this.country,
                address: this.address,
                phone: this.phone,
                email: this.email,
                notes: this.notes,
                orderItems: orderItems,
                priceTotal: this.priceTotal
            };

            try {
                this.loaded = true;
                const response = await Repository.post(`${baseUrl}/orders`, orderData);
  
                this.loaded = false;
                return response.data;
            } catch (error) {

                console.error('Error posting products:', error);
                throw error;
            }
        }


    }
};
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