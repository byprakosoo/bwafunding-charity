<script>
    import CharityList from '../components/CharityList.svelte'
    import Header from '../components/Header.svelte'
    import Welcome from '../components/Welcome.svelte'
    import Promo from '../components/Promo.svelte'
    import Footer from '../components/Footer.svelte'
    import Loader from '../components/Loader.svelte'
    
    let data = getData();

    async function getData(){
        const res = await fetch('http://localhost:3000/charities/')
        const data = await res.json();
        
        if(res.ok){
            return data
        } else{
            throw new Error(data)
        }
    }
    console.log(data)
</script>

<Header />
<Welcome />
<Promo />
{#await data}
    <Loader />
{:then charities} 
    <CharityList {charities} />
{/await}
<Footer />
