<template>
	<div class="bg-light pt-3 pb-5 mb-5 special-collection">
		<div class="container">
			<tabs
				class="nav nav-pills nav-big nav-border-anim justify-content-center mb-5"
				:data="tabsData"
				id="tab1"
			></tabs>
			<div class="tab-content tab-content-carousel">
				<div
					class="tab-pane fade show active p-0"
					id="tab1-trending"
				>
					<div class="swiper-carousel swiper-simple carousel-with-shadow swiper-1">
						<div v-swiper:swiper1="carouselSetting1">
							<div class="swiper-wrapper">
								<div
									class="swiper-slide"
									v-for="(product, index) in featuredProducts"
									:key="index"
								>
									<product-twelve :product="product"></product-twelve>
								</div>
							</div>
						</div>
						<div class="swiper-nav">
							<div class="swiper-prev">
								<i class="icon-angle-left"></i>
							</div>
							<div class="swiper-next">
								<i class="icon-angle-right"></i>
							</div>
						</div>
						<div class="swiper-dots"></div>
					</div>
				</div>

				<div
					class="tab-pane fade"
					id="tab1-new"
				>
					<div class="swiper-carousel swiper-simple carousel-with-shadow swiper-2">
						<div v-swiper:swiper2="carouselSetting2">
							<div class="swiper-wrapper">
								<div
									class="swiper-slide"
									v-for="(product, index) in newProducts"
									:key="index"
								>
									<product-twelve :product="product"></product-twelve>
								</div>
							</div>
						</div>
						<div class="swiper-nav">
							<div class="swiper-prev">
								<i class="icon-angle-left"></i>
							</div>
							<div class="swiper-next">
								<i class="icon-angle-right"></i>
							</div>
						</div>
						<div class="swiper-dots"></div>
					</div>
				</div>

				<div
					class="tab-pane fade"
					id="tab1-top"
				>
					<div class="swiper-carousel swiper-simple carousel-with-shadow swiper-3">
						<div v-swiper:swiper3="carouselSetting3">
							<div class="swiper-wrapper">
								<div
									class="swiper-slide"
									v-for="(product, index) in topProducts"
									:key="index"
								>
									<product-twelve :product="product"></product-twelve>
								</div>
							</div>
						</div>
						<div class="swiper-nav">
							<div class="swiper-prev">
								<i class="icon-angle-left"></i>
							</div>
							<div class="swiper-next">
								<i class="icon-angle-right"></i>
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
import Tabs from '~/components/elements/Tabs';
import ProductTwelve from '~/components/elements/products/ProductTwelve';

import { attrFilter } from '~/utilities/common';
import { carouselSetting1 } from '~/utilities/carousel';

export default {
	components: {
		Tabs,
		ProductTwelve
	},
	props: {
		products: Array
	},
	data: function() {
		return {
			tabsData: [
				{
					id: 'trending',
					title: 'Now Trending',
					active: true
				},
				{
					id: 'new',
					title: 'New Releases'
				},
				{
					id: 'top',
					title: 'Best-Rated'
				}
			],
			carouselSetting1: {
				...carouselSetting1,
				slidesPerView: 5,
				navigation: {
					nextEl: '.special-collection .swiper-1 .swiper-next',
					prevEl: '.special-collection .swiper-1 .swiper-prev'
				},
				pagination: {
					el: '.special-collection .swiper-1 .swiper-dots',
					clickable: true
				}
			},
			carouselSetting2: {
				...carouselSetting1,
				slidesPerView: 5,
				navigation: {
					nextEl: '.special-collection .swiper-2 .swiper-next',
					prevEl: '.special-collection .swiper-2 .swiper-prev'
				},
				pagination: {
					el: '.special-collection .swiper-2 .swiper-dots',
					clickable: true
				}
			},
			carouselSetting3: {
				...carouselSetting1,
				slidesPerView: 5,
				navigation: {
					nextEl: '.special-collection .swiper-3 .swiper-next',
					prevEl: '.special-collection .swiper-3 .swiper-prev'
				},
				pagination: {
					el: '.special-collection .swiper-3 .swiper-dots',
					clickable: true
				}
			}
		};
	},
	computed: {
		featuredProducts: function() {
			return attrFilter(this.products, 'featured');
		},
		newProducts: function() {
			return attrFilter(this.products, 'new');
		},
		topProducts: function() {
			return attrFilter(this.products, 'top');
		}
	}
};
</script>
