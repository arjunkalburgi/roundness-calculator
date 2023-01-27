<div class="container">
    <div class="content">
        <span>💎 Tips and tricks</span>
        <h1>How to calculate <br /><b>the roundness?<b></h1>
        <div class="ex-sq">
            <div>
                <p>Parent radius: 64px</p>
                <p>Padding between: 40px</p>
                <p>Child radius: 64px - 40px = 24px</p>
            </div>
        </div>
    </div>
</div>

<style>
    .container {
        padding: 5rem;
        display: flex;
        justify-content: center;
    }

    div.content {
        text-align: center;
        display: inline-block;
    }

    .ex-sq {
        background: white;
        border-radius: 64px;
        padding: 40px;
        height: 300px;
        width: 300px;
        display: flex;
        filter: drop-shadow(0 10px 0.75rem #cddde2);
        filter: drop-shadow(0 10px 0.75rem #e6f2fe); /* bg */
        filter: drop-shadow(0 10px 0.75rem #dbe2ea);
    }

    .ex-sq div {
        background: #47ca6c;
        border-radius: 24px;
        width: 100%;
    }
</style>