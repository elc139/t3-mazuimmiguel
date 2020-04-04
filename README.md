[Programação Paralela](https://github.com/AndreaInfUFSM/elc139-2020a) > Trabalhos

# T3: Scheduling com OpenMP 

## Preparação

1. Este trabalho deve ser feito em um computador com mais de um núcleo de processamento. 



2. Estude o programa [ThreadDemoABC.cpp](ThreadDemoABC.cpp), que implementa 3 casos de teste para ilustrar o escalonamento de 3 threads que atualizam concorrentemente um array compartilhado. Este programa usa POSIX Threads. Cada thread insere 20 caracteres A, B ou C na próxima posição livre. Os caracteres podem ser adicionados em diferentes posições, dependendo do escalonamento das threads. Qualquer que seja a ordem, no final de um caso de teste a contagem de caracteres no array deve ser igual a 60, a não ser em casos de implementação incorreta, em que não é garantida exclusão mútua.



3. Compile e execute o programa, observando os resultados em cada caso de teste.

   ```
   g++ -std=c++11 ThreadDemoABC.cpp -pthread -o ThreadDemoABC
   ./ThreadDemoABC
   ```


## Trabalho

Usando o programa [ThreadDemoABC.cpp](ThreadDemoABC.cpp) como inspiração, você deverá criar um novo programa chamado `OpenMPDemoABC.cpp`. Seu programa vai implementar vários casos com threads que atualizam o array compartilhado, usando OpenMP, ilustrando o efeito das opções de escalonamento disponíveis para a cláusula `schedule`:

  1. Schedule `static`, com e sem especificação do `chunk`
  2. Schedule `dynamic`, com e sem especificação do `chunk`
  3. Schedule `guided`, com e sem especificação do `chunk`
  4. Schedule `runtime`
  5. Schedule `auto`
  6. Um ou mais casos sem exclusão mútua, para apresentar saídas incorretas.

  Note que, ao contrário do programa original com POSIX Threads, você deixará o particionamento/aglomeração/mapeamento também a cargo do OpenMP (no programa original, isso é feito manualmente e cada thread faz exatamente 20 inserções).


## Entrega

Em seu repositório, crie um documento `Entrega.md`, contendo:
 - Identificação da disciplina e do aluno;
 - Link para o programa `OpenMPDemoABC.cpp` desenvolvido.
 - Exemplo de saída do programa, com explicação dos casos de teste.
 - Referências.
 

 
## Material de apoio

- [Tutorial OpenMP](https://computing.llnl.gov/tutorials/openMP/)  
  Tutorial do Lawrence Livermore National Laboratory (LLNL) sobre OpenMP. 

