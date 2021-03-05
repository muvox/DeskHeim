<script>
    export let data
</script>

<div>
    <div class="panelHeaderWrapper">
        <h3 class="panelHeader">Server</h3>
        <span class="iconify" data-icon="clarity:rack-server-line" data-inline="false" style="margin-right: 10px; font-size: 30px; color: white;"></span>
    </div>
    <div class="panelWrapper">
        <div class="itemWrapper">
            <p>Server status: </p>
            <div style="display: flex; flex-direction:row">
                <p style="margin: 0;">{data['Status']}</p>
                {#if data['Status'] = "ONLINE"}
                <span class="greenDot"></span>
                {:else}
                <span class="redDot"></span>
                {/if}
            </div>
        </div>
        <div class="itemWrapper">
            <p>Distro: </p>
            <p> {data['Distro']}</p>
        </div>
        <div class="itemWrapper">

            <p>Uptime: </p>
            <p>{data['Uptime']}</p>
        </div>
        <div class="itemWrapper">
            <p>LinuxGSM version: </p>
            <p>{data['LinuxGSM version']}</p>
        </div>


    </div>
</div>

<style>
    .panelHeaderWrapper{
		display: flex;
		flex-direction: row; 
		justify-content: space-between;
		align-items: center;
		width: 100%;
		background-color: #606F89;
		overflow:hidden;
		padding-top: 10px;
		padding-bottom: 10px;
		border-radius: 4px 4px 0px 0px;
	}
	.panelHeader{
		margin-left: 10px;
		margin-right: 10px;
		color: #eeeeed;
	}
	.panelWrapper{
		display: flex; 
		flex-direction: column;
		align-items: start; 
		padding: 15px;
	}
	.itemWrapper{
		width: 100%;
		display: flex;
		flex-direction: row; 
		justify-content: space-between;
	}
	.greenDot{
		height: 20px;
		width: 20px;
		background-color: rgb(0, 255, 64);
		border-radius: 50%;
		display: inline-block;
		margin-left: 5px;
	}
	.redDot{
		height: 25px;
		width: 25px;
		background-color: rgb(211, 0, 0);
		border-radius: 50%;
		display: inline-block;
		margin-left: 5px;
	}
	h3 {
		margin-top: 0px;
		margin-bottom: 0px;
		color: #eeeeed;
	}
</style>