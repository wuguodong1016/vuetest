<template>
	<div class="app">
		<h1>{{title}}</h1>
		<input v-model="newItem" v-on:keyup.enter="addNewItem(newItem)" />
		<ul>
			<li v-for="item in items" v-bind:class="{infinshed:item.isfinshed}" v-on:click="toggleFinshed(item)">
				{{item.val}}
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				title: "这是一个小测试",
				items: [
				],
				newItem:''
			}
		},
		methods: {
			toggleFinshed: function(item) {
				item.isfinshed = !item.isfinshed;
			},
			addNewItem: function (newItem){
				this.items.push({
					val: newItem,
					isfinshed: false
				});
				this.newItem = ''
			}
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
	
	.infinshed {
		color: red;
	}
	body {
		display:flex;
		align-items: center;
		justify-content: center;
		height: 100%;
	}
</style>