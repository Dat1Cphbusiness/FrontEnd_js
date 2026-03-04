<script>
    const form = document.querySelector("form");
    form.addEventListener('input',onInput );
    console.log(form);
    function onInput(e){
        console.log(e.currentTarget);
        const to = form.querySelector('#to');
        const from = form.querySelector('#from');
        if(to.value === from.value){
alert("til og fra by kan ikke være det samme ");
        }
    }
</script>