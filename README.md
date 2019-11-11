# demonalgorithm
Algoritmo baseado no Demon Algorithm, desenvolvido por Michael Creutz.

Quando trabalhamos com um sistema de muitas partículas, tendo E, V e N
fixos, podemos integrar as equações de movimento para cada partícula e calcular a
média temporal das quantidades físicas de interesse. Porém, o que fazer quando
não se tem a equação de movimento das partículas do sistema? E como calcular as
médias de E, V e N através de um essemble? Uma maneira seria enumerar os
microestados acessíveis ao sistema e calcular a média das quantidades físicas
através de um essemble. Porém, mesmo para sistemas pequenos, podem existir
muitos microestados acessíveis.
Queremos então um método que nos forneça o número total de microestados
para uma dada energia. Isso pode ser feito fixando N, escolhendo aleatoriamente
um spin para ser up ou down e guardar essa configuração caso ela tenha a energia
total escolhida. Acontece que a maioria das configurações não teria a energia
desejada e teriam então que ser descartadas.
Pensando nisso, Michael Creutz desenvolveu o chamado ‘Demon Algorithm’,
que é uma simulação computacional de Monte Carlo microcanônica. Consideramos
um sistema macroscópico ao qual adicionamos um grau de liberdade, este é o
chamado ‘demônio’ do sistema, o qual transfere energia para o sistema quando há
uma tentativa de mudar a dinâmica das partículas do mesmo. Caso a mudança no
sistema diminua a energia total, o excesso de energia é dado para o demônio.
Entretanto, se a mudança aumenta a energia total do sistema, essa quantidade de
energia a mais tem que ser dada pelo demônio, caso este a tenha. Além disso, o
demônio não pode ter energia negativa.
