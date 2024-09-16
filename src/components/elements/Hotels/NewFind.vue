<script>
import { getFormatMonth } from "@/utilities/calendar";
import { DatePicker } from "v-calendar";
export default {
	components: {DatePicker},
	data() {
		return {
			form: {
				place: ``,
				enter: null,
				outer: null,
				persons: 1,
			},
			isCalendar1: false,
		}
	},

	methods: {
		formatDate(date) {
      if (!date) return null;
      let days = ["вс", "пн", "вт", "ср", "чт", "пт", "сб"];
      let month = date.toLocaleString("ru-RU", { month: "long" });
      month = getFormatMonth(Number(date.getMonth()));
      let day = date.getDate();
      let dayWeek = days[Number(date.getDay())];
      return day + " " + month + ", " + dayWeek;
    },
	}
}
</script>

<template>
	<form class="modal-container" @submit.prevent=''>

		<div v-if='this.isCalendar1'>
			<div class="data-modal-left">
				<DatePicker v-model='form.enter'/>
			</div>
			<div class="data-modal-right">
				<DatePicker v-model='form.outer'/>
			</div>
		</div>

		<img class='close-btn cursor-pointer' @click="this.$emit('openNewFind')" src="../../../assets/images/icons/Close.svg" alt="close">
		<h4 class='text-centera'>Доступные отели в Екатеринбурге на 7-8 июня</h4>
		<div class="inputs-block d-flex flex-column py-22">
			<input v-model='form.place' type="text" placeholder='Выберите место'>
			<img @click='this.form.place = ``' class='cenel-text' src="../../../assets/images/icons/Cenel.svg">
			<div class="data-inputs d-flex">
				<input :value='this.formatDate(form.enter)' placeholder='Дата въезда'>
					<img @click='this.isCalendar1 = !this.isCalendar1' class='calendar-left cursor-pointer' src="../../../assets/images/icons/calendar.svg">
				<input :value='this.formatDate(form.outer)' placeholder='Дата выезда'>
					<img @click='this.isCalendar1 = !this.isCalendar1' class='calendar-right cursor-pointer' src="../../../assets/images/icons/calendar.svg">
			</div>
			<select v-model='form.persons'>
				<option value="1">1 гость</option>
				<option value="2">2 гостя</option>
				<option value="3">3 гостя</option>
				<option value="4">4 гостя</option>
			</select>
			<img class='person-select' src="../../../assets/images/icons/user.svg">
		</div>
		<button class="find-btn w-100"><img src="../../../assets/images/icons/searchWhite.svg" alt='52'> <span class='ml-3'>Найти</span></button>
	</form>

</template>

<style scoped>
.data-modal-left {
	position: absolute !important;
	top: 160px;
	left: -165px;
}

.data-modal-right {
	position: absolute;
	top: 160px;
	right: -165px;
}

.calendar-right {
	position: absolute;
	top: 118px;
	right: 20px;
}

.calendar-left {
	position: absolute;
	top: 118px;
	left: 154px;
}

.person-select {
	position: absolute;
	bottom: 73px;
	right: 22px;
	cursor: pointer;
}

.cenel-text {
	position: absolute;
	top: 90px;
	right: 22px;
	cursor: pointer;
}

.data-inputs input {
	width: 50%;
	border: 1px solid #E6E6E6 !important;
	padding-right: 23px;
}

.data-inputs input:nth-child(1) {
	border-left: none !important;
	border-right: none !important;
}

.data-inputs input:nth-child(2) {
	border-right: none !important;
}

.inputs-block {
	border: 1px solid #E6E6E6;
	border-radius: 10px;
	overflow: hidden;
}

.inputs-block input, .inputs-block select {
	border: none;
	outline: none;
	height: 30px !important;
	appearance: none;
	padding-left: 4px;
	padding-right: 23px;
}

.modal-container {
	position: fixed;
	z-index: 10;
	background-color: #fff;
	top: calc(60% - 245px);
	width: 350px;
	/* height: 245px; */
	padding: 16px;
	color: #000;
	border-radius: 12px;
}

.close-btn {
	position: absolute;
	top: 10px;
	right: 10px;
}

.find-btn {
	display: flex;
	justify-content: center;
	align-items: center;
	background-color: #55246A;
	color: #fff;
	font-size: 16px;
	border-radius: 7px;
	height: 40px;
	padding: 0 16px;
	margin-top: 10px;
}
</style>