# php
//Campo de senha


<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Passagem de Parâmetros via GET</title>
</head>
<body>
    <form action="gabarito_senha.php" method="post">
        <label for="senha">Digite a senha:</label>
        <input type="text" id="senha" name="senha"><br><br>
        <input type="submit" value="Enviar">
    </form>
</body>
</html>

------------------------------------------------------------------------------------------------------------------------

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adivinhando a senha</title>
</head>
<body>
<?php
    print_r($_POST);
    

if(isset($_POST['senha']))//
{
    $senha = $_POST['senha'];

   // echo '<br><br>';
    //echo 'senha: '.$senha;
  if($senha == '123') 
  {
   echo " Parabéns, você sabe a senha";   
  }else
  {
       echo "Você errou";  

       $arquivo = "senhas_enviadas.txt";

       if(!file_exists($arquivo)){
        $file = fopen($arquivo, "w");
    } else {
        $file = fopen($arquivo, "a");
    }
    
    fwrite($file, $senha."\n");
    fflush($file);
    fclose($file);



  }
}
?>
</body>
</html>
