<script>
    import Prism from 'prismjs';

    let parentRadius = 64;
    let parentPadding = 40;
    $: childRadius = parentRadius - parentPadding;

    let codeSample = `
.parent {
    border-radius: ${parentRadius}px;
    padding: ${parentPadding}px;
}
    
.child {
    border-radius: ${parentRadius - parentPadding}px;
}`;
</script>

<svelte:head>
	<title>Roundness Calculator</title>
	<meta
		name="description"
		content="Learn how to properly round the corners of boxes within boxes."
	/>
    <link href="https://raw.githubusercontent.com/PrismJS/prism-themes/master/themes/prism-duotone-earth.css" rel="stylesheet" />
</svelte:head>

<div class="container">
    <span>💎 Tips and tricks</span>
    <h1>How to calculate <br /><b>the roundness?<b></h1>
    <p>simply substract the side distance from the larger corner radius.</p>
    <div class="ex-sq" style="border-radius: {parentRadius}px; padding: {parentPadding}px;">
        <div style="border-radius: {childRadius}px;">
            <pre class="language-css">
                <code>
                    {@html Prism.highlight(codeSample, Prism.languages['css'], 'css')}
                </code>
            </pre>
        </div>
    </div>
    <input type="number" bind:value={parentRadius} />
    <input type="number" bind:value={parentPadding} />
    <input type="number" bind:value={childRadius} />

    <!-- <blockquote class="twitter-tweet"><p lang="en" dir="ltr">🔥 It&#39;s one of those little things that I find extremely annoying in UI.<br>Learn how to properly round the corners of boxes within boxes.<br><br>A thread 👇 <a href="https://t.co/3MjBxGZG0q">pic.twitter.com/3MjBxGZG0q</a></p>&mdash; Michal Malewicz (@michalmalewicz) <a href="https://twitter.com/michalmalewicz/status/1587038731629797376?ref_src=twsrc%5Etfw">October 31, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>  -->
</div>

<style>
    .container {
        padding: 5rem;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .ex-sq {
        background: white;
        height: 250px;
        width: 250px;
        display: flex;
        filter: drop-shadow(0 10px 0.75rem #cddde2);
        filter: drop-shadow(0 10px 0.75rem #e6f2fe); /* bg */
        filter: drop-shadow(0 10px 0.75rem #dbe2ea);
    }

    .ex-sq div {
        background: #47ca6c;
        width: 100%;
    }

    .ex-sq div pre {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        margin: 0;
        padding: 0;
    }
</style>