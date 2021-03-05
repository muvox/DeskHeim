<script>
    export let data
</script>

<div>				
	<div class="panelHeaderWrapper">
		<h3 class="panelHeader">Players</h3>
		<span class="iconify" data-icon="clarity:group-solid" data-inline="false" style="margin-right: 10px; font-size: 30px; color: white;"></span>
	</div>
	<div class="panelWrapper">
		<div class="itemWrapper">
			<p> Players online: </p>
			<p>{data['gdetails']['raw']['numplayers']}</p>
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
		height: 100%
	}
	.itemWrapper{
		width: 100%;
		display: flex;
		flex-direction: row; 
		justify-content: space-between;
	}
	h3 {
		margin-top: 0px;
		margin-bottom: 0px;
		color: #eeeeed;
	}
</style>