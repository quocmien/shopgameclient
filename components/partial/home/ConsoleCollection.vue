<template>
	<div class="container">
		<div class="heading heading-flex mb-3">
			<div class="heading-left mb-2">
				<h2 class="title">Consoles & Accessories</h2>
			</div>

			<div class="heading-right mb-2">
				<nuxt-link
					to="/shop/sidebar/list"
					class="title-link"
				>View more products <i class="icon-long-arrow-right"></i></nuxt-link>
			</div>
		</div>
		<div class="swiper-carousel swiper-simple carousel-with-shadow console-carousel">
			<div v-swiper:swiper1="carouselSetting">
				<div class="swiper-wrapper">
					<div
						class="swiper-slide"
						v-for="(product, index) in products"
						:key="index"
					>
						<product-twelve :product="product"></product-twelve>
					</div>
				</div>
			</div>
			<div class="swiper-dots d-block d-sm-none mb-2"></div>
		</div>
	</div>
</template>
<script>
import ProductTwelve from '~/components/elements/products/ProductTwelve';

import { carouselSetting1 } from '~/utilities/carousel';

export default {
	components: {
		ProductTwelve
	},
	props: {
		products: Array
	},
	data: function() {
		return {
			carouselSetting: {
				...carouselSetting1,
				slidesPerView: 5,
				pagination: {
					el: '.console-carousel .swiper-dots',
					clickable: true
				}
			}
		};
	}
};
</script>
