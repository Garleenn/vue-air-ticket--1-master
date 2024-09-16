<script>
export default {
	data() {
		return {
			indexNow: 0
		}
	},

	props: {
		images: Array,
		index: Number
	},

	methods: {
		slideLeft() {
			if (this.indexNow == 0) {
				this.indexNow = this.images.length - 1;
			} else {
				this.indexNow--;
			}
		},

		slideRight() {
			if (this.indexNow == this.images.length - 1) {
				this.indexNow = 0;
			} else {
				this.indexNow++;
			}
		},
	},

	mounted() {
		this.indexNow = this.index
	}
}
</script>

<template>
	<div class="modal-container">
		<img class='close-btn cursor-pointer' @click="this.$emit('closeFullImage')" src="../../../assets/images/icons/Close.svg" alt="close">
		<img @click='slideLeft' class='arrow arrow-left' src="../../../assets/images/icons/arrowLeft.svg">
		<img class='main-image' :src="images[indexNow]" alt="image">
		<img @click='slideRight' class='arrow arrow-right' src="../../../assets/images/icons/arrowLeft.svg">
	</div>
</template>

<style scoped>
@media (max-width: 1224px) {
	.modal-container {
		width: 100% !important;
		height: 25% !important;
		top: 35% !important;
		left: 0 !important;
	}

	
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

.main-image {
	width: 100%;
	height: 100%;
	object-fit: cover;
	border-radius: 12px;
}

.modal-container {
	position: fixed;
	z-index: 10;
	background-color: #fff;
	top: 5%;
	left: 5%;
	width: 90%;
	height: 90%;
	color: #000;
	border-radius: 12px;
}

.close-btn {
	position: absolute;
	top: 10px;
	right: 10px;
}
</style>