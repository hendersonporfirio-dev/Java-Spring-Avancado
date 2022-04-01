# Método Split() - Divisão de Arrays por Partes
## O método string split() quebra uma determinada string em torno de correspondências da expressão regular fornecida. Depois de dividir em relação à expressão regular fornecida, esse método retorna uma matriz de caracteres.
## Exemplo:  
```
Input String: 016-78967
Regular Expression: - 
Output : {"016", "78967"}
```
## Duas Variantes do Método Split()
### 1. Public String [ ] split ( String regex, int limit )

#### Parâmetros:

##### regex – uma expressão regular delimitadora
##### Limit - o limite resultante
##### Return: Um array de strings é calculado dividindo a string dada.
##### Lança Exceção: PatternSyntaxException – se a sintaxe da expressão regular fornecida for inválida.  

### 2. O parâmetro limit pode ter 3 valores: 

#### a. " limit > 0 " - Se este for o caso, então o padrão será aplicado no máximo limit -1 vezes, o comprimento do array resultante não será maior que " n ", e a última entrada do array resultante conterá todas as entradas além do último padrão correspondido.
#### b. " limit < 0 " - Neste caso, o padrão será aplicado o maior número de vezes possível, e o array resultante pode ser de qualquer tamanho.
#### c. " limit = 0 " - Neste caso, o padrão será aplicado o maior número de vezes possível, o array resultante pode ser de qualquer tamanho e as strings vazias à direita serão descartadas.

## Exemplo 2:
### jerk@para@heroes -> String que vai sofrer a divisão (split).

| EXEMPLO:| Regex  |	Limit | 	Result|
| :---:|:---:  |	:---: | 	:---:|
| A |@	| 2	|{“jerk”, ”para@heroes”}|
| B |@	| 5	|{“jerk”, ”para”, ”heroes”}| 
| C |@	|-2	|{“jerk”, ”para”, ”heroes”}|
| D |s  | 	5	|{“je”, ”“, “@para@je”, “”, “”}|
| E |s  |  	-2|	{“je”, ” “, ” “, “@para@je”, “”, “”}|
| F |s  |  	0|	{“je”, ””, ”@para@je”}|

### Exmplo 3 - praticando:
#### A.
````
// Programa Java para demonstrar o funcionamento prático do split(regex, limit) com o limit baixo = 2.
public class Jerk {
	public static void main(String args[])
	{
		String str = "jerks@para@heroes";
		String[] arrOfStr = str.split("@", 2);

		for (String a : arrOfStr)
			System.out.println(a);
	}
}
````
#### Saída:
````
jerk
para@heroes
````
#### B.
````
// Programa Java para demonstrar o funcionamento prático do split(regex, limit) com o limit alto = 5.
public class Jerk {
	public static void main(String args[])
	{
		String str = "jerks@para@heroes";
		String[] arrOfStr = str.split("@", 5);

		for (String a : arrOfStr)
			System.out.println(a);
	}
}
````
#### Saída:
````
jerk
para
heroes
````
#### C.
````
// Programa Java para demonstrar o funcionamento prático do split(regex, limit) com o limit negativo = -2.
public class Jerk {
	public static void main(String args[])
	{
		String str = "jerks@para@heroes";
		String[] arrOfStr = str.split("@", -2);

		for (String a : arrOfStr)
			System.out.println(a);
	}
}
````

#### Saída:
````
jerk
para
heroes
````
#### D.
````
// Programa Java para demonstrar o funcionamento prático do split(regex com "s", limit) com o limit alto = 5.
public class Jerk {
	public static void main(String args[])
	{
		String str = "jerks@para@heroes";
		String[] arrOfStr = str.split("s", 5);

		for (String a : arrOfStr)
			System.out.println(a);
	}
}
````
#### Saída:
````
jerk
@para@heroe
````
#### E.
````
// Programa Java para demonstrar o funcionamento prático do split(regex com "s", limit) com o limit negativo = -2
public class Jerk {
	public static void main(String args[])
	{
		String str = "jerks@para@heroes";
		String[] arrOfStr = str.split("s", -2);

		for (String a : arrOfStr)
			System.out.println(a);
	}
}
````
#### Saída:
````
jerk
@para@heroe
````
