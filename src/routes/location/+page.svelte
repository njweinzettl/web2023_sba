<script>
    import { page } from '$app/stores';

    let location = '';

    //fetch location id
    fetch('https://rickandmortyapi.com/api/location')
    .then(res => res.json())
    .then(data => {
        console.log(data);
        location = data.results.id;
    })
    
    const location_id = $page.url.searchParams.get('id');
    console.log(location_id);

    let name;
    let type;
    let dimension;
    let residents = 0;

</script>

<div>
    <h1>{ name }</h1>
    <h3>{ type } | { dimension }</h3>
    <h5>{ residents } residents</h5>
</div>