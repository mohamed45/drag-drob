<script>
	import { Button, Col, Row } from '@sveltestrap/sveltestrap';
	export let value, name;
</script>

<Col xs="4" sm="4">
	<div class="list-item">
		<h1>{value}</h1>
		<h1>{name}</h1>
	</div>
</Col>

<style>
	.list-item {
		width: 100%;
		height: 300px;
		background-color: gray;
		margin: 10px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
</style>
