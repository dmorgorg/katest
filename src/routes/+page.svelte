<script>
	import { onMount,afterUpdate } from 'svelte';
	import '$lib/styles/styles.css';
    let katexify;

	onMount(() => {
		katexify = () => {
			renderMathInElement(document.body, {
				delimiters: [
					{
						left: '$$',
						right: '$$',
						display: true
					},
					{
						left: '!$',
						right: '!$',
						display: false
					}
				]
			});
		};
        katexify();
	});

	afterUpdate(()=>{
		katexify();
	})
</script>

Hello !$a^2=b^2+c^2!$ World

<svelte:head>


	<!-- The loading of KaTeX is deferred to speed up page rendering -->
	<script
		defer
		src="https://cdn.jsdelivr.net/npm/katex@0.16.4/dist/katex.min.js"
		integrity="sha384-PwRUT/YqbnEjkZO0zZxNqcxACrXe+j766U2amXcgMg5457rve2Y7I6ZJSm2A0mS4"
		crossorigin="anonymous"></script>

	<!-- To automatically render math in text elements, include the auto-render extension: -->
	<script
		defer
		src="https://cdn.jsdelivr.net/npm/katex@0.16.4/dist/contrib/auto-render.min.js"
		integrity="sha384-+VBxd3r6XgURycqtZ117nYw44OOcIax56Z4dCRWbxyPt0Koah1uHoK0o4+/RRE05"
		crossorigin="anonymous"
		onload="renderMathInElement(document.body);"></script>
</svelte:head>
