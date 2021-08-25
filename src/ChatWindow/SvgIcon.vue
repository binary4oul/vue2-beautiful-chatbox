<template>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		xmlns:xlink="http://www.w3.org/1999/xlink"
		version="1.1"
		:width="width"
		:height="height"
		viewBox="0 0 24 24"
	>
		<path :id="svgId" :d="svgItem.find(item => item.name === name).path" />
	</svg>
</template>

<script>
export default {
	name: 'svg-icon',
	props: {
	  name: { type: String, required: true },
    path: { type: String, required: false },
    param: { type: String, required:  false },
    width: { type: String, requird: false, default: '24' },
    height: { type: String, required: false, default: '24' },
  },

	computed: {
		svgId() {
			const param = this.param ? '-' + this.param : ''
			return `chat-icon-${this.name}${param}`
		}
	},

	data() {
		return {
			svgItem: [
				{
					name: 'search',
					path:
						'M9.5,3A6.5,6.5 0 0,1 16,9.5C16,11.11 15.41,12.59 14.44,13.73L14.71,14H15.5L20.5,19L19,20.5L14,15.5V14.71L13.73,14.44C12.59,15.41 11.11,16 9.5,16A6.5,6.5 0 0,1 3,9.5A6.5,6.5 0 0,1 9.5,3M9.5,5C7,5 5,7 5,9.5C5,12 7,14 9.5,14C12,14 14,12 14,9.5C14,7 12,5 9.5,5Z'
				},
				{
					name: 'add',
					path:
						'M17,13H13V17H11V13H7V11H11V7H13V11H17M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2Z'
				},
				{
					name: 'toggle',
					path:
						'M5,13L9,17L7.6,18.42L1.18,12L7.6,5.58L9,7L5,11H21V13H5M21,6V8H11V6H21M21,16V18H11V16H21Z'
				},

				{
					name: 'menu',
					path:
						'M12,16A2,2 0 0,1 14,18A2,2 0 0,1 12,20A2,2 0 0,1 10,18A2,2 0 0,1 12,16M12,10A2,2 0 0,1 14,12A2,2 0 0,1 12,14A2,2 0 0,1 10,12A2,2 0 0,1 12,10M12,4A2,2 0 0,1 14,6A2,2 0 0,1 12,8A2,2 0 0,1 10,6A2,2 0 0,1 12,4Z'
				},
				{
					name: 'close',
					path:
						'M12,2C17.53,2 22,6.47 22,12C22,17.53 17.53,22 12,22C6.47,22 2,17.53 2,12C2,6.47 6.47,2 12,2M15.59,7L12,10.59L8.41,7L7,8.41L10.59,12L7,15.59L8.41,17L12,13.41L15.59,17L17,15.59L13.41,12L17,8.41L15.59,7Z'
				},
				{
					name: 'file',
					path:
						'M14,17H7V15H14M17,13H7V11H17M17,9H7V7H17M19,3H5C3.89,3 3,3.89 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V5C21,3.89 20.1,3 19,3Z'
				},
				{
					name: 'paperclip',
					path:
						'M2.88604 21.7532C-0.105241 18.7621 -0.105242 13.8948 2.88604 10.9032L12.1864 1.60279C14.3231 -0.533729 17.7998 -0.533589 19.9364 1.60307C21.0048 2.67149 21.539 4.07446 21.5389 5.47799C21.5387 6.88115 21.0047 8.28486 19.9364 9.3531L11.4111 17.8782C10.7901 18.4993 9.9644 18.8414 9.08615 18.8414C8.20785 18.8414 7.3822 18.4995 6.76101 17.8783C5.47902 16.5962 5.47907 14.5101 6.76124 13.2282L12.3362 7.65313C12.7642 7.22511 13.4581 7.22511 13.8862 7.65304C14.3143 8.08101 14.3142 8.77499 13.8862 9.20305L8.31121 14.7782C7.88385 15.2055 7.88376 15.9008 8.31112 16.3282C8.51812 16.5352 8.79337 16.6492 9.0861 16.6492C9.37884 16.6492 9.65399 16.5352 9.86109 16.3282L18.3863 7.80308C19.6683 6.521 19.6685 4.43507 18.3864 3.15308C17.1044 1.8711 15.0183 1.87101 13.7362 3.15285L4.43606 12.4532C2.29931 14.59 2.29931 18.0667 4.43606 20.2032C5.47106 21.2383 6.84726 21.8084 8.31103 21.8084C9.77479 21.8084 11.151 21.2383 12.1861 20.2032L21.4866 10.903C21.9146 10.4751 22.6085 10.4751 23.0366 10.9031C23.2507 11.1171 23.3576 11.3976 23.3576 11.6781C23.3576 11.9586 23.2505 12.2391 23.0366 12.4531L13.7362 21.7532C12.2871 23.2024 10.3604 24.0004 8.31107 24.0005C6.26174 24.0005 4.33509 23.2024 2.88604 21.7532Z'
				},
				{
					name: 'close-outline',
					path:
						'M19,6.41L17.59,5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41Z'
				},
				{
					name: 'send',
					path: 'M2,21L23,12L2,3V10L17,12L2,14V21Z'
				},
				{
					name: 'emoji',
					path:
						'M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm3.5-9c.83 0 1.5-.67 1.5-1.5S16.33 8 15.5 8 14 8.67 14 9.5s.67 1.5 1.5 1.5zm-7 0c.83 0 1.5-.67 1.5-1.5S9.33 8 8.5 8 7 8.67 7 9.5 7.67 11 8.5 11zm3.5 6.5c2.33 0 4.31-1.46 5.11-3.5H6.89c.8 2.04 2.78 3.5 5.11 3.5z'
				},
				{
					name: 'document',
					path: 'M5,20H19V18H5M19,9H15V3H9V9H5L12,16L19,9Z'
				},
				{
					name: 'pencil',
					path:
						'M20.71,7.04C21.1,6.65 21.1,6 20.71,5.63L18.37,3.29C18,2.9 17.35,2.9 16.96,3.29L15.12,5.12L18.87,8.87M3,17.25V21H6.75L17.81,9.93L14.06,6.18L3,17.25Z'
				},
				{
					name: 'checkmark',
					path: 'M21,7L9,19L3.5,13.5L4.91,12.09L9,16.17L19.59,5.59L21,7Z'
				},
				{
					name: 'eye',
					path:
						'M12,9A3,3 0 0,0 9,12A3,3 0 0,0 12,15A3,3 0 0,0 15,12A3,3 0 0,0 12,9M12,17A5,5 0 0,1 7,12A5,5 0 0,1 12,7A5,5 0 0,1 17,12A5,5 0 0,1 12,17M12,4.5C7,4.5 2.73,7.61 1,12C2.73,16.39 7,19.5 12,19.5C17,19.5 21.27,16.39 23,12C21.27,7.61 17,4.5 12,4.5Z'
				},
				{
					name: 'dropdown',
					path: 'M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z'
				},
				{
					name: 'deleted',
					path:
						'M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12C4,13.85 4.63,15.55 5.68,16.91L16.91,5.68C15.55,4.63 13.85,4 12,4M12,20A8,8 0 0,0 20,12C20,10.15 19.37,8.45 18.32,7.09L7.09,18.32C8.45,19.37 10.15,20 12,20Z'
				}
			]
		}
	}
}
</script>

<style lang="scss">
#chat-icon-search {
	fill: var(--chat-icon-color-search);
}

#chat-icon-add {
	fill: var(--chat-icon-color-add);
}

#chat-icon-toggle {
	fill: var(--chat-icon-color-toggle);
}

#chat-icon-menu {
	fill: var(--chat-icon-color-menu);
}

#chat-icon-close {
	fill: var(--chat-icon-color-close);
}

#chat-icon-close-image {
	fill: var(--chat-icon-color-close-image);
}

#chat-icon-file {
	fill: var(--chat-icon-color-file);
}

#chat-icon-paperclip {
	fill: var(--common-chat-action-icon-color);
}

#chat-icon-close-outline {
	fill: var(--chat-icon-color-close-outline);
}

#chat-icon-send {
	fill: var(--chat-icon-color-send);
}

#chat-icon-send-disabled {
	fill: var(--chat-icon-color-send-disabled);
}

#chat-icon-emoji {
	fill: var(--common-chat-action-icon-color);
}

#chat-icon-emoji-reaction {
	fill: var(--chat-icon-color-emoji-reaction);
}

#chat-icon-document {
	fill: var(--chat-icon-color-document);
}

#chat-icon-pencil {
	fill: var(--chat-icon-color-pencil);
}

#chat-icon-checkmark {
	fill: var(--chat-icon-color-checkmark);
}

#chat-icon-eye {
	fill: var(--chat-icon-color-eye);
}

#chat-icon-dropdown-message {
	fill: var(--chat-icon-color-dropdown-message);
}

#chat-icon-dropdown-scroll {
	fill: var(--chat-icon-color-dropdown-scroll);
}
</style>
