<script lang="ts">
		import { flip } from 'svelte/animate';
		import { dndzone,type DndEvent } from 'svelte-dnd-action'
		import ListItem from './ListItem.svelte';
	
		const flipDuartionMs = 100;
	
		interface ListItem {
			id: number
			title: string
		}
	
		let items : ListItem[] = [
			{
				id: 1, // need to be unique
				title: "item 1",
				
			},
			{
				id: 2, // need to be unique
				title: "item 2",
				
			},
			{
				id: 3, // need to be unique
				title: "item 3",
				
			},
			{
				id: 4, // need to be unique
				title: "item 4",
				
			},
			{
				id: 5, // need to be unique
				title: "item 5",
				
			},
			{
				id: 6, // need to be unique
				title: "item 6",
				
			},
			{
				id: 7, // need to be unique
				title: "item 7",
				
			},
			{
				id: 8, // need to be unique
				title: "item 8",
				
			},
			{
				id: 9, // need to be unique
				title: "item 9",
				
			},
			{
				id: 10, // need to be unique
				title: "item 10",
				
			}
		]
	
		const handleConsider = (evt : CustomEvent<DndEvent<ListItem>>) => {
			console.log("consider");
			// evt.detail.items <--
			items = evt.detail.items;
		}
	
		const handleFinalize = (evt: CustomEvent<DndEvent<ListItem>>) => {
			console.log("finalize");
			items = evt.detail.items;
		}
	
	</script>
	
	<div>
		<section
			use:dndzone="{{ items: items, flipDurationMs: flipDuartionMs, dropTargetStyle: {} }}"
			on:consider="{handleConsider}"
			on:finalize="{handleFinalize}"
			class="container "
		>
			{#each items as item (item.id)}
				<div class="card card-hover" animate:flip="{{ duration: flipDuartionMs}}">
					<ListItem id={item.id} name={item.title} />
				</div>
			{/each}
		</section>
	</div>

	<style>
		.container {
		gap: 20px;
		background-color: white;
		flex-wrap: wrap;
		display: flex;
		flex-direction: row;
		/* justify-content: center; */
		/* align-items: center; */	
		}
	
	</style>
