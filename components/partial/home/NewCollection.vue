<template>
	<div class="container">
		<div class="heading heading-flex mb-2 mb-lg-3">
			<div class="heading-left">
				<h2 class="title mb-0">Games Coming Soon</h2>
			</div>

			<div class="heading-right">
				<nuxt-link
					to="/shop/market"
					class="title-link"
				>View more products <i class="icon-long-arrow-right"></i></nuxt-link>
			</div>
		</div>

		<div class="games-soon">
			<div class="row">
				<div class="col-lg-7">
					<div class="products">
						<div class="row">
							<div
								class="col-6 col-md-4"
								v-for="(product,index) in products.slice(0,6)"
								:key="index"
							>
								<product-twelve :product="product"></product-twelve>
							</div>
						</div>
					</div>
				</div>
				<div class="col-lg-5 order-lg-first">
					<div class="swiper-carousel games-banners-slider swiper-simple">
						<div v-swiper:swiper1="carouselSetting1">
							<div class="swiper-wrapper">
								<div class="swiper-slide">
									<div class="banner banner-overlay product-banner">
										<nuxt-link to="/shop/market">
											<img
												v-lazy="'./images/home/banners/banner-9.jpg'"
												alt="Banner"
												width="456"
												height="750"
											>
										</nuxt-link>
										<div class="banner-content align-items-center center">
											<h4 class="banner-subtitle text-white">Out 14 May 2019</h4>
											<img
												class="banner-title-img bg-transparent"
												v-lazy="'./images/home/banners/banner-9-title.png'"
												alt="Banner-9"
												width="348"
												height="266"
											>
											<h4 class="banner-price">$29.99</h4>
											<nuxt-link
												to="/shop/market"
												class="banner-link"
											>Pre-Order Now<i class="icon-long-arrow-right"></i></nuxt-link>
										</div>
									</div>
								</div>
								<div class="swiper-slide">
									<div class="banner banner-overlay product-banner">
										<nuxt-link to="/shop/market">
											<img
												v-lazy="'./images/home/banners/banner-10.jpg'"
												alt="Banner"
												width="456"
												height="750"
											>
										</nuxt-link>
										<div class="banner-content">
											<h4 class="banner-subtitle text-white">Out 14 May 2019</h4>
											<img
												class="banner-title-img bg-transparent"
												v-lazy="'./images/home/banners/banner-10-title.png'"
												alt="Banner-10"
												width="400"
												height="155"
											>
											<h4 class="banner-price">$79.99</h4>
											<nuxt-link
												to="/shop/market"
												class="banner-link"
											>Pre-Order Now<i class="icon-long-arrow-right"></i></nuxt-link>
										</div>
									</div>
								</div>
								<div class="swiper-sldie">
									<div class="banner banner-overlay product-banner">
										<nuxt-link to="/shop/market">
											<img
												v-lazy="'./images/home/banners/banner-11.jpg'"
												alt="Banner"
												width="456"
												height="750"
											>
										</nuxt-link>
										<div class="banner-content align-items-center center">
											<h4 class="banner-subtitle text-white">Out 14 May 2019</h4>
											<img
												class="banner-title-img bg-transparent"
												v-lazy="'./images/home/banners/banner-11-title.png'"
												alt="Banner-11"
												width="418"
												height="142"
											>
											<h4 class="banner-txt">Main Game & Kombat Pack</h4>
											<img
												class="banner-title-img bg-transparent"
												v-lazy="'./images/home/banners/banner-11-subtitle.png'"
												alt="Banner-11"
												width="339"
												height="29"
											>
											<h4 class="banner-price mt-1">$99.99</h4>
											<nuxt-link
												to="/shop/market"
												class="banner-link"
											>Pre-Order Now<i class="icon-long-arrow-right"></i></nuxt-link>
										</div>
									</div>
								</div>
							</div>
						</div>
						<div class="swiper-dots"></div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
import ProductTwelve from '~/components/elements/products/ProductTwelve';
import {
	carouselSettingSingle,
	carouselSettingDefault
} from '~/utilities/carousel';

export default {
	components: {
		ProductTwelve
	},
	props: {
		products: Array
	},
	data: function() {
		return {
			carouselSetting1: {
				...carouselSettingSingle,
				pagination: {
					el: '.games-banners-slider .swiper-dots',
					clickable: true
				}
			}
		};
	}
};
</script>