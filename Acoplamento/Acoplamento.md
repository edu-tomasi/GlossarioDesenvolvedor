# Acoplamento

[Retornar](../README.md)

Acoplamento é a união ou a ligação entre dois ou mais corpos, formando um único conjunto. 

Este adjetivo é muito usado no desenvolvimento de software pois as partes (*building blocks*) precisam estar conectadas para a construção da aplicação, porém o acoplamento remete à um problema de "ligação" direta entre dois elementos que acaba causando um impacto grande, pois sempre que um elemento sofre uma alteração o outro também precisa ser alterado para continuar à funcionar.

Para eviar isso, devemos pensar e desenvolver o software com um **Baixo Acoplamento**, tendo um baixo nível de dependência entre componentes, assim mantê-los será algo menos problemático de se fazer.

## Exemplo Acoplamento
```C#
public class ProcessarVenda
{
  public void Executar()
  {
      var financeiro = new Financeiro();
      var estoque = new Estoque(); 
      
      if (finalizador.ValidarPagamento())
      {
        estoque.SepararPedido();
        estoque.DespacharPedido();
      }
  }
}
```

Digamos que haja alguma mudança na maneira de instanciar a classe `Financeiro` ou `Estoque`, teriamos que sair buscando em todas as classes que criam uma instância dessas classes para fazer as mudanças necessárias.

O alto acoplamento por exemplo, pode ser evitado usando a injeção de dependência.
