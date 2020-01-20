<style>
	:global(html){
		font-family: system-ui, Calibri, Arial, Helvetica, sans-serif;
	}

	:global(body){
		margin: 0;
	}

	select{
		font: inherit;
		padding: 0.5em;
		justify-self: center;
	}

	code{
		flex: none;
		justify-self: flex-start;
		background: #f6f8fa;
		margin: 2em auto 2em 0;
		padding: 0.75em;
		border-radius: 4px;
	}

	.main{
		--size: 5em;
		display: flex;
		flex-direction: column;
		width: 600px;
		margin: 0 auto;
	}


	.row{
		display: flex;
		flex-direction: row;
	}

	.row-reverse{
		display: flex;
		flex-direction: row-reverse;
	}

	.col{
		display: flex;
		flex-direction: column;
	}

	.col-reverse{
		display: flex;
		flex-direction: column-reverse;
	}

	.wrap{
		background: yellow;
		box-shadow: rgba(0,0,0,0.25) 0 1px 2px 0;
	}

	.fixh{
		height: 460px;
	}

	.x {
		display: flex;
		flex-direction: column;
	}

	.y{
		display: flex;
		flex-direction: row;
	}

	.list{
		display: flex;
		align-items: center;
	}

	.box{
		width: var(--size);
		height: var(--size);
		margin: 1em;
		background: red;
		border-radius: 0.2em;
		flex: none;
	}
</style>

<script>
	import * as trans from "../package/index";
	import Infinite from "./Infinite.svelte";

	let name = "slideRight";
	$: current = trans[name];
</script>

<main class="main">

	<h1>Svelte layout aware transitions</h1>

	<code>npm i svelte-layout-aware-transitions</code>

	<select bind:value={name}>
		<option>slideRight</option>
		<option>flyRight</option>
		<option>slideLeft</option>
		<option>flyLeft</option>
		<option>slideDown</option>
		<option>flyDown</option>
		<option>slideUp</option>
		<option>flyUp</option>
	</select>

	<code>
		import {"{"} { name } {"}"} from "svelte-layout-aware-transitions";
	</code>

	{#if name === "slideRight"}
		<div class="list row">
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>
	
	{:else if name === "flyRight"}
		<div class="list row">
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>

	{:else if name === "slideLeft"}
		<div class="list row-reverse">
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>

	{:else if name === "flyLeft"}
		<div class="list row-reverse">
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>

	{:else if name === "slideDown"}
		<div class="list col fixh">
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>

	{:else if name === "flyDown"}
		<div class="list col fixh">
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>

	{:else if name === "slideUp"}
		<div class="list col-reverse fixh">
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>

	{:else if name === "flyUp"}
		<div class="list col-reverse fixh">
			<div class="wrap row">
				<div class="box"></div>
				<div class="box"></div>
			</div>
			<Infinite transition={current} opts={{duration: 2000}}/>
			<div class="wrap col">
				<div class="box"></div>
				<div class="box"></div>
			</div>
		</div>
	
	{/if}

</main>