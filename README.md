# testeatv
<img width="1643" height="957" alt="image" src="https://github.com/user-attachments/assets/e1a0b7c0-4cbf-4a74-a5df-b295a45ccc0a" />


Classe Filme
Construtor:

Deve possuir um construtor cheio e validar as seguintes condições:

O título não pode ser nulo ou vazio.
O gênero não pode ser nulo.
O diretor não pode ser nulo ou vazio.
A duração em minutos não pode ser nula e deve ser maior que zero.

Caso alguma dessas condições não sejam atendidas, deve ser lançada uma exceção do tipo FilmeInvalidoException com uma mensagem apropriada.

Métodos:

Deve conter apenas getters para todos os atributos.

Interface Observador
Método:
void receberFilme(Filme filme)

Método abstrato que será chamado para notificar o observador sobre um novo filme adicionado.

Classe Usuario
Construtor:
Usuario(String nome, String email, Genero generoFavorito)

Inicializa os atributos:

nome
email
generoFavorito

Inicializa a lista de filmes recebidos como uma lista vazia.

Inicializa a lista de favoritos como uma lista vazia.

Métodos:
receberFilme(Filme filme)
Adiciona o filme recebido à lista de filmes do usuário.
Se o gênero do filme for igual ao gênero favorito do usuário, o filme também deve ser adicionado à lista de favoritos.

Deve conter apenas getters para todos os atributos.

Classe Estatistica
Métodos:
getPercentual()

Método abstrato que retorna o percentual da estatística em relação ao total de filmes recebidos.

receberFilme(Filme filme)

Atualiza o total de filmes recebidos.

Deve conter apenas getters para todos os atributos.

Classe EstatisticaGenero
Construtor:
EstatisticaGenero(Genero genero)

Inicializa:

genero
qtdFilmes com zero
qtdGenero com zero
Métodos:
receberFilme(Filme filme)
Incrementa o atributo qtdFilmes.
Se o gênero do filme for igual ao gênero da estatística, incrementa qtdGenero.
getPercentual()

Retorna o percentual de filmes do gênero em relação ao total de filmes recebidos.

Se qtdFilmes for zero, o método deve retornar 0.0 para evitar divisão por zero.

Deve conter apenas getters para todos os atributos.

Classe EstatisticaDiretor
Construtor:
EstatisticaDiretor(String diretor)

Inicializa:

diretor
qtdFilmes com zero
qtdDiretor com zero
Métodos:
receberFilme(Filme filme)
Incrementa qtdFilmes.
Se o diretor do filme for igual ao diretor da estatística, incrementa qtdDiretor.
getPercentual()

Retorna o percentual de filmes do diretor em relação ao total de filmes recebidos.

Se qtdFilmes for zero, o método deve retornar 0.0.

Deve conter apenas getters para todos os atributos.

Classe Streaming
Construtor:
Streaming(String nome)

Inicializa:

nome
lista de observadores vazia
Métodos:
inscrever(Observador observador)

Adiciona o observador à lista de observadores.

desinscrever(Observador observador)

Remove o observador da lista de observadores.

adicionarFilme(Filme filme)

Notifica todos os observadores sobre o novo filme, chamando o método:

receberFilme(filme)

para cada observador.

getGeneroMaisAssistido()

Retorna o gênero com maior percentual entre todas as as estatísticas registradas.

Se não houver estatísticas registradas, o método deve retornar null.

getUsuarioComMaisFavoritos()

Retorna o nome do usuário com maior quantidade de filmes favoritos.

Se não houver usuários inscritos, o método deve retornar null.

Enum Genero
ACAO
COMEDIA
DRAMA
TERROR
Classe FilmeInvalidoException

Deve herdar de:

RuntimeException
