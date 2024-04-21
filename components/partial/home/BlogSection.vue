<template>
	<div class="blog-posts bg-light pt-4 pb-5">
		<div class="container">
			<div class="heading heading-flex mb-4">
				<div class="heading-left">
					<h2 class="title mb-0">From Our Blog</h2>
				</div>

				<div class="heading-right">
					<nuxt-link
						to="/blog/classic"
						class="title-link"
					>View more articles <i class="icon-long-arrow-right"></i></nuxt-link>
				</div>
			</div>
			<div class="swiper-carousel carousel-with-shadow swiper-simple swiper-simple blog-carousel">
				<div
					class="mb-0"
					v-swiper:swiper1="carouselSetting"
				>
					<div class="swiper-wrapper">
						<div
							class="swiper-slide"
							v-for="(blog, index) in blogs"
							:key="index"
						>
							<blog-four
								:blog="blog"
								class="mb-0"
							></blog-four>
						</div>
					</div>
				</div>
				<div class="swiper-dots d-sm-none d-block"></div>
			</div>
		</div>
	</div>
</template>
<script>
import BlogFour from '~/components/elements/blogs/BlogFour';
import { carouselSettingDefault } from '~/utilities/carousel';

export default {
	components: {
		BlogFour
	},
	props: {
		blogs: Array
	},
	data: function() {
		return {
			carouselSetting: {
				...carouselSettingDefault,
				slidesPerView: 4,
				breakpoints: {
					480: {
						slidesPerView: 1
					},
					768: {
						slidesPerView: 2
					},
					992: {
						slidesPerView: 3
					}
				},
				pagination: {
					el: '.blog-carousel .swiper-dots',
					clickable: true
				}
			}
		};
	}
};
</script>