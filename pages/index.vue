<template>
	<div class="main home-page">
		<div class="mb-2"></div>

		<div class="container">
			<div class="row">
				<div class="col-xl-3 d-none d-xl-block">
					<nav class="side-nav">
						<div class="sidenav-title">Browse Categories</div>
						<ul class="menu-vertical sf-arrows">
							<li>
								<a
									href="#"
									class="sf-with-ul"
								>Playstation</a>

								<div class="megamenu megamenu-sm">
									<div class="row no-gutters">
										<div class="col-md-6">
											<div class="menu-col">
												<div class="menu-title">Games Software</div>
												<ul>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=action">Action</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=adventure">Adventure</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=sport">Sports</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=strategy">Strategy</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=role-playing">Role-Playing Game</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=action">Action-Adventure</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=stealth">Stealth</nuxt-link>
													</li>
													<li>
														<nuxt-link to="/shop/sidebar/list?category=shooter">Shooter</nuxt-link>
													</li>
												</ul>
											</div>
										</div>

										<div class="col-md-6">
											<div class="banner banner-overlay">
												<nuxt-link to="/shop/sidebar/list">
													<img
														v-lazy="'./images/home/menu/banner-2.jpg'"
														alt="Banner"
														width="280"
														height="414"
													>
												</nuxt-link>
											</div>
										</div>
									</div>
								</div>
							</li>
							<li class="megamenu-container">
								<a
									href="#"
									class="sf-with-ul"
								>XBOX</a>

								<div class="megamenu">
									<div class="row no-gutters">
										<div class="col-md-8">
											<div class="menu-col">
												<div class="row">
													<div class="col-md-6">
														<div class="menu-title">Games Software</div>
														<ul>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=action">Action</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=adventure">Adventure</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=sport">Sports</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=strategy">Strategy</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=role-playing">Role-Playing Game</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=action">Action-Adventure</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=stealth">Stealth</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=shooter">Shooter</nuxt-link>
															</li>
														</ul>
													</div>

													<div class="col-md-6">
														<div class="menu-title">Game Console & Accessories</div>
														<ul>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=console">Console</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=headsets">Headsets</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=collectibles">Collectibles</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=gaming-chairs">Gaming Chairs</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=controller">Controller</nuxt-link>
															</li>
															<li>
																<nuxt-link to="/shop/sidebar/list?category=digital">Digital</nuxt-link>
															</li>
														</ul>
													</div>
												</div>
											</div>
										</div>

										<div class="col-md-4">
											<div class="banner banner-overlay">
												<nuxt-link
													to="/shop/sidebar/list"
													class="banner banner-menu"
												>
													<img
														v-lazy="'./images/home/menu/banner-1.jpg'"
														alt="Banner"
														width="280"
														height="414"
													>
												</nuxt-link>
											</div>
										</div>
									</div>
								</div>
							</li>
							<li>
								<nuxt-link to="/shop/sidebar/list?category=nindendo">Nindendo</nuxt-link>
							</li>
							<li>
								<nuxt-link to="/shop/sidebar/list?category=pc-gaming">PC Gaming</nuxt-link>
							</li>
							<li>
								<nuxt-link to="/shop/sidebar/list?category=smart-phones">Phones & Tablets</nuxt-link>
							</li>
							<li>
								<nuxt-link to="/shop/sidebar/list?category=pre-owned">Pre-owned</nuxt-link>
							</li>
							<li>
								<nuxt-link to="/shop/sidebar/list?category=deals">Deals</nuxt-link>
							</li>
							<li><a href="#">Coming Soon</a></li>
							<li>
								<nuxt-link to="/shop/sidebar/list?category=accessories">Accessories</nuxt-link>
							</li>
						</ul>
					</nav>
				</div>

				<div class="col-lg-8 col-xl-6">
					<div class="banner banner-overlay banner-lg  content-left" 
						v-for="(banner, index) in banners.slice(0,1)"
						:key="index">
						<nuxt-link to="/shop/sidebar/list">
							
							<img
								class="home-banner1"
								v-lazy="`${baseUrl}${banner.picture[0].url}`"
								alt="Banner"
								width="576"
								height="414"
							>
						</nuxt-link>
						<div class="banner-content">
							<h4 class="banner-subtitle">{{ banner.title }}</h4>
							<h3 class="banner-title">{{ banner.name }}</h3>
							<nuxt-link
								to="/shop/sidebar/list"
								class="banner-link"
							>Pre-Order Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>

				<div class="col-sm-6 col-lg-4 col-xl-3">
					<div class="banner banner-overlay banner-sm content-right"
						v-for="(banner, index) in banners.slice(1,2)"
						:key="index">
						<nuxt-link to="/shop/sidebar/2cols">
							<img
								class="home-banner2"
								v-lazy="`${baseUrl}${banner.picture[0].url}`"
								alt="Banner"
								width="277"
								height="260"
							>
						</nuxt-link>
						<div class="banner-content text-right">
							<h4 class="banner-subtitle">{{ banner.title }}</h4>
							<img
								class="banner-title-img bg-transparent home-icon2"
								v-lazy="`${baseUrl}${banner.icon[0].url}`"
								alt="Banner-2"
								width="158"	
								height="38"
							>
							<h4 class="banner-price">Save<span class="price">{{ banner.price }}</span></h4>
							<nuxt-link
								to="/shop/sidebar/3cols"
								class="banner-link"
							>Buy Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>

					<div class="banner banner-overlay d-none d-lg-block banner-sm content-right align-center"
						v-for="(banner, index) in banners.slice(2,3)"
						:key="index">
						<nuxt-link to="/shop/sidebar/4cols">
							<img
								class="home-banner3"
								v-lazy="`${baseUrl}${banner.picture[0].url}`"
								alt="Banner"
								width="277"
								height="134"
							>
						</nuxt-link>
						<div class="banner-content text-right">
							<img
								class="banner-title-img bg-transparent home-icon3"
								v-lazy="`${baseUrl}${banner.icon[0].url}`"
								alt="Banner-3"
								width="122"
								height="48"
								style="margin-bottom: 1.3rem; margin-top: -.8rem;"
							>
							<nuxt-link
								to="/shop/sidebar/4cols"
								class="banner-link"
							>Buy Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>

				<div class="col-sm-6 col-lg-3">
					<div class="banner banner-overlay banner-sm content-left"
						v-for="(banner, index) in banners.slice(3,4)"
						:key="index">
						<nuxt-link to="/shop/market">
							<img
								class="home-banner4"
								v-lazy="`${baseUrl}${banner.picture[0].url}`"
								alt="Banner"
								width="277"
								height="260"
							>
						</nuxt-link>
						<div class="banner-content">
							<h4 class="banner-subtitle">{{ banner.title }}</h4>
							<img
								class="banner-title-img bg-transparent home-icon4"
								v-lazy="`${baseUrl}${banner.icon[0].url}`"
								alt="Banner-4"
								width="134"
								height="38"
							>
							<h4 class="banner-price"><span class="off">25% off</span></h4>
							<nuxt-link
								to="/shop/market"
								class="banner-link"
							>Buy Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>

				<div class="col-lg-9">
					<div class="banner banner-overlay banner-lg  content-right"
						v-for="(banner, index) in banners.slice(4,5	)"
						:key="index">
						<nuxt-link to="/shop/sidebar/list">
							<img
								class="home-banner5"
								v-lazy="`${baseUrl}${banner.picture[0].url}`"
								alt="Banner"
								width="873"
								height="260"
							>
						</nuxt-link>
						<div class="banner-content text-right">
							<h4 class="banner-subtitle">{{  banner.title  }}</h4>
							<img
								class="banner-title-img bg-transparent home-icon5"
								v-lazy="`${baseUrl}${banner.icon[0].url}`"
								alt="Banner-5"
								width="377"
								height="100"
							>
							<nuxt-link
								to="/shop/sidebar/list"
								class="banner-link"
							>Pre-Order Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>
			</div>
		</div>

		<div class="icon-boxes-container icon-boxes-separator bg-transparent">
			<div class="container">
				<div class="row">
					<div class="col-sm-6 col-lg-3">
						<div class="icon-box icon-box-side">
							<span class="icon-box-icon">
								<i class="icon-rocket"></i>
							</span>
							<div class="icon-box-content">
								<h3 class="icon-box-title">Free Shipping</h3>
								<p>Orders $50 or more</p>
							</div>
						</div>
					</div>

					<div class="col-sm-6 col-lg-3">
						<div class="icon-box icon-box-side">
							<span class="icon-box-icon">
								<i class="icon-rotate-left"></i>
							</span>

							<div class="icon-box-content">
								<h3 class="icon-box-title">Free Returns</h3>
								<p>Within 30 days</p>
							</div>
						</div>
					</div>

					<div class="col-sm-6 col-lg-3">
						<div class="icon-box icon-box-side">
							<span class="icon-box-icon">
								<i class="icon-info-circle"></i>
							</span>

							<div class="icon-box-content">
								<h3 class="icon-box-title">Get 20% Off 1 Item</h3>
								<p>When you sign up</p>
							</div>
						</div>
					</div>

					<div class="col-sm-6 col-lg-3">
						<div class="icon-box icon-box-side">
							<span class="icon-box-icon">
								<i class="icon-life-ring"></i>
							</span>

							<div class="icon-box-content">
								<h3 class="icon-box-title">We Support</h3>
								<p>24/7 amazing services</p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>

		<special-collection
			:products="products"
			v-if="loaded"
		></special-collection>

		<div class="container">
			<div class="row justify-content-center">
				<div class="col-sm-6 col-md-4">
					<div class="banner banner-overlay banner-sm banner-ad content-right align-center">
						<nuxt-link to="/shop/sidebar/2cols">
							<img
								v-lazy="'./images/home/banners/banner-6.jpg'"
								alt="Banner'"
								width="376"
								height="260"
							>
						</nuxt-link>
						<div class="banner-content">
							<h4 class="banner-subtitle">Weekend Offer</h4>
							<img
								class="banner-title-img bg-transparent"
								v-lazy="'./images/home/banners/banner-6-title.png'"
								alt="Banner-6"
								width="175"
								height="51"
							>
							<h4 class="banner-price"><span class="price">Save $19.99</span></h4>
							<nuxt-link
								to="/shop/sidebar/list"
								class="banner-link"
							>Buy Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>

				<div class="col-sm-6 col-md-4">
					<div class="banner banner-overlay banner-sm banner-ad content-left align-center">
						<nuxt-link to="/shop/sidebar/3cols">
							<img
								v-lazy="'./images/home/banners/banner-7.jpg'"
								alt="Banner"
								width="376"
								height="260"
							>
						</nuxt-link>
						<div class="banner-content">
							<h4 class="banner-subtitle">Amazing Deal on an</h4>
							<img
								class="banner-title-img bg-transparent"
								v-lazy="'./images/home/banners/banner-7-title.png'"
								alt="Banner-7"
								width="140"
								height="25"
							>
							<h4 class="banner-txt">Console</h4>
							<h4 class="banner-price color-black mt-3">Save $50</h4>
							<nuxt-link
								to="/shop/sidebar/3cols"
								class="banner-link"
							>Buy Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>

				<div class="col-sm-6 col-md-4">
					<div class="banner banner-overlay banner-sm banner-ad content-left align-center">
						<nuxt-link to="/shop/sidebar/4cols">
							<img
								v-lazy="'./images/home/banners/banner-8.jpg'"
								alt="Banner"
								width="376"
								height="260"
							>
						</nuxt-link>
						<div class="banner-content">
							<h4 class="banner-price text-white mb-1">Save $29.00</h4>
							<img
								class="banner-title-img mb-2 bg-transparent"
								v-lazy="'./images/home/banners/banner-8-title.png'"
								alt="Banner-8"
								width="147"
								height="64"
							>
							<nuxt-link
								to="/shop/sidebar/4cols"
								class="banner-link"
							>Buy Now<i class="icon-long-arrow-right"></i></nuxt-link>
						</div>
					</div>
				</div>
			</div>
		</div>

		<div class="container">
			<hr class="mt-0 mb-4">
		</div>

		<new-collection
			:products="newProducts"
			v-if="loaded"
		></new-collection>

		<div class="mb-3"></div>

		<div class="container">
			<div
				class="cta cta-horizontal cta-horizontal-box bg-image mb-4"
				v-lazy:background-image="'./images/home/bg-2.jpg'"
			>
				<div class="row align-items-center">
					<div class="col-lg-5">
						<h3 class="cta-title text-primary">Join Our Newsletter</h3>
						<p class="cta-desc text-light">Subcribe to get information about products and coupons</p>
					</div>

					<div class="col-lg-7 d-flex justify-content-lg-end">
						<form action="#">
							<div class="input-group">
								<input
									type="email"
									class="form-control form-control-white"
									placeholder="Enter your Email Address"
									aria-label="Email Adress"
									required
								>
								<div class="input-group-append">
									<button
										class="btn btn-primary-white btn-rounded"
										type="submit"
									><span>Subscribe</span><i class="icon-long-arrow-right"></i></button>
								</div>
							</div>
						</form>
					</div>
				</div>
			</div>
		</div>

		<console-collection
			:products="consoleProducts"
			v-if="loaded"
		></console-collection>

		<blog-section
			:blogs="blogs"
			v-if="loaded"
		></blog-section>
	</div>
</template>
<script>
import { mapGetters } from 'vuex';

import SpecialCollection from '~/components/partial/home/SpecialCollection';
import NewCollection from '~/components/partial/home/NewCollection';
import ConsoleCollection from '~/components/partial/home/ConsoleCollection';
import BlogSection from '~/components/partial/home/BlogSection';
import NewsletterModal from '~/components/elements/modals/NewsletterModal';

import Repository, { baseUrl } from '~/repositories/repository.js';
import { attrFilter, catFilter } from '~/utilities/common';

export default {
	components: {
		BlogSection,
		SpecialCollection,
		ConsoleCollection,
		NewCollection
	},
	data: function() {
		return {
			loaded: false,
			products: [],
			newProducts: [],
			consoleProducts: [],
			blogs: [],
			banners: [],
			baseUrl: baseUrl,
		};
	},
	computed: {
		...mapGetters('demo', ['newsletterShow'])
	},
	created: function() {
		this.getProducts();
		this.getBanners();
	},
	mounted: function() {
		if (this.newsletterShow) {
			setTimeout(() => {
				if (this.$route.path == '/' && this.newsletterShow) {
					this.$modal.show(
						NewsletterModal,
						{},
						{ width: '970', height: 'auto', adaptive: true }
					);
				}
			}, 8000);
		}
	},
	methods: {
		getProducts: async function() {
			this.loaded = false;
			await Repository.get(`${baseUrl}/demo19`)
				.then(response => {
					this.products = response.data.products;
					this.topProducts = attrFilter(this.products, 'top');
					this.newProducts = attrFilter(this.products, 'new');
					this.consoleProducts = catFilter(this.products, [
						'console',
						'accessories'
					]);
					this.blogs = response.data.blogs;
					this.loaded = true;
				})
				.catch(error => ({ error: JSON.stringify(error) }));
		},
		getBanners: async function() {
			this.loaded = false;
			await Repository.get(`${baseUrl}/banners`)
				.then(response => {
					this.banners = response.data;
				})
				.catch(error => ({ error: JSON.stringify(error) }));
		}
	}
};
</script>

<style scoped>
.home-banner1 {
    width: 576px;
    height: 414px; 
}

.home-banner2 {
	width: 277px;
    height: 260px; 
}

.home-banner3{
	width: 277px;
    height: 134px; 
}

.home-banner4 {
	width: 277px;
    height: 260px; 
}
.home-banner5 {
	width: 873px;
    height: 260px; 
}



.home-icon2 {
	width: 158px;
    height: 38px; 
}

.home-icon3{
	width: 122px;
    height: 48px; 
}
.home-icon4{
	width: 134px;
    height: 38px; 
}
.home-icon5 {
	width: 377px;
    height: 100px; 
}

</style>


