<script>
	import { Button, Col, Row } from '@sveltestrap/sveltestrap';
	export let id, name;
</script>

<Col xs="4" sm="4">
	<div class="list-item">
		<h1>{id}</h1>
		<h1>{name}</h1>
	</div>
</Col>

<style>
	.list-item {
		width: 200px;
		height: 200px;
		background-color: gray;
		/* margin: 10px; */
		display: flex;
		/* flex-direction: column; */
		justify-content: center;
		align-items: center;
	}
</style>
