<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <title>calculadora </title>
</head>
<body>
<style>
    
</style>
</style>
</head>
<body>
<center>

<form name="f1"><br>
<input type="text" name="txtcaja1" id="#response">
<br>
<input type="text" name="txtcaja2" value="" id="#response">
<br>
<input type="button" class="btn btn-info"class="arit" onClick="arit('%')" value="%">
<input type="button" class="btn btn-info"onClick="raiz()" value="√">
<input type="button" class="btn btn-info"onClick="raiz()3"value="3√">
<input type="button" class="btn btn-info"class="arit" onClick="arit('¹/×')" value="¹/×">
<br>
<input type="button" class="btn btn-info"class="clear" onClick="document.f1.txtcaja2.value='0'" value="CE">
<input type="button" class="btn btn-info"class="clear" onClick="document.f1.reset(); blocdel = false;" value="C">
<input type="button" class="btn btn-info"class="clear" onClick="deletecarac()" value="◄">
 
<input type="button"class="btn btn-info" class="arit" onClick="arit('/')" value="÷">
<br>
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="7">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="8">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="9">
<input type="button" class="btn btn-info"class="arit" onClick="arit('*')" value="×">
<br>
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="4">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="5">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="6">
<input type="button" class="btn btn-info"class="arit" onClick="arit('-')" value="-">
<br>
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="1">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="2">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="3">
<input type="button" class="btn btn-info"class="arit" onClick="arit('+')" value="+">
<br>
<input type="button" class="btn btn-info"class="arit" onClick="masmenos()" value="±">
<input type="button" class="btn btn-info"onclick="escribir(this.value)" value="0">
<input type="button" class="btn btn-info"onClick="escribir('.')" value=".">
<input type="button" class="btn btn-info"class="igual" onClick="calcular()" value="=">
<br>
</form>
</center>
<script type="text/javascript" id="#response">
    var borrar = false;
    function deletecarac(){
        var caja2 = document.f1.txtcaja2.value;
            if (caja2 == "" || caja2 == "0" || caja2.length == 1 && blocdel!=true){
                document.f1.txtcaja2.value = "0";
            }
            else if(blocdel!=true){
                var res = caja2.substring(0,caja2.length-1);
                document.f1.txtcaja2.value = res;

   function escribir(n){
        var caja2 = document.f1.txtcaja2.value;
        if (borrar) {
            //alert("se borro");
            document.f1.txtcaja2.value="";
            borrar = false;
            document.f1.txtcaja2.value = n;
        }
        else if (caja2 == "0" && n != "."){
            cajao = caja2.replace("0", "")
            document.f1.txtcaja2.value = cajao + n;
        }
        else{
            document.f1.txtcaja2.value = caja2 + n;
        }
    }
    function raiz(){
        var caja1 = document.f1.txtcaja1.value;
        var caja2 = document.f1.txtcaja2.value;
        document.f1.txtcaja1.value = "Math.sqrt("+ caja2 + caja1 +")";
        document.f1.txtcaja2.value = "";
   
    }
    function arit(o){
        var caja1 = document.f1.txtcaja1.value;
        var caja2 = document.f1.txtcaja2.value;
        var unum = caja1.substring(caja1.length-1);
        calcular()
        if (unum == "+" || unum == "-" || unum=="*" || unum=="/") {
            unum = unum.replace(unum,o);
            var res = caja1.substring(0,caja1.length-1);
            document.f1.txtcaja1.value = res+unum;
        }
        if (caja1 == "" && caja2 != ""){
            document.f1.txtcaja1.value = caja2 + o;
        }
        else{
            document.f1.txtcaja1.value = caja1 + caja2 + o;
        }
        borrar = true;
    }
    function calcular(){
        var caja1 = document.f1.txtcaja1.value;
        var caja2 = document.f1.txtcaja2.value;
        document.f1.txtcaja2.value = eval(caja1 + caja2);
        document.f1.txtcaja1.value = "";
        borrar = true;
        blocdel = true;
    }
    function masmenos(){
        var caja2 = document.f1.txtcaja2.value;
        if (caja2 > 0){
            document.f1.txtcaja2.value = "(-" + caja2 + ")";
        }
        else{
            cajaplus = caja2.replace(/[-|(|)]/g, "");
            document.f1.txtcaja2.value = cajaplus;
        }
    }
</script>
<script src="js/jquery.js" ></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4./js/bootstrap.js" ></script>
<script src="js/app.js" ></script>
</body>
</html>
