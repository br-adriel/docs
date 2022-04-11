# Orientação à Objetos

11/04/2022 - Organização Sistemas e Métodos

Resultado do exercício passado em sala para fixar conceitos vistos em aula

## Conceitos

### Orientação a objetos

É um paradigma de desenvolvimento de sistemas que fornece mecanismos poderosos
para melhor resolver problemas do mundo real no mundo computacional.

Nesse paradigma todos os entes de um sistema são vistos como um objeto que possui
características e pode executar ações.

### Abstração

É a construção de um modelo para representar algo do mundo real, o processo de
passar um objeto do mundo real para o mundo computacional.

### Objeto

É qualquer coisa do mundo real que pode ser abstraído para o mundo computacional,
no qual o objeto será composto por atributos e métodos.

### Classe

É o agrupamento de objetos computacionais que possuem características em comum,
dessa forma as classes atuam como um molde para a criação de novos objetos.

### Método

É alguma ação que o objeto pode desempenhar, essa ação geralmente atua sobre seus
atributos e pode ou não alterá-los.

### Atributo

É uma característica de determinado objeto, seu estado.

### Sobrecarga de métodos

Ocorre quando dois ou mais métodos de uma mesma classe possuem o mesmo nome, mas
os atributos passados para cada um são diferentes.

Geralmente a própria linguagem de programação determina qual deve ser executado
de acordo com os atributos passados em sua chamada de execução.

### Encapsulamento

Ocorre quando os atributos de um objeto/classe são ocultados dos demais objetos/classes,
de forma que se torna impossível acessá-los diretamente, mas são providos métodos para
que seja possivel a interação e modificação desses dados de forma indireta.

### Herança

Ocorre quando um classe reaproveita os atributos e/ou métodos de uma outra classe,
contribuindo assim com uma menor repetição de código.

### Polimorfismo

Ocorre quando uma classe implementa um método com o mesmo nome de um método herdado,
dessa forma o sobrescrevendo.

### Agregação

Ocorre quando há uma associação forte entre objetos de forma que uma classe/objeto
possui uma outra class/objeto como um de seus atributos.

## Modificadores de acesso

Os modificadores de acesso são os responsáveis por determinar se os elementos de uma
classe, e consequentemente seus objetos, serão acessiveís por outras classes.

Há três deles: Público, Privado e Protegido.

### Público

Os atributos e métodos definidos como público podem ser acessados pela própria
classe e por qualquer outra.

Normalmente esse modificador é evitado nos atributos das classes para que eles não
possam ser acessados diretamente e assim seja possível a aplicação do encapsulamento.

Esse modificador é representado pelo símbolo `+`.

### Privado

Os atributos e métodos definidos como privado podem ser acessados apenas pela própria
classe, nem mesmo às classes "filhas" conseguem acessar o que é posto como privado.

Normalmente esse modificador é adotado nos atributos das classes mas evitado nos métodos.

Esse modificador é representado pelo símbolo `-`.

### Protegido

Similar ao modificador privado, os atributos e métodos definidos como protegido podem
ser acessados apenas pela própria classe e por suas filhas, isto é, pelas classes que
herdam dela.

Esse modificador é representado pelo símbolo `#`.

A seguir há uma tabela resumindo o comportamento dos três modificadores.

| Modificador | Representação | Pŕopria classe | Herdeiras        | Outras classes   |
| ----------- | ------------- | -------------- | ---------------- | ---------------- |
| Público     | +             | Pode acessar   | Pode acessar     | Pode acessar     |
| Privado     | -             | Pode acessar   | Não pode acessar | Não pode acessar |
| Protegido   | #             | Pode acessar   | Pode acessar     | Não pode acessar |

## Sobrecarga vs Polimorfismo

Apesar de ambos tratarem de métodos que possuem o mesmo nome, sobrecarga e polimorfismo
não são a mesma coisa.

A sobrecarga trata de métodos com o mesmo nome que estão em uma mesma classe.

Entretanto,apesar do nome ser o mesmo, os atributos passados para cada um são diferentes,
que é como a linguagem diferencia os dois e decide qual executar quando é solicitado.

Isso permite a execução de diferentes implementações que servem para o mesmo propósito de
acordo com a entrada passada.

Já o polimorfismo trata da redeclaração de métodos já existentes na classe pai, de forma a
completamente sobrescrevê-lo.

### Exemplo

Por exemplo, imaginemos um cenário onde tempos uma classe `SerVivo` com o método `falar`.

Quando `falar` é executado, é exibida a mensagem `"faz barulhos"`.

Agora imaginemos que tenhamos uma outra classe chamada `Humano` que herda da classe
`SerVivo`.

Se apenas herdamos da classe e não fizermos mais nada, ao executar o método `falar` em
`Humano` ele também exibirá `"faz barulhos"`.

Isso não é tão interessante, podemos então sobrescrever esse método para que quando `falar`
seja executado em humano, seja exibida a mensagem `"Olá"`.

Para sobrescrever esse método, basta criar um método com o memso nome na classe `Humano`,
ou seja, `Humano` ganha um novo método chamado `falar` que sobrescreve o método vindo de
`SerVivo` apenas nessa classe. Isso é Polimorfismo.

Agora imagine que queiramos passar um nome para que `Humano` cumprimente ao falar, mas ao
mesmo tempo queremos que quando não passarmos nenhum nome, ele continue exibindo apenas
`"Olá"`.

Para fazer isso podemos implementar mais um método com o memso nome `falar`, mas dessa
vez recebendo o argumento `nome`, ou seja, agora temos dois métodos: `falar()` e `falar(nome)`.

Quando chamamos `falar()` a primeira implementração é executada, quando chamamos 
`falar(fulano)` a segunda implementação é chamada. Os dois existem ao mesmo tempo
e o sistema é quem determina qual será executado com base nos argumentos passados
em sua chamada. Isso é Sobrecarga.
