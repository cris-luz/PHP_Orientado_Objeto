#Dicas Rapidas

#Diferença entre PRINT, ECHO, PRINT_R e VAR_DUMP no PHP


>Para imprimirmos um texto, variável, vetor ou código html dentro de um arquivo php, 
podemos utilizar quatro funções distintas. 
>


#Echo:

>O echo é mais rápido que o print pois não retorna um valor, e também não precisa concatenar variáveis 
>que podem ser separadas por vírgulas. O echo não é uma função e sim um construtor do PHP.

Exemplo:

```php
  <?php
  
  echo $var1, $var2;
  
  ?>
```
#Print:

>O print é utilizado também para impressão no PHP, é considerado uma função de impressão de valores.
> A função print retorna um valor de natureza. 
 
 Exemplo:
 
```php 
   <?php
   
   print $var1 . $var2;
   
   ?>
```

#Print_r:

> O print_r () exibe informações sobre uma variável de uma forma que é legível por seres humanos.
  Valores da matriz serão apresentadas em um formato que mostra chaves e elementos.
> Notação similar é usado para objetos.
 
```php    
   <?php
   
   $array = array('123',123);
   
   print_r($array);
   
   ?>

Resultará em:

Array

  (
  
      [0] => 123
      
      [1] => 123
      
  )
```

#Var_dump:

> A função var_dump exibe informações estruturadas sobre as variáveis ​​/ expressões, incluindo o tipo e o valor.
> Arrays são explorados recursivamente com valores recuados para mostrar a estrutura. Ele também mostra que
> os valores de matriz e propriedades do objeto são referências.

```php   
   <?php
   
   $array = array('123',123);
   
   var_dump($array);
   
   ?>

Resultará em:

   array(2) {
   
     [0]=>
     
     string(3) "123"
     
     [1]=>
     
     int(123)
   }
```

# MVC :: Conceito Prático de Utilização

```php
<!DOCTYPE html>

      <html lang="pt-br">
      
        <head>
        
           <meta charset="UTF-8">
           
      	 <title>TecWeb PHP - MVC :: Conceito Prático de Utilização</title>
      	 
        <head>
        
        <body>
        
            <?php
      	  //CONTROLLER 
      	  require('./ _aap/Config.inc.php');
      	  
      	  //MODEL
      	  $read = new Read;
      	  $read -> ExeRead ('tw_categories');
      	  
      	  foreach ($read ->getResult () as $cat);
      	     extrect($cat);
      		 
      		 //VIEW
      		 echo "<article>"
      		 ."<header> <h1> {$category_title} </h1> </header>"
      		 ."<p> {$category_content} </p>"
      		 ."</article><hr>";
      		 //END VIEW
      	   
      	   endforeach;
      	   //END MODEL
      	   
      	   //END CONTROLLER
      	   ?>
      	   
      	</body>
      	
      </html>
 ```

#  PHP Files | Manipulação de arquivo


```php 
    <?php
        
    	header ('Content-Type:text/html; charset=utf-8');
    	
    	
    	$BaseDir = gercwd()."/05";
    	echo $BaseDir;
    	echo "<hr>";
    
    	//r = ler
    	//w = escrever
    	//a = anexar
    	
    	//criando o arquivo
    	
        $File = fopen ("{$BaseDir}/05.txt",'w');
        
    	//String para manipular
        $Txt= "Bulbasaur Lorem ipsum dolor sit amet,\r\n\consectetur adipiscing elit.\r\n\Ivysaur Lorem ipsum dolor sit amet";
    	fwrite($File, $Txt);
    	
    	// Atenção!!! Sempre feche o arquivo.
    	fclosed ($File);
    	
    	//Adicionando nova linha 
    	$Add = "\r\n\Venusaur Lorem ipsum consectetur adipiscing elit.";
    	$FileTrue = fopen ("{$BaseDir}/05.txt",'a');
    	fwrite ($FileTrue, $Add)
    	fclosed ($File);
    	
    	//loop para exibir todas linhas
    	$FileTrue = fopen ("{$BaseDir}/05.txt",'r');
    	//eof é constante de quebra linha, nesse caso vamos usar feof
    	while (!feof ($FileRead));
    	   $Dado = fgets ($FileRead);
    	   echo "{$Dado}<br>";
    	endwhile;
        fclosed ($FileRead);
    	
    	//subescrever o arquivo.
    	file_put_contents("{$BaseDir}/05.txt"," Sobrescrevendo o srquivo ");
    	
    	//pegando o arquivo e adicionado conteudo 
    	 $File = "{$BaseDir} /05.txt";
    	 $FileContent = file_get_contents ($File);	 
         file_put_contents($File,$FileContent . $Add);
    	 
    	//Fazendo o arquivo se tornar um array
        $File = file ($File);
        var_dump ($File);
        
        
         //fazendo uma copia do arquivo
        copy($File,getcwd(). '/05/teste.txt');
    	//Apagendo o  arquivo
    	unlink ($File);
    	
    	
    	
    	echo str_reapeat ("<br>".40)
?>
 ```
