<style>
	.main{
		--size: 5em;
		display: flex;
		flex-direction: column;
	
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
	import {
		slideRight,
		flyRight,
		slideLeft,
		flyLeft,
		slideDown,
		flyDown,
		slideUp,
		flyUp
	} from "../package/index";
	import Infinite from "./Infinite.svelte";
</script>

<h1>Svelte layout aware transitions</h1>

<div class="main">

	<div class="x">

		<div class="list" style="flex-direction: row">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={slideRight} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">slideRight</div>
		</div>

		<div class="list" style="flex-direction: row">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={flyRight} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">flyRight</div>
		</div>

		<div class="list" style="flex-direction: row-reverse;">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={slideLeft} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">slideLeft</div>
		</div>

		<div class="list" style="flex-direction: row-reverse;">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={flyLeft} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">flyRight</div>
		</div>
	
	</div>

	<div class="y">
		<div class="list" style="flex-direction: column;">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={slideDown} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">slideLeft</div>
		</div>

		<div class="list" style="flex-direction: column;">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={flyDown} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">flyRight</div>
		</div>

		<div class="list" style="flex-direction: column-reverse;">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={slideUp} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">slideLeft</div>
		</div>

		<div class="list" style="flex-direction: column-reverse;">
			<div class="box"></div>
			<div class="box"></div>
			<Infinite transition={flyUp} opts={{duration: 2000}}/>
			<div class="box"></div>
			<div class="label">flyRight</div>
		</div>
	</div>
</div>