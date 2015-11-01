# PHP_Orientado_Objeto
DIFERENÇA ENTRE PRINT, ECHO, PRINT_R E VAR_DUMP NO PHP

Para imprimirmos um texto, variável, vetor ou código html dentro de um arquivo php, 
podemos utilizar quatro funções distintas. 


echo:

O echo é mais rápido que o print pois não retorna um valor, e também não precisa concatenar variáveis 
que podem ser separadas por vírgulas. O echo não é uma função e sim um construtor do PHP.

Exemplo:

<?php
echo $var1, $var2;
?>

print:

O print é utilizado também para impressão no PHP, é considerado uma função de impressão de valores.
 A função print retorna um valor de natureza. 
 
 Exemplo:
 
 <?php
 print $var1 . $var2;
 ?>
 
print_r:

O print_r () exibe informações sobre uma variável de uma forma que é legível por seres humanos.
 Valores da matriz serão apresentadas em um formato que mostra chaves e elementos.
 Notação similar é usado para objetos.
 
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

var_dump:

A função var_dump exibe informações estruturadas sobre as variáveis ​​/ expressões, incluindo o tipo e o valor.
 Arrays são explorados recursivamente com valores recuados para mostrar a estrutura. Ele também mostra que
 os valores de matriz e propriedades do objeto são referências.
 
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
