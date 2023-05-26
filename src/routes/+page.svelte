<script>

    let formSubmit = {
        username : "",
        password : "",
    }

    const submitForm = async (event) => {
        let personDetails = formSubmit
        event.target.reset()
        
        $: formSubmit = {
            username : '',
            password : '',
        };

        const response = await fetch("http://localhost:3000/",{
            method: 'POST',
            body: JSON.stringify(personDetails),
            headers: {
                'content-type' : 'application/json'
            }
        })
        const res = await response.json()
        console.log(res)
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
                <input id="username" type="password" class="mb-2" placeholder="Password" bind:value={formSubmit.password}/>
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