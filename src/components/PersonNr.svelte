<script>

    
    let userPeronNumber = '';
    const getUserData = () => {
        console.log("Clicked");
        fetch('https://api.paynova.com/addresses/SE/198901157993', {
        mode: 'no-cors',
        credentials: 'include',
        method: 'GET',
    })
            .then(data => {
                console.log(data)
                // return data.json();
            })
            // .then(post => {
            // console.log(post.title);
            // });
            // fetch('https://api.paynova.com/addresses/SE/198901157993')
            //     .then(data => {
            //         console.log(data)
            //     })
            //     .catch(function() {

            // });
    }
    getUserData()

</script>

<style lang="scss">
    .content{
        width: 100%;

        .customer-data{
                width: 90%;
                display: flex;
                flex-direction: column;
                margin: 0 auto 20px auto;
                // border: #aeaeae 1px solid;
                padding: 14px;
                border-radius: 8px;

                label{
                    margin-bottom: 7px;
                }

                input{
                    width: 100%;
                    border-radius: 8px;
                    padding: 10px;
                }
            }

        .title{
                background-color: black;
                color: white;
                padding: 10px;
                font-weight: 400;
                font-size: large;
                margin-top: 0;
            }
        

        @media (min-width: 700px) {
           width: 50%;
	    }

        input{
            width: 300px;
        }

        .get-user-data-button{
            margin-top: 20px;
            border-radius: 28px;
            border: none;
            background-color: bisque;
            padding: 11px;
            font-weight: 500;
            width: 300px;

            @media (min-width: 1000px) {
                transition: transform .2s;
    	    }
        }
        
        .get-user-data-button:hover{
            cursor: pointer;
            background-color: rgb(255, 195, 121);

            @media (min-width: 1000px) {
                transform: scale(1.1);
    	    }
        }
    }
</style>

<div class="content">
    <h2 class="title">
        Kunduppgifter
    </h2>
    <div class="customer-data">
        <label>Personnummer</label>
        <input type="text" placeholder="ÅÅÅÅMMDDXXXX">
    </div>
    <button class="get-user-data-button" on:click={getUserData} >Hämta kunddata</button>
</div>