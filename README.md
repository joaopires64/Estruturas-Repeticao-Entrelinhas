# Estruturas-Repeticao-Entrelinhas

Exercícios Para revisão e ficação para os alunos do projeto Entre Linhas, PUC minas Barreiro.

Olá, aluno! O objetivo desta atividade é praticar o uso de estruturas de repetição em C#.

Você encontrará três exercícios de "completar o código". Em cada um, você deve analisar a lógica e preencher as condições ou valores que faltam, indicados pelos comentários // ...?.

# Intrunções

## Jogos!

Nessa aula preparei tres jogos simples, para testar sua sorte e o seu conhecimento em soma e multiplicação. Ao total temos tres jogos, um no qual envolve adicionar dois numeros aleatórios, o segundo que envolve sorte, no qual você deve acertar qual o numero correto. e por fim, o terceiro, no qual você escolhe o numero e escreva sua taboada, com no máximo 4 erros.

### Requisitos para entrega!
Entrega deve ser feita em sala de aula, com revisão ao final

Como acessar?
Os Codigos estão disponiveis abaixo de cada exercício. Basta abrir um novo projeto no seu visual studio code, digitar o comando no terminal: "dotnet new console" e inserir e completar os codigos dentro do arquivo "Program.cs". Assim que terminar o exercicio, teste o prgrama digitando o comando "dotnet run" e verifique se aatende ao que foi pedido.

Atenção
Tudo o que for pedido estará comentado na cor verde, nos comentarios do códio (caso não tenha essa cor, avise o professor) Siga o que os comentarios te pedir, mas não esqueça de ler o texto abaixo porque muitas perguntas só podem ser respondidas adequadamente com os textos abaixo

Leia a descrição de cada exercício.

Analise o código-fonte fornecido.

Encontre os comentários que fazem uma pergunta (ex: // qual a condição...?).

Substitua os espaços em branco (como ==, while(), i <=, etc.) pela lógica correta para fazer o jogo funcionar.

Desde já bons estudos!

## Exercicio 1

Jogo de Soma (Loop while)

Objetivo: Este jogo gera somas aleatórias. O jogador precisa acertar 3 somas para vencer. O loop while é usado aqui porque não sabemos quantas tentativas o usuário levará, apenas sabemos a condição de parada (3 pontos).

Código:

        // esse jogo tem como foco em ver se o numero digitado pelo usuário corresponde a soma correta
        // variaveis, numero1, numero 2, respota e pontuação atual (valor inicial 0)
        int numero1, numero2, resposta, pontuiacao = 0;

        // Mensagem de boas-vindas
        Console.WriteLine("Bem-vindo ao jogo de soma!");

        // Gerador de números aleatórios
        Random random = new Random();

        // estrutura de repetição para o jogo continuar 
        while (pontuiacao < ) // qual pontuação é necessária para vencer? O loop continua ENQUANTO a pontuação for MENOR que 3.
        {
            numero1 = random.Next(1, 101); // Gera um número entre 1 e 100
            numero2 = random.Next(1, 101); // Gera um número entre 1 e 100

            Console.WriteLine($"Qual é a soma de {numero1} + {numero2}?");
            resposta = int.Parse(Console.ReadLine());

            // qual a condição para a pessoa ponturar?
            if (resposta == ) // Verifique se a RESPOSTA do usuário é IGUAL à soma
            {
                pontuiacao++;
                Console.WriteLine("Resposta correta! Sua pontuação é: " + pontuiacao);
            }
            else
            {
                Console.WriteLine("Resposta incorreta. Tente novamente!");
            }
        }
        // após sair da repetição, mensagem de vitória
        Console.WriteLine("Parabéns! Você alcançou 3 pontos e venceu o jogo!");


## Exercicio 2

Jogo de Adivinhação (Loop do-while)

Objetivo: O computador sorteará um número de 1 a 9. O usuário deve adivinhar qual é. O jogador tem no máximo 5 TENTATIVAS. Se acertar, vence. Se errar 5 vezes, perde.

Usamos do-while porque o usuário deve jogar pelo menos uma vez antes de verificarmos a condição de parada.

Código:

        // agora esse jogo depende de sorte, um numero de 1 a 9 será sortado e o usuário deve adivinhar qual é esse numero
        // se em 5 tentativas o usuário não acertar, o jogo acaba, se ele acertar, ele vence
        // variaves numero sorteado, resposta e uma variavel boolean para verificar se ele acertou
        int numerosorteio, resposta, tentativas = 0;
        bool acertou = false;
        
        Console.WriteLine("Bem-vindo ao Jogo de Adivinhação (1-9)!");

        // Gerador de números aleatórios
        numerosorteio = new Random().Next(1, 10); // Gera um número entre 1 e 9

        // ele executa a repetiçaõ pelo menos uma vez
        do
        {
            Console.WriteLine($"Tentativa {tentativas + 1} de 5. Qual número foi sorteado?");
            resposta = int.Parse(Console.ReadLine());
            
            // se a resposta for igual ao numero sorteado, a pessoa acertou
            if (resposta == )
            {
                acertou = true;
            }

            // verificação das condições de vitória ou derrota
            // se ele acertou, ele vence
            if (acertou == true)
            {
                Console.WriteLine("Resposta correta! Parabens, você ganhou!");
            }
            // caso o contrario, se ele já tenha tentado 5 vezes, ele perde
            // se caso esse else if for verdadeiro, o jogo acaba
            else if (tentativas ==) // qual condição verifica se esta foi a 5ª tentativa  e ele errou?
            {
                Console.WriteLine($"Número de tentativas esgotadas. Você perdeu! O número era {numerosorteio}.");
            }
            // caso contrario, ele não acertou e ainda tem tentativas
            else
            {
                Console.WriteLine("Resposta incorreta. Tente novamente!");
                tentativas++;
            }

        // quais as condições devem ser atendidas para continuar no jogo?
        // 1. Ele NÃO pode ter acertado 
        // 2. Ele PRECISA ter menos de 5 tentativas 
        } while (acertou   && tentativas ); 


## Exercicio 3

Jogo da Tabuada (Loop for)

Objetivo: Este é um desafio de tabuada. Você escolherá um número e o programa perguntará a tabuada dele, do 1 ao 9. Você tem um limite de erros.

Usamos for porque sabemos exatamente quantas vezes o loop deve rodar (9 vezes, uma para cada item da tabuada).

Regra: Serão tolerados no máximo 4 erros (ou seja, você precisa de 5 acertos para vencer).

Código:

        // Por fim, temos esse ultimo exercicio, ele é mais complexo, então preste bastante atenção
        // você deve escolher um numero, a partir dai, fazer a taboada desse numero,
        // dica: evite numeros muito longos para não dificultar o calculo da taboada
        // a taboada vai do numero 1 ao 9, serão tolerados no máximo 4 erros
        // variaves eu numero, resposta e acertos
        int seunumero, resposta, acertos = 0;

        // Mensagem de boas-vindas
        Console.WriteLine("Bem-vindo ao Jogo da Tabuada!");
        Console.WriteLine("Escreva um numero qualquer (dica: não escreva numeros muito grandes)");

        seunumero = int.Parse(Console.ReadLine());

        // repetição usando for. A taboada vai de 1 a 9.
        // qual numero a variavel i deve ser menor ou igual para manter a repetição?
        for (int i = 1; i <= ; i++)
        {
            // exibir qual numero deve ser digitado
            Console.Write($"Quanto é {seunumero} x {i}? ");
            resposta = int.Parse(Console.ReadLine());

            // qual operadores devemos usar para verificar se a resposta é igual à multiplicação?
            if (resposta == )
            {
                acertos++;
                Console.WriteLine("Correto!");
            }
            else
            {
                Console.WriteLine("Incorreto.");
            }
        }

        // quantos acertos deve ter para vencer?
        // Se o total é 9 e o limite de erros é 4, você precisa de 5 acertos.
        if (acertos )
        {
            Console.WriteLine("Parabens, você ganhou!");
        }
        else
        {
            Console.WriteLine("Você perdeu, mais sorte da próxima vez!");
        }
