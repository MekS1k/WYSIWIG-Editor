<template>
	<div class="main" contenteditable="true" ref="editableArea">
		<div class="buttons">
			<button @click="undoChange" :disabled="!canUndo"><img src="/src/assets/img/Group 1.png" alt="" /></button>
			<button><img src="/src/assets/img/Group 2.png" alt="" /></button>
			<button @click="makeHeading"><img src="/src/assets/img/Group 3.png" alt="" /></button>
			<button><img src="/src/assets/img/Group 4.png" alt="" /></button>
			<button @click="makeParagraph"><img src="/src/assets/img/Group 5.png" alt="" /></button>
			<button @click="getHtml" class="coppy-button">Скопировать HTML</button>
		</div>

		<p>
			Таким образом консультация с широким активом представляет собой интересный эксперимент проверки позиций, занимаемых участниками в отношении
			поставленных задач. С другой стороны постоянное информационно-пропагандистское обеспечение нашей деятельности представляет собой интересный
			эксперимент проверки форм развития. Идейные соображения высшего порядка, а также укрепление и развитие структуры влечет за собой процесс
			внедрения и модернизации соответствующий условий активизации. Задача организации, в особенности же реализация намеченных плановых заданий играет
			важную роль в формировании дальнейших направлений развития. Повседневная практика показывает, что постоянное информационно-пропагандистское
			обеспечение нашей деятельности играет важную роль в формировании существенных финансовых и административных условий.
		</p>
		<h1>Смотрите какие обезьянки</h1>
		<img src="/src/assets/img/image 1.png" alt="" />

		<p>
			Таким образом консультация с широким активом представляет собой интересный эксперимент проверки позиций, занимаемых участниками в отношении
			поставленных задач. С другой стороны постоянное информационно-пропагандистское обеспечение нашей деятельности представляет собой инйцу шо шщйоц
			ущойц ущошцщйуо йцщуо йщцоу щйоу шщйцош ущйтересный эксперимент проверки форм развития. Идейные соображения высшего порядка, а также укрепление
			и развитие структуры влечет за собой процесс внедрения и модернизации соответствующий условий активизации. Задача организации, в особенности же
			реализация намеченных плановых заданий играет важную роль в формировании дальнейших направлений развития. Повседневная практика показывает, что
			постоянное информационно-пропагандистское обеспечение нашей деятельности играет важную роль в формировании существенных финансовых и
			административных условий. Товарищи! новая модель организационной деятельности требуют от нас анализа направлений прогрессивного развития. Задача
			организации, в особенности же постоянный количественный рост и сфера нашей активности требуют от нас анализа позиций, занимаемых участниками в
			отношении поставленных задач. Задача организации, в особенности же реализация намеченных плановых заданий требуют от нас анализа системы
			обучения кадров, соответствует насущным потребностям.
		</p>
	</div>
</template>

<script>
export default {
	data() {
    html:""
  },
	computed: {},
	methods: {
		// Метод для превращения выделенного текста в заголовок
		makeHeading() {
			const selection = window.getSelection();
			const editableArea = this.$refs.editableArea;

			if (selection.rangeCount > 0 && editableArea) {
				const range = selection.getRangeAt(0);
				const selectedText = range.extractContents(); // Извлечь выделенный текст
				const heading = document.createElement("h1"); // Создать тег <h1>
				heading.appendChild(selectedText); // Поместить текст в <h1>
				range.insertNode(heading); // Вставить заголовок на место выделенного текста
			}
		},
		makeParagraph() {
			const selection = window.getSelection();
			const editableArea = this.$refs.editableArea;

			if (selection.rangeCount > 0 && editableArea) {
				const range = selection.getRangeAt(0);
				const selectedText = range.extractContents(); // Извлечь выделенный текст
				const Paragraph = document.createElement("p"); // Создать тег <p>
				Paragraph.appendChild(selectedText); // Поместить текст в <p>
				range.insertNode(Paragraph); // Вставить параграф на место выделенного текста
			}
		},
		getHtml() {
			this.html = document.documentElement.outerHTML;

			navigator.clipboard.writeText(this.html)
		},
	},
	mounted() {},
};
</script>

<style scoped>
.main {
	margin-left: 107px;
	max-width: 600px;
	padding: 20px;
}
p,
h1 {
	color: #eaeaea;
}
button {
	background: none;
	border: none;
}
.coppy-button {
	color: #639eff;
}
.buttons {
	display: flex;
}
</style>
