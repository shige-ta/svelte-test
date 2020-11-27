 <script>
	let datas = []
	const url = "楽天API";
	async function getfetch(){
		const response = await fetch(url);
		const data = await response.json();
		console.log(data.Items[0].Item);
		datas = data.Items
}
</script>
  
<button on:click={getfetch}>
	取得
</button>	
{#each datas as d,i}
<div class="card mb-3" style="max-width: 540px">
    <div class="row no-gutters">
        <div class="col-md-4 my-auto">
            <img class="card-img" src={d.Item.smallImageUrl} >
        </div>
        <div class="col-md-8">
            <div class="card-body">
                <h5 class="card-title">第{i+1}位</h5>
                <p>{d.Item.title}</p>
                <a class="btn btn-primary" href="#">詳細</a>
            </div>
        </div>
    </div>
</div>
{/each}

