# Design Patterns com Java: Dos Clássicos (GoF) ao Spring Framework

## O código implementa o padrão de projeto Facade para simplificar a interação com um subsistema complexo composto por um videogame, um console e um drive. O objetivo do padrão Facade é fornecer uma interface unificada que facilite a utilização de um conjunto de classes de maneira mais simples e coesa, ocultando a complexidade do sistema.

### Estrutura do Código:
Classe VideoGame: Representa o videogame e tem métodos que simulam as ações básicas do dispositivo, como iniciar (start), executar (execute), carregar a tela inicial (load) e liberar dados (free).
Classe Console: Representa o console que exibe as informações do videogame. Os métodos load e free são responsáveis por carregar e liberar os dados do console.
Classe Drive: Representa o drive (como o HD do videogame), com métodos para ler (read) e gravar (write) dados. O método read retorna uma string simulando o processo de leitura do setor de inicialização do HD.
Classe VideoGameFacade: A classe Facade centraliza as operações complexas e oferece um único ponto de interação para o cliente (no caso, o usuário do sistema). Ela tem referências para as classes VideoGame, Console e Drive. O método ligarVideoGame orquestra a sequência de ações necessárias para ligar o videogame:

### Inicia o videogame com videoGame.start().
Lê os dados do setor de inicialização do HD com drive.read().
Carrega as informações no console com console.load().
Executa o videogame com videoGame.execute().
Libera a memória e os dados com videoGame.free() e console.free().
Classe Main: A classe Main é o ponto de entrada para o programa. Ela instancia as classes VideoGame, Console, Drive e VideoGameFacade, e chama o método ligarVideoGame() da classe VideoGameFacade para simular o processo de inicialização do videogame.

### Funcionamento do Padrão Facade:
Sem o Facade: O cliente precisaria interagir diretamente com as classes VideoGame, Console e Drive, chamando métodos em cada uma delas, o que tornaria o código mais complexo e menos coeso.
Com o Facade: A classe VideoGameFacade simplifica essa interação, oferecendo um único método (ligarVideoGame()) que realiza todas as operações necessárias de forma coordenada. O cliente interage apenas com a fachada, sem se preocupar com a implementação interna de cada componente.
Vantagens do Facade:
Simplicidade: O cliente tem uma interface simples e limpa para interagir com o sistema.
Desacoplamento: O cliente não precisa entender a complexidade do sistema subjacente, o que reduz o acoplamento entre ele e as classes internas.
Facilidade de Manutenção: Alterações nas classes internas (como a adição de novos métodos ou mudanças na lógica de inicialização) não afetam o cliente, desde que a fachada mantenha a mesma interface.

No geral, o código implementa um exemplo claro de como o padrão Facade pode ser usado para simplificar a interação com um subsistema complexo, proporcionando uma interface única e fácil de usar.
