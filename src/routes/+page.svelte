<script>
    let outerRadius = 64;
    let outerPadding = 40;
    $: innerRadius = outerRadius - outerPadding;
</script>

<svelte:head>
	<title>Roundness Calculator</title>
	<meta
		name="description"
		content="Learn how to properly round the corners of boxes within boxes."
	/>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/prism-themes/1.9.0/prism-atom-dark.min.css" rel="stylesheet" />
</svelte:head>

<div class="container">
    <span>💎 Tips and tricks</span>
    <h1>How to calculate <br /><b>the roundness?<b></h1>
    <p>simply substract the side distance from the larger corner radius.</p>
    <div class="ex-sq" style="border-radius: {outerRadius}px; padding: {outerPadding}px;">
        <pre class="language-css"  style="border-radius: {innerRadius}px;">
            <code>
<span class="token selector">.outer</span> <span class="token punctuation">{`{`}</span>
    <span class="token property">border-radius</span><span class="token punctuation">:</span> {outerRadius}px<span class="token punctuation">;</span>
    <span class="token property">padding</span><span class="token punctuation">:</span> {outerPadding}px<span class="token punctuation">;</span>
<span class="token punctuation">{'}'}</span>
    
<span class="token selector">.inner</span> <span class="token punctuation">{'{'}</span>
    <span class="token property">border-radius</span><span class="token punctuation">:</span> {innerRadius}px<span class="token punctuation">;</span>
<span class="token punctuation">{'}'}</span>
            </code>
        </pre>
    </div>
    <div class="parent-controls">
        <label>
            <span>outer radius</span>
            <input type="number" bind:value={outerRadius} />
        </label>
        <label>
            <span>outer padding</span>
            <input type="number" bind:value={outerPadding} />
        </label>
    </div>
    <label>
        <span>inner radius</span>
        <input type="number" bind:value={innerRadius} />
    </label>

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
        margin: 40px 0;
        filter: drop-shadow(0 10px 0.75rem #cddde2);
        filter: drop-shadow(0 10px 0.75rem #e6f2fe); /* bg */
        filter: drop-shadow(0 10px 0.75rem #dbe2ea);
    }

    .ex-sq pre {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        margin: 0;
        padding: 0;
        font-size: 13px;
    }

    .parent-controls {
        display: flex;
        gap: 30px;
    }

    label {
        display: flex;
        flex-direction: column;
        margin: 10px;
    }

    input {
        border-color: white;
        border-style: solid;
        text-align: right;
        filter: drop-shadow(0 10px 0.75rem #dbe2ea);
    }
</style>