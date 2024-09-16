<script>
import HeaderProduct from '@/components/partial/headers/headerProduct.vue';
import { DatePicker } from 'v-calendar';
export default {
	components: { HeaderProduct, DatePicker },
	data() {
		return {
			form: {
				place: ``,
				persons: 1,
				enter: null,
				outer: null,
			},

			isOpenFiltersSm: false,

			isCalendar1: false,

			showFakeMap: true,

			isLargeWindow: true,

			sort: false,

			hotels: [
				{
					title: `Grand Way Один`,
					raiting: 5,
					images: [`src/assets/images/icons/hotelImage.png`, `src/assets/images/icons/pluses.svg`],
					price: 113796,
					grade: 8.9,
					type: `Отель`,
					plusPlace: `Сочи, 0.5 км до центра города`,
					short_desk: `Отдых должен быть комфортным! Отель «SLIDE Bleisure &amp; MICE Hotel» находится в Екатеринбурге. Этот отель расположен неподалёку от центра города. Рядом с отелем можно прогуляться. Неподалёку: Екатеринбургский зоопарк, Свято‑Троицкий Кафедральный собор и Памятник клавиатуре.`,
					isFullDesk: false,
					subsDesk: 180,
					showAllPluses: false,
					pluses: [`WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`, `WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`],
					review: 17,
					indexOfPhoto: 0,
				},
				{
					title: `Grand Way Один`,
					raiting: 5,
					images: [`src/assets/images/icons/hotelImage.png`, `src/assets/images/icons/hotelImage.png`],
					price: 113796,
					grade: 8.9,
					type: `Отель`,
					plusPlace: `Сочи, 0.5 км до центра города`,
					short_desk: `Отдых должен быть комфортным! Отель «SLIDE Bleisure &amp; MICE Hotel» находится в Екатеринбурге. Этот отель расположен неподалёку от центра города. Рядом с отелем можно прогуляться. Неподалёку: Екатеринбургский зоопарк, Свято‑Троицкий Кафедральный собор и Памятник клавиатуре.`,
					isFullDesk: false,
					subsDesk: 180,
					showAllPluses: false,
					pluses: [`WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`, `WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`],
					review: 17,
					indexOfPhoto: 0,
				},
				{
					title: `Grand Way Один`,
					raiting: 5,
					images: [`src/assets/images/icons/hotelImage.png`, `src/assets/images/icons/hotelImage.png`],
					price: 113796,
					grade: 8.9,
					type: `Отель`,
					plusPlace: `Сочи, 0.5 км до центра города`,
					short_desk: `Отдых должен быть комфортным! Отель «SLIDE Bleisure &amp; MICE Hotel» находится в Екатеринбурге. Этот отель расположен неподалёку от центра города. Рядом с отелем можно прогуляться. Неподалёку: Екатеринбургский зоопарк, Свято‑Троицкий Кафедральный собор и Памятник клавиатуре.`,
					isFullDesk: false,
					subsDesk: 180,
					showAllPluses: false,
					pluses: [`WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`, `WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`],
					review: 17,
					indexOfPhoto: 0,
				},
				{
					title: `Grand Way Один`,
					raiting: 5,
					images: [`src/assets/images/icons/hotelImage.png`, `src/assets/images/icons/hotelImage.png`],
					price: 113796,
					grade: 8.9,
					type: `Отель`,
					plusPlace: `Сочи, 0.5 км до центра города`,
					short_desk: `Отдых должен быть комфортным! Отель «SLIDE Bleisure &amp; MICE Hotel» находится в Екатеринбурге. Этот отель расположен неподалёку от центра города. Рядом с отелем можно прогуляться. Неподалёку: Екатеринбургский зоопарк, Свято‑Троицкий Кафедральный собор и Памятник клавиатуре.`,
					isFullDesk: false,
					subsDesk: 180,
					showAllPluses: false,
					pluses: [`WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`, `WI-FI`, `Трансфер`, `Парковка`, `Бар или ресторан`, `Другое`, `Конференс-зал`],
					review: 17,
					indexOfPhoto: 0,
				},
			],

			isSelectOpen: false,


			categorySearch: [
				{
					title: `Цена за ночь`,
					options: [`2 000 - 4 000`, `4 000 - 6 000`, `6 000 - 8 000`, `8 000 - 11 000`, `более 11 000`],
					type: `checkbox`,
					isHide: false,
					modal: [],
					isHideInSm: false,
				},
				{
					title: `Тип отеля`,
					options: [`Апарт-отели`, `Апартаменты`, `Гостевые дома`, `Курортные отели`, `Отели`],
					type: `checkbox`,
					isHide: false,
					isHideInSm: false,
				},
				{
					title: `Тип питания`,
					options: [`Питание не включено`, `Завтрак`, `Трехразовое питание`, `Двухразовое питание`],
					type: `checkbox`,
					isHide: false,
					isHideInSm: false,
				},
				{
					title: `Услуги`,
					options: [`Доступ в интернет`, `Бесплатный Wi-Fi`, `Парковка`, `Ресторан`, `Бассейн`, `Другое`],
					type: `checkbox`,
					isHide: false,
					isHideInSm: false,
				},
				{
					title: `Оценка гостей`,
					options: [`1+`, `2+`, `3+`, `4+`, `5+`],
					type: `radio`,
					isHideInSm: false,
				},
				{
					title: `Тема отеля`,
					options: [`Гольф/Спорт`, `Деловая поездка`, `Дизайн-отель`, `Дикая природа`, `Замок`, `Другое`],
					type: `checkbox`,
					isHide: false,
					isHideInSm: false,
				},
				{
					title: `Звёздность отеля`,
					options: [`Гольф/Спорт`, `Деловая поездка`, `Дизайн-отель`, `Дикая природа`, `Замок`, `Другое`],
					type: `checkbox`,
					isHide: false,
					isHideInSm: false,
				},
				{
					title: `Расстояние до центра`,
					isHide: false,
					isHideInSm: false,
				},
			],
			aaa: [],
			categoryData: {
				prices: {
					price24: false,
					price46: false,
					price68: false,
					price811: false,
					price11: false,
				},
				typeOfHotel: {
					isApartHotel: false,
					isApartament: false,
					isQuestHomes: false,
					isCurort: false,
					isHotel: false,
				},
				typeEat: {
					times0: false,
					times1: false,
					times3: false,
					times2: false,
				},
				pluses: {
					ethernet: false,
					wifi: false,
					parking: false,
					kafe: false,
					swimmingPool: false,
					other: false,
				},
				pluses: {
					plus1: false,
					plus2: false,
					plus3: false,
					plus4: false,
					plus5: false,
				},
				hotelTheme: {
					sport: false,
					buisness: false,
					design: false,
					art: false,
					town: false,
					other: false,
				},
				stars: {
					star0: false,
					star1: false,
					star2: false,
					star3: false,
					star4: false,
					star5: false,
				},
				range: 50,
			},

			isCheap: false,
			isExpensive: false,
			isReiting: false,

			openBlock5: false,
			openBlock3: false,

			paginator: [1, 2, 3],
		}
	},

	methods: {
		hideCategores(index) {
			this.categorySearch[index].isHide = !this.categorySearch[index].isHide;
			if(index == 52) {
				this.sort = !this.sort;
			}
		},

		showFilters(index) {
			this.categorySearch[index].isHideInSm = !this.categorySearch[index].isHideInSm;
			this.isOpenFiltersSm = !this.isOpenFiltersSm;
		},

		getInnerWidth() {
			if(window.innerWidth <= 1000) {
				this.isLargeWindow = false;
			}
			console.log(window.innerWidth);
		},

		reset() {
			this.categoryData.prices.price24 = false;
			this.categoryData.prices.price46 = false;
			this.categoryData.prices.price68 = false;
			this.categoryData.prices.price811 = false;
			this.categoryData.prices.price11 = false;
			this.categoryData.typeOfHotel.isApartHotel = false;
			this.categoryData.typeOfHotel.isApartament = false;
			this.categoryData.typeOfHotel.isQuestHomes = false;
			this.categoryData.typeOfHotel.isCurort = false;
			this.categoryData.typeOfHotel.isHotel = false;
			this.categoryData.typeEat.times0 = false;
			this.categoryData.typeEat.times1 = false;
			this.categoryData.typeEat.times2 = false;
			this.categoryData.typeEat.times3 = false;
			this.categoryData.pluses.ethernet = false;
			this.categoryData.pluses.wifi = false;
			this.categoryData.pluses.parking = false;
			this.categoryData.pluses.kafe = false;
			this.categoryData.pluses.swimmingPool = false;
			this.categoryData.pluses.other = false;
			this.categoryData.pluses.plus1 = false;
			this.categoryData.pluses.plus2 = false;
			this.categoryData.pluses.plus3 = false;
			this.categoryData.pluses.plus4 = false;
			this.categoryData.pluses.plus5 = false;
			this.categoryData.hotelTheme.sport = false;
			this.categoryData.hotelTheme.buisness = false;
			this.categoryData.hotelTheme.design = false;
			this.categoryData.hotelTheme.art = false;
			this.categoryData.hotelTheme.town = false;
			this.categoryData.hotelTheme.other = false;
			this.categoryData.stars.star0 = false;
			this.categoryData.stars.star1 = false;
			this.categoryData.stars.star2 = false;
			this.categoryData.stars.star3 = false;
			this.categoryData.stars.star4 = false;
			this.categoryData.stars.star5 = false;
			this.range = 50;
		},

		sortP(value) {
			if(value == 1) {
				this.isCheap = !this.isCheap;
				this.isExpensive = false;
				this.isReiting = false;
			} else if(value == 2) {
				this.isCheap = false;
				this.isExpensive = !this.isExpensive;
				this.isReiting = false;
			} else if(value == 3) {
				this.isCheap = false;
				this.isExpensive = false;
				this.isReiting = !this.isReiting;
			}
		},

		pagination(number) {
			if(number != 52 && number != 0) {
				this.$router.push(`/hotels?page=${number}`)
				if(number > 2) {
					if(number <= 5) {
						this.paginator[0] = number - 1;
						this.paginator[1] = number;
						this.paginator[2] = number + 1;
					}
				}
			} else if(number == 0) {
				this.paginator = [1, 2, 3];
				this.$router.push(`/hotels?page=${1}`)
			} else {
				this.paginator = [1, 2, 3];
			}
		},

		sliderLeft(index) {
			if (this.hotels[index].indexOfPhoto == 0) {
				this.hotels[index].indexOfPhoto = this.hotels[index].images.length - 1;
			} else {
				this.hotels[index].indexOfPhoto--;
			}
			console.log(hotels[index].indexOfPhoto);
		},

		sliderRight(index) {
			if (this.hotels[index].indexOfPhoto == this.hotels[index].images.length - 1) {
				this.hotels[index].indexOfPhoto = 0;
			} else {
				this.hotels[index].indexOfPhoto++;
			}
			console.log(hotels[index].indexOfPhoto);
		},
	},

	mounted() {
		this.getInnerWidth();
		this.$router.push(`/hotels?page=${1}`)
	}
}

</script>


<template>
	<HeaderProduct />

	<div v-if='this.isCalendar1'>
		<div class="data-modal-left">
			<DatePicker v-model='form.enter' />
		</div>
		<div class="data-modal-right">
			<DatePicker v-model='form.outer' />
		</div>
	</div>

	<div class="title d-flex flex-column align-items-center pb-4 pt-6">
		<h1>Авиабилеты</h1>
		<router-link to="/flight-tickets">Путешевствия</router-link>
	</div>
	<main class="main container">

		<nav aria-label="breadcrumb" class="breadcrumb-nav mb-1"
			style="border-top: 0.1rem solid rgba(235, 235, 235, 0.55);">
			<div class="container">
				<ol class="breadcrumb">
					<li class="breadcrumb-item">
						<router-link to="/">Главная</router-link>
					</li>
					<li class="breadcrumb-item">
						<router-link to="/hotels" class='black-flight'>Путешевствия</router-link>
					</li>
				</ol>
			</div>
		</nav>

		<nav>
			<div class="types-site mb-3">
				<button class='d-flex align-items-center'>
					<img class='mr-2' src="../../../assets/images/icons/airplaneImage.svg">
					<span>Чартеры</span>
				</button>
				<button class='d-flex align-items-center'>
					<img class='mr-2' src="../../../assets/images/icons/train.svg">
					<span>Ж/Д билеты</span>
				</button>
				<button class='d-flex align-items-center hot-bg'>
					<img class='mr-2' src="../../../assets/images/icons/hotels.svg">
					<span>Отели</span>
				</button>
			</div>
		</nav>

		<form class="d-flex justify-content-start align-items-center" @submit.prevent=''>
			<div class="inputs-block d-flex flex-row py-22">
				<div class="rel">
					<input v-model='form.place' type="text" placeholder='Город или отель'>
					<img @click='this.form.place = ``' class='cenel-text' src="../../../assets/images/icons/Cenel.svg">
				</div>
				<div class="data-inputs d-flex">
					<div class="rel">
						<input class='date-inp1' :value='form.enter' placeholder='Дата въезда'>
						<img @click='this.isCalendar1 = !this.isCalendar1' class='calendar-left cursor-pointer'
							src="../../../assets/images/icons/calendar.svg">
					</div>
					<div class="rel">
						<input class='date-inp2' :value='form.outer' placeholder='Дата выезда'>
						<img @click='this.isCalendar1 = !this.isCalendar1' class='calendar-right cursor-pointer'
							src="../../../assets/images/icons/calendar.svg">
					</div>
				</div>
				<div class="rel">
					<select v-model='form.persons'>
						<option value="1">1 гость</option>
						<option value="2">2 гостя</option>
						<option value="3">3 гостя</option>
						<option value="4">4 гостя</option>
					</select>
					<img class='person-select' src="../../../assets/images/icons/user.svg">
				</div>
			</div>
			<button class="find-btn ml-3"><img src="../../../assets/images/icons/searchWhite.svg" alt='52'> <span
					class='ml-2'>Найти</span></button>
		</form>

		

		<div class="main-page d-flex">

			<div class="left-block">
				<div class="widget widget-clean mb-0 mt-2">
					<label style="font-family: Gilroy-Medium !important;">Фильтры:</label>
					<a href="#" class="sidebar-filter-clear" style="font-size: 14px !important; "
						@click.prevent="reset">Очистить</a>
				</div>
				<div class="show-not-map">
					<img class='fake-map'
					src="../../../assets/images/icons/showMap.svg" alt="Карта">
					<button v-if='this.showFakeMap' @click='this.showFakeMap = !this.showFakeMap'> <img src="../../../assets/images/icons/location.svg" alt=""> Скрыть карту</button>
					<button v-else @click='this.showFakeMap = !this.showFakeMap'> <img src="../../../assets/images/icons/location.svg" alt=""> Показать карту</button>
				</div>




				<div class="search-container mt-3 d-flex flex-column">
					<div class="search-block mb-2" v-if='this.categorySearch[0].isHideInSm || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[0].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[0].isHide }' @click='hideCategores(0)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
							<img class='close-lg-not' @click='this.categorySearch[0].isHideInSm = !this.categorySearch[0].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[0].isHide' class="options-block">
							<input class='top-box top-box2' id='15252' type="checkbox" disabled>
							<label for='15252'>До 2000</label>
							<input v-model='categoryData.prices.price24' class='top-box' id='1' type="checkbox">
							<label for='1'>{{ categorySearch[0].options[0] }}</label>
							<input v-model='categoryData.prices.price46' class='top-box' id='2' type="checkbox">
							<label for='2'>{{ categorySearch[0].options[1] }}</label>
							<input v-model='categoryData.prices.price68' class='top-box' id='3' type="checkbox">
							<label for='3'>{{ categorySearch[0].options[2] }}</label>
							<input v-model='categoryData.prices.price811' class='top-box' id='4' type="checkbox">
							<label for='4'>{{ categorySearch[0].options[3] }}</label>
							<input v-model='categoryData.prices.price11' class='top-box' id='5' type="checkbox">
							<label for='5'>{{ categorySearch[0].options[4] }}</label>
						</div>
					</div>

					<div class="search-block mb-2" v-if='this.categorySearch[6].isHideInSm  || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[6].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[6].isHide }' @click='hideCategores(6)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
								<img class='close-lg-not' @click='this.categorySearch[6].isHideInSm = !this.categorySearch[6].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[6].isHide' class="options-block">
							<input v-model='categoryData.stars.star1' class='top-box' id='11152' type="checkbox">
							<label for='11152'> <img src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> </label>
							<input v-model='categoryData.stars.star2' class='top-box' id='11252' type="checkbox">
							<label for='11252'> <img src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> </label>
							<input v-model='categoryData.stars.star3' class='top-box' id='11352' type="checkbox">
							<label for='11352'> <img src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> </label>
							<input v-model='categoryData.stars.star4' class='top-box' id='11452' type="checkbox">
							<label for='11452'> <img src="../../../assets/images/icons/star.svg" alt="star"> <img
									src="../../../assets/images/icons/star.svg" alt="star"> </label>
							<input v-model='categoryData.stars.star5' class='top-box' id='11552' type="checkbox">
							<label for='11552'> <img src="../../../assets/images/icons/star.svg" alt="star"> </label>
							<input v-model='categoryData.stars.star0' class='top-box' id='115522' type="checkbox">
							<label for='115522'> Без звёзд </label>
						</div>
					</div>

					<div class="search-block mb-2" v-if='this.categorySearch[1].isHideInSm  || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[1].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[1].isHide }' @click='hideCategores(1)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
								<img class='close-lg-not' @click='this.categorySearch[1].isHideInSm = !this.categorySearch[1].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[1].isHide' class="options-block">
							<input v-model='categoryData.typeOfHotel.isApartHotel' class='top-box' id='6' type="checkbox">
							<label for='6'>{{ categorySearch[1].options[0] }}</label>
							<input v-model='categoryData.typeOfHotel.isApartament' class='top-box' id='7' type="checkbox">
							<label for='7'>{{ categorySearch[1].options[1] }}</label>
							<input v-model='categoryData.typeOfHotel.isQuestHomes' class='top-box' id='8' type="checkbox">
							<label for='8'>{{ categorySearch[1].options[2] }}</label>
							<input v-model='categoryData.typeOfHotel.isCurort' class='top-box' id='9' type="checkbox">
							<label for='9'>{{ categorySearch[1].options[3] }}</label>
							<input v-model='categoryData.typeOfHotel.isHotel' class='top-box' id='1' type="checkbox">
							<label for='10'>{{ categorySearch[1].options[4] }}</label>
						</div>
					</div>

					<div class="search-block mb-2" v-if='this.categorySearch[2].isHideInSm  || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[2].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[2].isHide }' @click='hideCategores(2)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
								<img class='close-lg-not' @click='this.categorySearch[2].isHideInSm = !this.categorySearch[2].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[2].isHide' class="options-block">
							<input v-model='categoryData.typeEat.times0' class='top-box' id='16' type="checkbox">
							<label for='16'>{{ categorySearch[2].options[0] }}</label>
							<input v-model='categoryData.typeEat.times1' class='top-box' id='17' type="checkbox">
							<label for='17'>{{ categorySearch[2].options[1] }}</label>
							<input v-model='categoryData.typeEat.times2' class='top-box' id='18' type="checkbox">
							<label for='18'>{{ categorySearch[2].options[2] }}</label>
							<input v-model='categoryData.typeEat.times3' class='top-box' id='19' type="checkbox">
							<label for='19'>{{ categorySearch[2].options[3] }}</label>
						</div>
					</div>

					<div class="search-block mb-2" v-if='this.categorySearch[3].isHideInSm  || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[3].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[3].isHide }' @click='hideCategores(3)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
								<img class='close-lg-not' @click='this.categorySearch[3].isHideInSm = !this.categorySearch[3].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[3].isHide' class="options-block">
							<input v-model='categoryData.pluses.ethernet' class='top-box' id='116' type="checkbox">
							<label for='116'>{{ categorySearch[3].options[0] }}</label>
							<input v-model='categoryData.pluses.wifi' class='top-box' id='117' type="checkbox">
							<label for='117'>{{ categorySearch[3].options[1] }}</label>
							<input v-model='categoryData.pluses.parking' class='top-box' id='118' type="checkbox">
							<label for='118'>{{ categorySearch[3].options[2] }}</label>
							<input v-model='categoryData.pluses.kafe' class='top-box' id='119' type="checkbox">
							<label for='119'>{{ categorySearch[3].options[3] }}</label>
							<input v-model='categoryData.pluses.swimmingPool' class='top-box' id='120' type="checkbox">
							<label for='120'>{{ categorySearch[3].options[4] }}</label>
							<input v-model='categoryData.pluses.other' class='top-box' id='121' type="checkbox">
							<label for='121'>{{ categorySearch[3].options[5] }}</label>
							<div class="close-block" v-if='this.openBlock3'>
									<input v-model='categoryData.hotelTheme.other' class='top-box' id='15522' type="checkbox">
									<label for='15522'>{{ categorySearch[3].options[1] }}</label>
								</div>
							</div>
							<h6 v-if='!this.openBlock3' class='cursor-pointer' @click='this.openBlock3 = !this.openBlock3'><u>Показать все</u></h6>
							<h6 v-else class='cursor-pointer' @click='this.openBlock3 = !this.openBlock3'><u>Скрыть</u></h6>
					</div>

					<div class="search-block mb-2" v-if='this.categorySearch[4].isHideInSm  || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[4].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[4].isHide }' @click='hideCategores(4)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
								<img class='close-lg-not' @click='this.categorySearch[4].isHideInSm = !this.categorySearch[4].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[4].isHide' class="options-block">
							<input v-model='categoryData.pluses.plus1' class='top-radio' id='152' type="checkbox">
							<label for='152'>{{ categorySearch[4].options[0] }}</label>
							<input v-model='categoryData.pluses.plus2' class='top-radio' id='252' type="checkbox">
							<label for='252'>{{ categorySearch[4].options[1] }}</label>
							<input v-model='categoryData.pluses.plus3' class='top-radio' id='352' type="checkbox">
							<label for='352'>{{ categorySearch[4].options[2] }}</label>
							<input v-model='categoryData.pluses.plus4' class='top-radio' id='452' type="checkbox">
							<label for='452'>{{ categorySearch[4].options[3] }}</label>
							<input v-model='categoryData.pluses.plus5' class='top-radio' id='552' type="checkbox">
							<label for='552'>{{ categorySearch[4].options[4] }}</label>
						</div>
					</div>

					<div class="search-block mb-2" v-if='this.categorySearch[7].isHideInSm  || this.isLargeWindow'>
						<div class="title-block d-flex justify-content-between align-items-center mb-2">
							<h5 class='mb-0'>{{ categorySearch[7].title }}</h5>
							<img :class='{ "rotate-180": categorySearch[7].isHide }' @click='hideCategores(7)' class='cursor-pointer return-category'
								src="../../../assets/images/icons/VectorUp.svg" alt="">
								<img class='close-lg-not' @click='this.categorySearch[7].isHideInSm = !this.categorySearch[7].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
						</div>
						<div v-if='!categorySearch[7].isHide' class="options-block d-flex flex-column">
							<label class='range-label mb-0' for='range'>{{ categoryData.range }}км</label>
							<input v-model='categoryData.range' class='top-range' id='radius' type="range" min='1' max='200' </div>
						</div>

						<div class="search-block mb-2" v-if='this.categorySearch[5].isHideInSm  || this.isLargeWindow'>
							<div class="title-block d-flex justify-content-between align-items-center mb-2">
								<h5 class='mb-0'>{{ categorySearch[5].title }}</h5>
								<img :class='{ "rotate-180": categorySearch[5].isHide }' @click='hideCategores(5)' class='cursor-pointer return-category'
									src="../../../assets/images/icons/VectorUp.svg" alt="">
									<img class='close-lg-not' @click='this.categorySearch[5].isHideInSm = !this.categorySearch[5].isHideInSm' src="../../../assets/images/icons/Close.svg" alt="Close">
							</div>
							<div v-if='!categorySearch[5].isHide' class="options-block">
								<input v-model='categoryData.hotelTheme.sport' class='top-box' id='1152' type="checkbox">
								<label for='1152'>{{ categorySearch[5].options[0] }}</label>
								<input v-model='categoryData.hotelTheme.buisness' class='top-box' id='1252' type="checkbox">
								<label for='1252'>{{ categorySearch[5].options[1] }}</label>
								<input v-model='categoryData.hotelTheme.design' class='top-box' id='1352' type="checkbox">
								<label for='1352'>{{ categorySearch[5].options[2] }}</label>
								<input v-model='categoryData.hotelTheme.art' class='top-box' id='1452' type="checkbox">
								<label for='1452'>{{ categorySearch[5].options[3] }}</label>
								<input v-model='categoryData.hotelTheme.town' class='top-box' id='1552' type="checkbox">
								<label for='1552'>{{ categorySearch[5].options[4] }}</label>
								<div class="close-block" v-if='this.openBlock5'>
									<input v-model='categoryData.hotelTheme.other' class='top-box' id='15522' type="checkbox">
									<label for='15522'>{{ categorySearch[5].options[5] }}</label>
								</div>
							</div>
							<h6 v-if='!this.openBlock5' class='cursor-pointer' @click='this.openBlock5 = !this.openBlock5'><u>Показать все</u></h6>
							<h6 v-else class='cursor-pointer' @click='this.openBlock5 = !this.openBlock5'><u>Скрыть</u></h6>
						</div>
					</div>


				</div>

				<div class="middle-block" :class="{'w-mr': !this.showFakeMap}">

					<div class="sort-block d-flex justify-content-end mt-2">
						<div class='sort-select-menu cursor-pointer'>
							<div class="d-flex">
								<span class='mr-2'  @click='this.isSelectOpen = !this.isSelectOpen'>Сортировать по</span> 
								<img  @click='this.isSelectOpen = !this.isSelectOpen' class='rotate-180 cursor-pointer return-category' src="../../../assets/images/icons/VectorUp.svg" alt="">
							</div>

							<div class="select-open-menu d-flex flex-column mt-1" v-if='this.isSelectOpen'>
								<span class='d-flex alugn-items-center' :class='{"active-sorting": isCheap}' @click='sortP(1)'>
									 <img v-if='this.isCheap' class='mr-2' src="../../../assets/images/icons/arrowOkey.svg"> 
									 <span>Сначала дешёвые</span></span>
								<span class='d-flex alugn-items-center' :class='{"active-sorting": isExpensive}' @click='sortP(2)'>
									 <img v-if='this.isExpensive' class='mr-2' src="../../../assets/images/icons/arrowOkey.svg"> 
									 <span>Сначала дорогие</span></span>
								<span class='d-flex alugn-items-center' :class='{"active-sorting": isReiting}' @click='sortP(3)'>
									 <img v-if='this.isReiting' class='mr-2' src="../../../assets/images/icons/arrowOkey.svg"> 
									 <span>По рейтингу</span></span>
							</div>
						</div>
						<div class="filters-btn sort-select w-100" @click='this.isOpenFiltersSm = !this.isOpenFiltersSm' >
							<img class='mr-2' src="../../../assets/images/icons/filters.svg" alt="">
							<span>Фильтры и сортировка</span>
						</div>
						<div class="filters" v-if='this.isOpenFiltersSm'>
							<div class="top-menus mt-4 mb-3 d-flex justify-content-between align-items-center">
								<h4>Фильтры и сортировка</h4>
								<span class='d-flex pr-3'><span @click.prevent="reset">Сбросить</span> <img @click='this.isOpenFiltersSm = !this.isOpenFiltersSm'  class='ml-2'src="../../../assets/images/icons/Close.svg" alt=""> </span>
							</div>

							<div class="filters-container">
								<div class='filter-btn' v-for='(item, index) in categorySearch' @click='showFilters(index)'>
									<h5>{{ item.title }}</h5>
								</div>
								<div @click='this.sort = !this.sort' class="filter-btn">
									<h5>Сортировка</h5>
								</div>
							</div>

							<div class="search-block mb-2 p-2" v-if='this.sort'>
							<div class="title-block d-flex justify-content-between align-items-center mb-2">
								<h5 class='mb-0'>Сортировать</h5>
									<img class='close-lg-not' @click='this.sort = !this.sort' src="../../../assets/images/icons/Close.svg" alt="Close">
							</div>
							<div class="options-block d-flex flex-column">
								<span class='d-flex alugn-items-center' :class='{"active-sorting": isCheap}' @click='sortP(1)'>
									 <img v-if='this.isCheap' class='mr-2 mb-2' src="../../../assets/images/icons/arrowOkey.svg"> 
									 <span class='mb-2'>Сначала дешёвые</span></span>
								<span class='d-flex alugn-items-center' :class='{"active-sorting": isExpensive}' @click='sortP(2)'>
									 <img v-if='this.isExpensive' class='mr-2 mb-2' src="../../../assets/images/icons/arrowOkey.svg"> 
									 <span class='mb-2'>Сначала дорогие</span></span>
								<span class='d-flex alugn-items-center' :class='{"active-sorting": isReiting}' @click='sortP(3)'>
									 <img v-if='this.isReiting' class='mr-2' src="../../../assets/images/icons/arrowOkey.svg"> 
									 <span>По рейтингу</span></span>
							</div>
						</div>


						</div>
					</div>

					<div class="hotels-container d-flex flex-column">
						<div class="hotel-card mt-1 cursor-pointer" v-for='(hotel, index) in hotels' :class='{"d-flex card-top big-shadow-card": !this.showFakeMap}'>
							<div class="image-main-cont" :class='{"w-182": !this.showFakeMap}'>
									<img v-if='!this.showFakeMap' @click='sliderLeft(index)' class='arrow arrow-left'src="../../../assets/images/icons/imageArrow.svg" alt="Arrow">		
								<img :src="hotel.images[hotel.indexOfPhoto]" :alt="hotel.title">
									<img v-if='!this.showFakeMap' @click='sliderRight(index)' class='arrow arrow-right'src="../../../assets/images/icons/imageArrow.svg" alt="Arrow">			
									<img v-if='!this.showFakeMap' @click='sliderRight()' class='favorite-img' src="../../../assets/images/icons/heart.svg" alt="Arrow">			
							</div>
							<div :class='{"main-main-info": !this.showFakeMap}'  class="d-flex flex-column p-5">
								<div :class='{"full-hotel-card": !this.showFakeMap}' class="info-main d-flex align-items-center justify-content-between">
									<div class="d-flex align-items-center">
										
										<img src="../../../assets/images/icons/starNormal.svg" :alt="star" v-for='star in hotel.raiting'>
										<span class='ml-2'>{{ hotel.type }}</span>
									</div>
									<span class='top-right-rating'> <u v-if='hotel.isFullDesk' class='mr-3'>{{ hotel.review }} отзывов</u> <b>{{ hotel.grade }}</b></span>
								</div>
								<div :class='{"sort-info-bottom": !this.showFakeMap}' class="sort-info d-flex align-items-center justify-content-between mt-1">
									<h5 class='fw-bold'>{{ hotel.title }}</h5>
									<div class="locations-map d-block" v-if='!this.showFakeMap'>
										<u class='mr-3'>на карте</u>
										<span>{{ hotel.plusPlace }}</span>
									</div>
									<div class="full-desk" v-if='hotel.isFullDesk && !this.showFakeMap'>
										<p>{{ hotel.short_desk.substring(0, hotel.subsDesk) }}<span v-if='hotel.subsDesk == 180'>...</span> </p>
										<div class="d-flex justify-content-end">
											<u v-if='hotel.subsDesk == 180' @click='hotel.subsDesk = 33333'>Подробнее</u>
											<u v-else @click='hotel.subsDesk = 180'>Свернуть</u>
										</div>
										<div class="plus-container d-flex flex-row flex-wrap">
											<div class="d-flex flex-column mr-5 pr-5">
												<div class='first-pluses info-main d-flex align-items-center flex-wrap' v-for='(plus, i) in hotel.pluses'>
													<img v-if='i <= 5 || hotel.showAllPluses' src="../../../assets/images/icons/pluses.svg">
													<span v-if='i <= 5 || hotel.showAllPluses' class='ml-2'>{{ plus }}</span>
												</div>
											</div>
											<div class="d-flex flex-column">
												<div class='second-pluses info-main d-flex align-items-center flex-wrap' v-for='(plus, i) in hotel.pluses' >
													<img v-if='i <= 5 || hotel.showAllPluses' src="../../../assets/images/icons/pluses.svg">
													<span v-if='i <= 5 || hotel.showAllPluses' class='ml-2'>{{ plus }}</span>
												</div>
											</div>
										</div>
										<button v-if='!hotel.showAllPluses' @click='hotel.showAllPluses = !hotel.showAllPluses'>Все услуги и удобства</button>
										<button v-else @click='hotel.showAllPluses = !hotel.showAllPluses'>Скрыть услуги и удобства</button>
									</div>
									<div :class='{"price-card-end": !this.showFakeMap}' class="price-block d-flex flex-column align-items-end">
										<h4 class='mb-0'><b>{{ hotel.price.toString().split(/(\d{3})/).join(' ').trim() }},00 <span v-if='!this.showFakeMap'>баллов</span> </b></h4>
										<span>За 1 ночь</span>
										<button @click='this.hotels[index].isFullDesk = !this.hotels[index].isFullDesk' v-if='!this.showFakeMap && !this.hotels[index].isFullDesk' class='find-btn w-100'>Подробнее</button>
										<button @click='this.hotels[index].isFullDesk = !this.hotels[index].isFullDesk' v-if='!this.showFakeMap && this.hotels[index].isFullDesk' class='find-btn w-100'>Выбрать</button>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<div class="right-block" v-if='this.showFakeMap && this.isLargeWindow'>
					<iframe src="https://www.google.com/maps/embed?pb=!1m16!1m12!1m3!1d217759.93368463306!2d55.44421602699476!3d25.377280411563785!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!2m1!1sal%20bustan%20hotel%204*2A!5e0!3m2!1sru!2sru!4v1726390730633!5m2!1sru!2sru" width="483" height="908" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" class='cuesor-pointer mt-2'></iframe>
				</div>
			</div>

			<div class="d-flex justify-content-center">
				<div class="pagination">
					<div class="left-arrow d-flex cursor-pointer" @click='pagination(0)'>
						<img src="../../../assets/images/icons/pagArrowLeft.svg">
						<span>В начало</span>
					</div>
					<div class="middle-counter d-flex">
						<div class="block-pagination cursor-pointer" v-for='number in paginator' @click='pagination(number)' :class='{"active-pag": this.$route.query.page == number}'>{{ number }}</div>
					</div>
					<div class="right-arrow d-flex align-items-center">
						<span>из 6</span>
						<span class='next ml-4 mr-2 cursor-pointer' @click='pagination(Number(this.$route.query.page) + 1)'>Дальше</span>
						<img class='cursor-pointer' src="../../../assets/images/icons/pagArrowRight.svg">
					</div>
				</div>
			</div>

	</main>
</template>

<style scoped>
.show-not-map {
	position: relative;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-bottom: 10px;
	cursor: default !important;
}

.show-not-map button {
	display: flex;
	align-items: center;
	gap: 5px;
	position: absolute;
	background-color: #FFFFFF;
	border-radius: 7px;
	padding: 8px 16px;
	border: 1px solid #e6e6e6;
	font-size: 14px;
	color: #797979;
	font-weight: 500;
}

.hotels-container {
	gap: 10px;
}

.hot-bg {
	background: #55246A;
	border: 2px solid #55246A;
	padding: 6px 8px;
	border-radius: 10px;
}

.hot-bg span {
	color: #fff !important;
	font-weight: 700 !important;
}

.types-site {
	display: none;
	justify-content: start;
	gap: 2px;
}

.types-site button {
	padding: 8px;
}

.types-site button span {
	color: #797979;
	font-size: 12px;
	font-weight: 400;
}

.active-pag {
	border: 1px solid #e6e6e6 !important;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-right: 2.2rem;
	border-radius: 6px;
}

.block-pagination {
	width: 30px;
	height: 30px;
}

.left-arrow span  {
	color: #E6E6E6 !important;
	margin-left: 5px;
}

.pagination {
	display: flex;
	align-items: center;
	gap: 20px;
}

.active-sorting {
	color: #55246A !important;
}

.favorite-img {
	position: absolute;
	top: 10px;
	right: 10px;
	width: 20px !important;
	height: 20px !important;
}

.w-mr {
	width: calc(381px + 482px + 18px) !important;
}

.sidebar-filter-clear {
	color: #777;
}

@media (max-width: 1200px) {
	.middle-block {
		width: 100% !important;
	}

	.types-site {
		background: #F4F7FF;
		padding: 3px 0;
		border-radius: 8px;
	}

	.show-not-map button {
		display: none !important;
	}

	.types-site {
		display: flex !important;
	}

	.search-block {
		border-top: 1px solid #e6e6e6;
		padding-top: 10px !important;
	}

	.hotel-card img {
		width: 100% !important;
		height: 100% !important;
		object-fit: cover;
	}

	.inputs-block {
		flex-direction: column !important;
		gap: 20px !important;
		width: 100% !important;
		border: none !important;
	}

	.rel input, .rel select {
		border-top: 1px solid #e6e6e6 !important;
		border-right: 1px solid #e6e6e6 !important;
		border-bottom: 1px solid #e6e6e6 !important;
		border-left: 1px solid #e6e6e6 !important;
		border-radius: 10px !important;
	}

	.data-inputs {
		display: flex;
		gap: 10px;
	}

	.rel {
		width: 100% !important;
	}

	.date-inp1 {
		margin-right: 10px !important;
	}

	.date-inp2 {
		width: 100% !important;
		border-right: 1px solid #e6e6e6 !important;
	}

	form {
		flex-direction: column !important;
	}

	input, select {
		width: 100% !important;
	}

	.find-btn {
		width: 100% !important;
		margin-top: 10px;
		height: 45px !important;
	}

	.person-select {
		top: 3px !important;
	}

	.data-modal-left {
		top: 40px !important;
		left: 15% !important;
		z-index: 52;
	}

	.data-modal-right {
		top: 450px !important;
		left: 15% !important;
		z-index: 52;
	}

	.sort-block select {
		display: none !important;
	}
	
	.left-block {
		width: 0 !important;
	}

	.right-block {
		width: 0 !important;
	}

	.widget, .fake-map {
		display: none;
	}

	.filters-btn {
		display: flex !important;
		justify-content: center;
	}

	.search-block {
		position: fixed;
		display: block !important;
		bottom: 0;
		left: 0;
		background: #fff;
		z-index: 52;
		width: 100%;
		margin-bottom: 0 !important;
		padding: 5px;
		box-shadow: 0px 1px 8px 0px #0000001A !important;
	}

	.return-category {
		display: none !important;
	}

	.sort-select-menu {
		display: none !important;
	}
}

@media (min-width: 1000px) {
	.close-lg-not {
		display: none;
	}
}

.filters-btn {
	display: none;
}

.filters {
	position: fixed;
	bottom: 0;
	left: 0;
	width: 100%;
	background: #fff;
	z-index: 12;
	border-top: 1px solid #e6e6e6;
}

.search-block {
	box-shadow: 0px 1px 8px 0px #0000001A !important;
	padding: 16px 24px;
	border-radius: 6px;
}

.top-menus h4 {
	font-size: 20px;
	color: #333;
	margin-bottom: 0 !important;
	padding-left: 8px;
}

.filter-btn {
	padding: 12px 8px;
}

.filter-btn h5 {
	font-size: 16px;
	color: #333;
}

.filter-btn:nth-child(3n) {
	border-bottom: 1px solid #e6e6e6;
	padding-bottom: 6px !important;
}

.filter-btn:nth-child(4n) {
	padding-top: 12px !important;
}

.top-range {
	width: 100% !important;
	cursor: pointer !important;
}

.top-radio+label {
	position: relative;
	padding-left: 30px;
	height: 1.5em;
	display: flex;
	align-items: center;
	color: #000;
	cursor: pointer;
	user-select: none;
}

.top-radio:checked+label::before {
	border-radius: 100%;
	border: 5px solid #55246A;
	background-size: 13px !important;
	background-position: center center;
	background-size: contain;
}

.top-radio+label:before {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	width: 1.4em;
	height: 1.4em;
	border: 1px solid #ccc;
	border-radius: 100%;
}

#radius,
#radius-2 {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    width: 250px;
    height: 18px;
    border: none;
    border-radius: 4px;
    overflow: hidden;
}

#radius::-webkit-slider-thumb,
#radius-2::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    background-color: #55246A;
    border: 0px solid #55246A;
    border-radius: 50%;
    height: 18px;
    width: 18px;
    margin-top: -7px;
    box-shadow: calc(-100vmax - 18px) 0 0 100vmax #55246A;
    clip-path: polygon(
        100% 0,
        2px 0,
        0 7px,
        -100vmax 7px,
        -100vmax 11px,
        0 11px,
        2px 100%,
        100% 100%
    );
}

#radius::-moz-range-thumb,
#radius-2::-moz-range-thumb {
    -moz-appearance: none;
    appearance: none;
    background-color: #55246A;
    border: 0px solid #55246A;
    border-radius: 50%;
    height: 18px;
    width: 18px;
    margin-top: -7px;
}

#radius::-webkit-slider-runnable-track,
#radius-2::-webkit-slider-runnable-track {
    height: 4px;
    border-radius: 4px;
    border: 0px solid #fff;
    box-shadow: 0px 0px 0px #353535;
    background: #d7d7d7;
}

.rotate-180 {
	rotate: 180deg;
}

.top-box:disabled+label {
	color: #ADADAD !important;
}

.top-box2+label::before {
	border: 1px solid #ececec !important;
	background: #F5F5F5 !important;
}

.top-box, .top-radio {
	display: none;
}

.top-box+label {
	position: relative;
	padding-left: 30px;
	height: 1.5em;
	display: flex;
	align-items: center;
	color: #000;
	cursor: pointer;
	user-select: none;
	border-radius: 5px !important;
	transition: all 50ms;
}

.top-box:checked+label::before {
	border-radius: 3px;
	border-color: #55246A;
	background-image: url('../../../assets/images/icons/Okey.svg');
	background-repeat: no-repeat;
	background-size: 13px !important;
	background-position: center center;
	background-size: contain;
	background-color: #55246A;
	color: #55246A !important;
}

input[type="checkbox"]:checked + label {
	color: #55246A !important;
}

.top-box+label:before {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	width: 1.4em;
	height: 1.4em;
	border: 1px solid #ccc;
	border-radius: 5px !important;
	color: #55246A !important;
}

.options-block input {
	width: fit-content;
	margin-right: 8px;
}

.fw-bold {
	color: #333 !important;
}

.black-flight {
	color: #000 !important;
}

.info-main b {
	color: #55246A;
	background-color: #F4F7FF !important;
	padding: 4px 8px;
	border-radius: 5px;
}

.hotel-card {
	position: relative;
	border: 1px solid #F3F3F3 !important;
	box-shadow: 0px 8px 55px 0px #00000005 !important;
	border-radius: 6px;
}

.big-shadow-card {
	box-shadow: 0px 1px 8px 0px #0000001A !important;
}

.hotel-card img {
	width: 381px;
	height: 181px;
	border-radius: 6px;
	object-fit: cover;
}

.full-hotel-card {
	justify-content: start !important;
}

.sort-info-bottom {
	flex-direction: column !important;
	align-items: start !important;
	margin-top: 0 !important;
}

.sort-info-bottom h5 {
	margin-bottom: 0 !important;
}

.main-main-info {
	padding-right: 230px !important;
	padding-top: 10px !important;
	padding-bottom: 60px !important;
}

.top-right-rating {
	position: absolute;
	top: 15px;
	right: 15px;
}

.full-hotel-card span u {
	font-weight: 400 !important;
	color: #333;
}

.price-card-end {
	position: absolute;
	bottom: 10px;
	right: 10px;
}

.one-plus1 img {
	width: 13px !important;
}

.image-main-cont {
	position: relative;
}

.image-main-cont img:nth-child(2) {
	width: 100% !important;
	height: auto !important;
	object-fit: cover !important;
}

.w-182 img:nth-child(2) {
	min-width: 181px !important;
	width: 181px !important;
	height: 100% !important;
	border-radius: 6px;
	object-fit: cover;
}

.arrow {
	position: absolute;
	top: calc(50% - 12px);
	width: 24px !important;
	height: 24px !important;
}

.arrow-left {
	left: 10px;
	rotate: 180deg;
}

.arrow-right {
	right: 10px;
}

.info-main img {
	width: 13px !important;
	height: 13px !important;
	object-fit: cover;
}

.first-pluses:nth-child(2n - 1) {
	display: none !important;
}

.second-pluses:nth-child(2n) {
	display: none !important;
}

.full-desk button {
	border: 1px solid #dddddd;
	padding: 6px 12px;
	margin-top: 16px;
	border-radius: 6px;
	font-weight: 500;
	color: 333;
	font-size: 16px;
}

.sort-select-menu {
	position: relative;
	border: 1px solid #E6E6E6;
	border-radius: 10px;
	padding: 10px 16px;
	color: #777;
}

.sort-select {
	position: relative;
	border: 1px solid #E6E6E6;
	border-radius: 10px;
	padding: 10px 16px;
	color: #777;
}

.select-open-menu {
	align-items: center;
	width: 100%;
	gap: 4px;
	position: absolute;
	background-color: #fff;
	z-index: 52;
	top: 37px;
	left: 0;
	border: 1px solid #E6E6E6 !important;
	border-radius: 10px;
	padding: 6px;
}

.sort-select option {
	color: #777;
}

.fake-map {
	cursor: pointer;
}

.main-page {
	gap: 10px;
}

.left-block {
	width: 281px;
}

.middle-block {
	width: 381px;
}

.right-block {
	width: 483px;
}

.main {
	position: relative;
}

input,
select {
	padding-left: 5px !important;
	width: 232px;
}

input:focus,
select:focus {
	overflow: hidden;
	outline: none;
}

.rel input,
.rel select {
	color: #000 !important;
	padding: 5px 0 5px 12px !important;
}

::-webkit-input-placeholder { 
    color:#000;
}

.rel select {
	height: 100% !important;
	appearance: none !important;
}

h1 {
	font-weight: 700;
}

.title {
	background-color: #F4F7FF !important;
	height: 100%;
}

.title a {
	font-weight: 500;
}

.rel {
	position: relative;
}

.data-modal-left {
	position: fixed !important;
	top: 530px;
	left: calc(50% - 350px);
	z-index: 52;
}

.data-modal-right {
	position: fixed;
	top: 530px;
	right: calc(50% - 350px);
	z-index: 52;
}

.calendar-right {
	position: absolute;
	top: 10px;
	right: 10px;
}

.calendar-left {
	position: absolute;
	top: 10px;
	right: 10px;
}

.person-select {
	position: absolute;
	top: 8px;
	right: 22px;
	cursor: pointer;
}

.cenel-text {
	position: absolute;
	top: 10px;
	right: 10px;
	cursor: pointer;
}

.rel input,
.rel select {
	border: 1px solid #E6E6E6;
	border-top: none;
	border-bottom: none;
	padding-right: 35px !important;
}

.date-inp1 {
	border-left: none;
	border-right: none;
}

.date-inp2 {
	border-right: none;
}

.inputs-block {
	justify-content: start;
	width: fit-content;
	border: 1px solid #E6E6E6;
	border-radius: 10px;
	overflow: hidden;
}

form {
	background-color: #F4F7FF !important;
	border: 1px solid #E6E6E6;
	border-radius: 8px;
	padding: 16px 10px;
}

.find-btn {
	display: flex;
	justify-content: center;
	align-items: center;
	background-color: #55246A;
	color: #fff;
	font-size: 16px;
	border-radius: 7px;
	height: 36px;
	padding: 0 16px;
	width: 20%;
}
</style>