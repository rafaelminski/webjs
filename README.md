# webjs
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <label for="myBrowser">Escolha um navegador</label>
    <input list="browser" id="myBrowser" name="myBrowser"> 
    <datalist></datalist>
</body>
</html>
<script>
    const bairro = prompt("Bairro de entrega")
    let taxaEntrega;

    switch(bairro){
        case "centro" :
            taxaEntrega = 5.00;
            break
        case "pacaembu": 
            taxaEntrega = 8.00;
            break
        case "floresta": 
            taxaEntrega = 10.00;
            break
        default : 
            taxaEntrega = 15.00    
    }

    alert(`A taxa de entrega do  ${bairro} é ${taxaEntrega.toFixed(2)}`)
</script>

// criar referencia aos elementos da página
const frm = document.querySelector("form");
const resp = document.querySelector("h3");


//criar um ouvinte para o evento submit
frm.addEventListener("submit", (e) => {
    e.preventDefault();

    //obter os valores dos inputs
    const nome = frm.inNome.value;
    const masculino = frm.inMasculino.checked;
    const altura = Number(frm.inAltura.value);


    let peso;

    if(masculino){
        peso = 22 * Math.pow(altura,2);
    }else {
        peso = 21 * Math.pow(altura,2);

    }

   // operador ternario : const peso = masculino ? 22 * Math.pow(altura, 2) : 21 * Math.pow(altura, 2)

    resp.innerText = ` ${nome}: Seu peso ideal é ${peso} kg.` 
})

frm.addEventListener("reset" , () =>{
    resp.innerText = "";
})
