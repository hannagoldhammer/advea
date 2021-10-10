<script>

    let totalAmount = '';
    $: vatOfTotalAmout = totalAmount * 0.2;

</script>

<style lang="scss">
    .form-wrapper{
        width: 100%;
        form{
            flex-direction: column;
            justify-content: center;
            display: flex;

            @media (min-width: 700px) {
                display: grid;
                grid-template-columns: repeat(2, 2fr);
                grid-auto-columns: auto;
                grid-gap: 10px;
		    }

            .title{
                background-color: black;
                color: white;
                padding: 10px;
                font-weight: 400;
                font-size: large;
                
            }

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
                input::-webkit-outer-spin-button,
                input::-webkit-inner-spin-button {
                -webkit-appearance: none;
                margin: 0;
                }
            }

            .summary{
                text-align: right;
            }
        }

        .button-wrapper{
            display: flex;
            justify-content: center;
        }

        .send-user-data-button{
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
        
        .send-user-data-button:hover{
            cursor: pointer;
            background-color: rgb(255, 195, 121);

            @media (min-width: 1000px) {
                transform: scale(1.1);
    	    }
        }
    }
</style>

<div class="form-wrapper">
    <form action="">
        <div>
            <h2 class="title" >Kunduppgifter</h2>
            <div class="customer-data">
                <label>Personnummer</label>
                <input type="text" placeholder="ÅÅÅÅMMDDXXXX">
                <label>E-post</label>
                <input type="text" placeholder="kund@mail.se">
                <label>Mobilnummer</label>
                <input type="text" placeholder="070-xxxxxxx">
            </div>
        </div>
        <div>
            <h2 class="title">Beställning</h2>
            <div class="customer-data">
                <label>Beställnings beskrivning</label>
                <input type="text" placeholder="ex. Samsung packet">
                <label>Total pris</label>
                <input type="number" bind:value={totalAmount} placeholder="0 SEK" on:change={(e) => e.preventDefault}>
                <div class="summary">
                    <p>Moms: {vatOfTotalAmout} SEK</p>
                </div>
            </div>
        </div>
        <!-- <div>
            <h2 class="title">Välj betalningssätt</h2>
            <div>
                <p>Delbetalning</p>
            </div>
            <div>
                <p>Kontokredit</p>
            </div>
        </div> -->
        <div class="button-wrapper">
            <button class="send-user-data-button">Skicka</button>
        </div>
    </form>
</div>