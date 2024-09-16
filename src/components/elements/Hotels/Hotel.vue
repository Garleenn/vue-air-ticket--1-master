<script>
import GalleryVertical from "@/components/partial/product/gallery/GalleryVertical.vue";
import DetailTwo from "@/components/partial/product/details/DetailTwo.vue";
import InfoOne from "@/components/partial/product/info-tabs/InfoOne.vue";
import Breadcrumb from "@/components/partial/product/BreadCrumb.vue";
import RelatedProductsOne from "@/components/partial/product/related/RelatedProductsOne.vue";
import headerProduct from "@/components/partial/headers/HeaderDefault.vue";
import NewFind from "./NewFind.vue";
import FullImages from "./fullImages.vue";

export default {
	components: {
		DetailTwo,
		InfoOne,
		Breadcrumb,
		GalleryVertical,
		RelatedProductsOne,
		headerProduct,
		NewFind,
		FullImages
	},

	data() {
		return {
			product: {
				id: 52,
				name: "Отель Мандарин Москва 4",
				location: "Москва, ул. Русаковская, д. 13 стр. 5",
				short_desc:
					"Отдых должен быть комфортным! Отель «SLIDE Bleisure &amp; MICE Hotel» находится в Екатеринбурге. Этот отель расположен неподалёку от центра города. Рядом с отелем можно прогуляться. Неподалёку: Екатеринбургский зоопарк, Свято-Троицкий Кафедральный собор и Памятник клавиатуре. Отдых должен быть комфортным! Отель «SLIDE Bleisure &amp; MICE Hotel>>> находится в Екатеринбурге. Этот отель расположен неподалёку от центра города. Рядом с отелем можно прогуляться. Неподалёку: Екатеринбургский зоопарк, Свято-Троицкий Кафедральный собор и Памятник клавиатуре.",
				price: 113796,
				review: 17,
				ratings: 8.9,
				pluses: [`Круглосуточная стойка регистрации`, `Интернет, Wi-Fi`, `Wi-Fi доступен на всей территории`, `Утюг, Гладильные принадлежности, Стиральная машина, Сушилка`, `Регистрация иностранных граждан`, `Номера для некурящих`, `Общая кухня`, `Услуга «звонок-будильник»/Будильник`, `Холодильник, Микроволновая печь, Кухня`, `Фен (по запросу)`],
				images: [`src/assets/images/Hotels/hotel1.svg`, `src/assets/images/Hotels/hotel1.svg`, `src/assets/images/icons/pluses.svg`],
				betterHotels: [{
					name: `Улучшенные номера, 24–33 м2`,
					desk: `Кровать в общем номере (мужской номер) (общая ванная комната) (8 кроватей)`,
					price1: 481.67,
					price16: 113796,
					images: [],
					pluses: [`Без питания`, `Нет бесплатной отмены`],
					indexOfPhoto: 0,
				}, {
					name: `Улучшенные номера, 24–33 м2`,
					desk: `Кровать в общем номере (мужской номер) (общая ванная комната) (8 кроватей)`,
					price1: 481.67,
					price16: 113796,
					images: [`src/assets/images/Hotels/hotel1.svg`, `src/assets/images/Hotels/hotel1.svg`, `src/assets/images/icons/pluses.svg`, `src/assets/images/Hotels/hotel1.svg`, `src/assets/images/Hotels/hotel1.svg`, `src/assets/images/Hotels/hotel1.svg`],
					pluses: [`Без питания`, `Нет бесплатной отмены`],
					indexOfPhoto: 0,
				}],
				reviews: [{
					avatar: `src/assets/images/Hotels/hotel1.svg`,
					username: `Marina`,
					nights: 1,
					data: `октябрь 2023 г`,
					raiting: 5.0,
					plus: `Рядом лес`,
					minus: `В номере очень пахло куревом, всю ночь шумели за стенкой, невозможно было спать, пьяные орали что‑то кидали`,
				}]
			},
			descriptionShort: 0,
			index: 0,
			loaded: true,
			isOpenFind: false,
			photo5: null,
			imageList5: ``,
			isFullImage: false,
		};
	},

	methods: {
		slideLeft() {
			if (this.index == 0) {
				this.index = this.product.images.length - 1;
			} else {
				this.index--;
			}
		},

		slideRight() {
			if (this.index == this.product.images.length - 1) {
				this.index = 0;
			} else {
				this.index++;
			}
		},

		spliceImagesBetter() {
			for (let i = 0; i < this.product.betterHotels.length; i++) {
				let item = this.product.betterHotels[i];
				if (item.images.length > 4) {
					this.imageList5 = item.images[4];
					item.images.splice(4, item.images.length - 1);
				}
			}
			if(this.product.betterHotels[4]) {
				photo5 = true;
			}
		},

		openNewFind() {
			this.isOpenFind = !this.isOpenFind;
		},

		getShort() {
			this.descriptionShort = this.product.short_desc.length
		},

		closeFullImage() {
			this.isFullImage = !this.isFullImage;
		}
	},


	mounted() {
		this.spliceImagesBetter();
		this.getShort();
	}
};
</script>

<template>
	<headerProduct />

	<div v-if='isOpenFind || this.isFullImage' class="bg-fone">
	</div>
	<div class="d-flex justify-content-center align-items-center">
		<NewFind v-if='isOpenFind' @openNewFind='openNewFind' />
	</div>
	<div class="d-flex justify-content-center align-items-center">
		<FullImages v-if='this.isFullImage' :images='product.images' :index='index' @closeFullImage='closeFullImage' />
	</div>

	<main class="main">
		<nav aria-label="breadcrumb" class="breadcrumb-nav mb-1"
			style="border-top: 0.1rem solid rgba(235, 235, 235, 0.55);">
			<div class="container">
				<ol class="breadcrumb">
					<li class="breadcrumb-item">
						<router-link to="/">Главная</router-link>
					</li>
					<li class="breadcrumb-item">
						<router-link to="/hotels">Отели</router-link>
					</li>
					<li class="breadcrumb-item">Москва</li>
					<li class="breadcrumb-item active">{{ product.name }}</li>
				</ol>
			</div>
		</nav>

		<div class="page-content">
			<div class="container skeleton-body">
				<div class="product-details-top">
					<div class="img-and-info">
						<div class="header-menu-top">
							<div class="main-info">
								<h2 class="mb-0">{{ product.name }}</h2>
								<div class="location">
									<img src="../../../assets/images/icons/location.svg">
									<u>{{ product.location }}</u>
								</div>
							</div>
							<div class="find-input-center" @click='openNewFind'>
								<img src="../../../assets/images/icons/search.svg">
								<button>Новый поиск</button>
							</div>
							<div class="ratings-block">
								<u>{{ product.review }} отзывов</u>
								<b>{{ product.ratings }}</b>
							</div>
						</div>
						<div class="skel-pro-single" :class="{ loaded: loaded }">
							<div class="image-main-block">
								<img @click='slideLeft' class='arrow arrow-left' src="../../../assets/images/icons/arrowLeft.svg">
								<img :src="product.images[index]" :alt="product.name">
								<img @click='slideRight' class='arrow arrow-right' src="../../../assets/images/icons/arrowLeft.svg">
								<img @click='this.isFullImage = true' class='zoom-img' src="../../../assets/images/icons/zoom.svg" alt="zoom">
								<div class="count-photos">
									<span>{{ index + 1 }} / {{ product.images.length }}</span>
								</div>
							</div>
							<div class="description-block">
								<h5>Описание</h5>
								<p class='mb-2'>{{ product.short_desc.substring(0, this.descriptionShort) }}<span v-if='this.descriptionShort <= 100'>...</span></p>
								<span v-if='this.descriptionShort > 100' class='cursor-pointer' @click='this.descriptionShort = 100'>Свернуть</span>
								<span v-else class='cursor-pointer' @click='this.descriptionShort = this.product.short_desc.length'>Развернуть</span>
							</div>
						</div>
					
					<div class="sort-info-bottom">
						<div class="image-container">
							<div class="coruusel-images-block" v-for='(image, index) in product.images'>
								<img @click='this.index = index' :class="{ 'border-purple': index == this.index }" :src="image"
									:alt="`Фото №${index + 1}`">
							</div>
						</div>
						<div class="price-block">
							<span>От {{ product.price.toString().split(/(\d{3})/).join(' ').trim() }},00 баллов</span>
							<button>Посмотреть цены</button>
						</div>
					</div>
				</div>

					<div class="description-block-sm">
						<h5>Описание</h5>
						<p class='mb-2'>{{ product.short_desc }}</p>
						<span class='cursor-pointer'>Свернуть</span>
					</div>

					<div class="plus-place-block mt-4">
						<div class="plus">
							<h5>Услуги и удобства</h5>
							<div class="d-flex flex-column plus-container">
								<div class='plus-wrapper' v-for='plus in product.pluses'>
									<div class="d-flex pluses align-items-start">
										<img class='mr-3 mt-1' src="../../../assets/images/icons/pluses.svg">
										<span>{{ plus }}</span>
									</div>
								</div>
							</div>
							<span class="d-flex more-pluses mt-1 cursor-pointer">Все услуги и удобства</span>
						</div>

						<div class="place-block pl-3">
							<h5 class='mb-0'>Расположение отеля</h5>
							<span class='d-flex mb-1'>{{ product.location }}</span>
							<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2243.4965708285677!2d37.670629877405986!3d55.78461487309603!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x46b53583707e9a69%3A0x13796e7153ed302b!2z0KDRg9GB0LDQutC-0LLRgdC60LDRjyDRg9C7LiwgMTMg0YHRgtGALiA1LCDQnNC-0YHQutCy0LAsIDEwNzE0MA!5e0!3m2!1sru!2sru!4v1726401827855!5m2!1sru!2sru" height="300" style="border:0; border-radius: 10px" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
						</div>
					</div>

					<div class="betters mt-3">
						<h5>Доступные номера</h5>
						<div class="better-container">
							<div class="better-card" v-for='item in product.betterHotels' :class='{"sh-md": !item.images.length}'>
								<div class='d-flex wrap-card'>
									<div class="image-block d-flex flex-column" v-if='item.images.length'>
										<img class='img-top-better cursor-pointer' :src="item.images[item.indexOfPhoto]" :alt="item.name">
										<div class="small-img d-flex">
											<img class='img-other-better cursor-pointer' v-for='(image, i) in item.images' :src="image" @click='item.indexOfPhoto = i'>
											<div v-if='item.images.length >= 4' class='more-images'> <img class='img-other-better' :src="imageList5"> <b>+ {{ item.images.length }}</b></div>
										</div>
									</div>
									<div class="info-block-better">
										<h4>{{ item.name }}</h4>
										<p>{{ item.desk }}</p>
										<div class="d-flex justify-content-between">
											<div class="d-flex flex-column price-night">
												<h5>Цена за ночь</h5>
												<span>{{ item.price1 }}</span>
											</div>
											<div class="d-flex flex-column plus-night">
												<h5>Условия</h5>
												<span v-for='plus in item.pluses'>{{ plus }}</span>
											</div>
										</div>
									</div>
								</div>
								<div class="price-better-count">
									<b>От {{ item.price16.toString().split(/(\d{3})/).join(' ').trim() }},00 баллов</b>
									<span>За 16 ночей</span>
									<button>Забронировать</button>
								</div>
								<button class='b-button'>Забронировать</button>
							</div>
						</div>
					</div>

					<div class="reviews-container mt-4">
						<h5>Отзывы <b class='ml-4'>{{ product.review }}</b></h5>
						<div class="all-review-block">
							<div class="review-card" v-for='review in product.reviews'>
								<div class="user-info-block d-flex flex-column pr-5">
									<div class="user-block d-flex">
										<img :src="review.avatar" :alt="review.username">
										<h4>{{ review.username }}</h4>
									</div>
									<div class="info-user-info d-flex mt-1">
										<img class='calendar-img' src="../../../assets/images/icons/calendar-simple.svg">
										<span class='ml-1'>{{ review.nights }} ночь</span>
										<span class='ml-3'>{{ review.data }}</span>
									</div>
								</div>
								<div class="d-flex flex-column main-review">
									<b class='mb-1 bg-fiol'>{{ review.raiting }},0</b>
									<p><b class='mr-4'>+ </b> {{ review.plus }}</p>
									<p><b class='mr-4'>- </b> {{ review.minus }}</p>
								</div>
							</div>
						</div>
					</div>

				</div>
			</div>
		</div>
	</main>
</template>

<style scoped>
.more-images {
	position: relative;
	width: 45px;
	height: 45px;
	border-radius: 8px;
	font-weight: 700;
	font-size: 16px;
}

.more-images img {
	background: #00000080;
}

.more-images b {
	position: absolute;
	top: 9px;
	left: 15px;
	color: #fff;
}

.count-photos {
	display: none;
}

.zoom-img {
	position: absolute;
	bottom: 10px;
	right: 15px;
	width: 20px;
	height: 20px;
	object-fit: cover;
	cursor: pointer;
}

@media (max-width: 990px) {
	.more-images {
		display: none
	}

	.count-photos {
		display: block;
		position: absolute;
		bottom: 10px;
		right: calc(50% - 30px);
		cursor: pointer;
		color: #fff;
	}

	.skel-pro-single {
		flex-direction: column !important;
	}

	.find-input-center {
		display: none;
	}

	.image-main-block {
		width: 100% !important;
		height: fit-content !important;
	}

	.image-main-block img:nth-child(2) {
		height: fit-content !important;
		object-fit: contain !important;
		border-radius: 2px !important;
	}

	.description-block {
		max-width: 100% !important;
	}

	.image-container {
		display: none !important;
	}

	.breadcrumb {
		max-width: 100% !important;
	}

	.img-and-info {
		display: flex;
		flex-direction: column;
	}

	.header-menu-top {
		order: 1;
	}

	.description-block {
		display: none;
	}

	.header-menu-top {
		flex-direction: column;
		align-items: start !important;
	}

	.ratings-block {
		display: flex;
		margin-bottom: 10px;
	}

	.ratings-block b {
		order: -1;
	}

	.sort-info-bottom {
		order: 1;
		margin-bottom: 22px;
	}

	.plus-place-block {
		flex-direction: column;
	}

	.plus {
		width: 100% !important;
	}

	.plus-wrapper {
		max-width: 100% !important;
	}

	.plus-container {
		max-height: 100% !important;
		max-width: 100% !important;
	}

	.place-block {
		width: 100% !important;
		padding-left: 0 !important;
	}

	.better-card {
		flex-direction: column;
		padding: 10px !important;
	}

	.price-better-count {
		border-left: none !important;
		border-top: 1px solid #e6e6e6 !important;
		padding-top: 5px;
		width: 100% !important;
		margin-left: 0 !important;
		padding-left: 0 !important;
	}

	.price-better-count button {
		width: 100% !important;
		display: none;
	}

	.wrap-card {
		flex-direction: column;
		align-items: start;
	}

	.image-block {
		position: relative;
	}

	.img-top-better {
		width: 120% !important;
		height: 100% !important;
		object-fit: cover;
	}

	.small-img {
		display: none !important;
	}

	.b-button {
		display: block !important;
		background-color: #55246A;
		color: #fff;
		font-size: 16px;
		border-radius: 7px;
		height: 40px;
		padding: 0 16px;
		margin-top: 10px;
		width: 100%;
		margin: 0 !important;
	}

	.review-card {
		flex-direction: column !important;
	}

	.user-info-block {
		flex-direction: row !important;
		justify-content: space-between !important;
		gap: 15px;
		padding-right: 0 !important;
	}

	.info-user-info span {
		font-size: 12px;
	}
}

@media (max-width: 1200px) and (min-width: 991px) {
	.img-other-better:nth-child(5) {
		display: none !important;
	}
}

.b-button {
	display: none;
}

.description-block-sm {
	max-width: 100%;
	display: flex;
	flex-direction: column;
}


.description-block-sm p {
	font-size: 16px;
	font-weight: 400;
}

.calendar-img {
	width: 20px;
	height: 20px;
}

@media (min-width: 991px) {
	.description-block-sm {
		display: none;
	}
}

.user-block h4, .info-user-info {
	margin-top: 10px !important;
	align-items: center;
}

.bg-fone {
	position: fixed;
	z-index: 2;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background: #000;
	opacity: 0.4;
}

.all-review-block,
.better-container {
	display: flex;
	flex-direction: column;
	gap: 12px;
}

.main-review p b,
.main-review b {
	color: #55246A !important;
}

.bg-fiol {
	background: #F4F7FF;
	width: fit-content;
	padding: 2px 8px;
	border-radius: 4px;
	font-weight: 700;
}

.main-review p {
	color: #000;
}

.user-block {
	display: flex;
	gap: 10px;
}

.user-block img {
	width: 40px;
	height: 40px;
	object-fit: cover;
	border-radius: 100%;
}

.review-card {
	position: relative;
	width: 100%;
	height: fit-content;
	display: flex;
	padding: 24px;
	border: 1px solid #e4e4e4;
	border-radius: 7px;
	gap: 16px;
}

.wrap-card {
	gap: 16px;
	justify-content: space-between;
}

.price-better-count {
	text-align: end;
	display: flex;
	flex-direction: column;
	justify-content: end;
	align-items: end;
	margin-left: 20px;
	border-left: 1px solid #e4e4e4;
	padding-left: 30px;
}

.price-better-count button {
	background-color: #55246A;
	color: #fff;
	font-size: 16px;
	border-radius: 7px;
	height: 40px;
	padding: 0 16px;
	margin-top: 10px;
}

.price-better-count b {
	font-size: 24px;
	color: #000;
}

.plus-night h5,
.price-night h5 {
	font-size: 16px !important;
	color: #333;
	margin-bottom: 6px;
	margin-top: 8px;
}

.plus-night span,
.price-night span {
	font-size: 13px;
}

.info-block-better {
	display: flex;
	flex-direction: column;
	gap: 6px;
}

.info-block-better h4 {
	font-weight: 500;
	color: #333;
	font-size: 20px;
	line-height: 20px;
	margin-bottom: 0;
}

.better-card {
	position: relative;
	width: 100%;
	height: fit-content;
	display: flex;
	padding: 24px;
	border: 1px solid #e4e4e4;
	border-radius: 7px;
	gap: 16px;
	justify-content: space-between;
}

.sh-md {
	box-shadow: 0px 1px 8px 0px #0000001A !important;
}

.small-img {
	gap: 2px;
}

.img-top-better {
	width: 233px;
	height: 182px;
	object-fit: cover;
	margin-bottom: 2px;
	border-radius: 8px;
}

.img-other-better {
	width: 45px;
	height: 45px;
	object-fit: cover;
	border-radius: 8px;
}

.arrow {
	position: absolute;
	top: calc(50% - 25px);
	padding: 0;
	cursor: pointer;
}

.arrow-left {
	left: 10px;
}

.arrow-right {
	right: 10px;
	rotate: 180deg;
}

.image-main-block {
	width: 50%;
	position: relative;
}

.image-main-block img:nth-child(2) {
	object-fit: cover;
	width: 100%;
	height: 350px;
}

.place-block {
	width: 50%;
	display: flex;
	flex-direction: column;
	gap: 10px;
}

.more-pluses {
	font-size: 16px;
	color: #333333;
	font-weight: 500;
}

.plus {
	width: 50%;
}

.plus-wrapper {
	max-width: 50%;
}

.pluses span {
	font-size: 15px;
	color: #333333;
}

.plus-container {
	gap: 10px;
	flex-wrap: wrap;
	max-height: 326px;
}

.plus-place-block {
	display: flex;
	justify-content: space-between;
	gap: 20px;
}

.price-block {
	display: flex;
	flex-direction: column;
	gap: 10px
}

.price-block span {
	font-size: 20px;
	color: #000;
}

.price-block button {
	background-color: #55246A;
	color: #fff;
	font-size: 16px;
	border-radius: 7px;
	height: 40px;
}

.border-purple {
	border: 2px solid #55246A;
}

.image-container {
	display: flex;
	gap: 10px;
	flex-wrap: wrap;
	max-width: 50%;
}

.coruusel-images-block {
	width: 65px;
	height: 65px;
	cursor: pointer;
}

.coruusel-images-block img {
	width: 65px;
	height: 65px;
	object-fit: cover;
	border-radius: 7px;
}

.sort-info-bottom {
	display: flex;
	align-items: center;
	justify-content: space-between;
}

.find-input-center {
	position: relative;
	background-color: #F4F7FF;
	padding: 6px 24px 6px 38px;
	border-radius: 10px;
	margin-right: 52px;
}

.find-input-center button {
	border: none;
	outline: none;
	color: #55246A;
	/* padding-left: 30px; */
	/* padding-right: 170px; */
	font-weight: 500;
	font-size: 16px;
}

.find-input-center img {
	position: absolute;
	top: 14px;
	left: 18px;
}

.ratings-block {
	display: flex;
	align-items: center;
	gap: 8px;
}

@media (min-width: 1224px) {
	.ratings-block {
		justify-content: end;
		width: 227px;
	}
}

.ratings-block b {
	color: #55246A;
	font-size: 14px;
	background-color: #F4F7FF;
	padding: 2px 12px;
	border-radius: 4px
}

.ratings-block span {
	font-size: 12px;
}

.header-menu-top {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.skel-pro-single {
	display: flex;
	flex-direction: row;
	gap: 20px;
}

.skel-pro-single img {
	border-radius: 8px;
}

.main-info {
	display: flex;
	flex-direction: column;
	gap: 5px;
}

.main-info h2 {
	font-size: 24px;
	font-weight: 600;
}

.location {
	font-size: 14px;
	font-weight: 400;
	margin-bottom: 7px;
	display: flex;
	align-items: center;
	gap: 4px;
}

.description-block {
	max-width: 50%;
}


.description-block p {
	font-size: 16px;
	font-weight: 400;
}
</style>