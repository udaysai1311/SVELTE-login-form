<script>

    let formSubmit = {
        username : "",
        password : "",
    }

    let personDetails = []

    function submitForm(event){
        personDetails = [...personDetails,formSubmit]
        console.log(personDetails)
        event.target.reset()
        
        $: formSubmit = {
            username : '',
            password : '',
        };
    }
</script>

<div class="container">
    <div class="row">
        <div class="form-container d-flex flex-column justify-content-center align-items-center"> 
            <form on:submit|preventDefault={submitForm} class="shadow-lg p-5">
                <label for="username">USERNAME</label>
                <br />
                <input id="username" type="text" class="mb-2" placeholder="Username" bind:value={formSubmit.username}/>
                <br />
                <label for="username">PASSWORD</label>
                <br />
                <input id="username" type="text" class="mb-2" placeholder="Password" bind:value={formSubmit.password}/>
                <br />
                <button class="btn btn-primary">Submit</button>
            </form>
        </div>
    </div>
</div>

<style>
    .form-container{
        height: 100vh;
    }
</style>