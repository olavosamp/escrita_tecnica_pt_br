- Original:
Pontos cegos que só apareceram no peer review

1. Você mirou no sotaque; o defeito é a veracidade. Este é o achado mais forte da rodada, apontado como resposta mais forte por 5 de 5 revisores. "Robusto", "seamless", travessão: isso é sotaque de IA, e a skill atual já mata. O que estraga um sumário de tarefa é outra coisa — a IA afirma que funciona sem ter rodado, descreve intenção como resultado, omite o que não testou, repete o diff em vez de dizer o que mudou de comportamento. Podar adjetivo de um relato falso produz uma mentira concisa. Commit, PR, plano e sumário precisam menos de estilo e mais de esquema com regra de veracidade: o que mudou, o que foi verificado e como, o que ficou fora, o que pode quebrar.

2. O mecanismo do ASD-STE100 não foi importado, só o clima dele. O padrão funciona porque tem dicionário fechado de ~900 palavras aprovadas e existe para leitor não nativo em contexto de segurança de voo. Em português esse dicionário não existe, e os leitores da Shape são devs nativos. Herdar os limites numéricos do inglês é herdar uma calibração que não foi feita para o português — a frase em pt-BR fica 20–30% mais longa para dizer o mesmo. A skill atual já corrigiu isso por estimativa (24/30), mas ninguém mediu.

3. Falta a lista de proibições verificáveis em pt-BR — a parte mais barata e a que mais entrega. "Vale ressaltar", "de forma robusta", "garantindo que", tríades, parágrafo-resumo final que repete o que já foi dito, hedge preventivo. O sotaque de IA em português vem principalmente de tradução do inglês, não de vocabulário rebuscado. O prompt não trouxe nenhuma lista dessas.

4. CLAUDE.md também tem custo, e ninguém precificou. Instrução sempre ativa consome contexto em toda sessão e perde força em conversa longa. O teste honesto é o turno 40, não o turno 1. Empurrar tudo para lá troca um problema de acionamento por um imposto de contexto.

- Problemas:

"Você mirou no sotaque; o defeito é a veracidade.": isso é linguagem de instagram ao invés de linguagem concisa e precisa. Melhor seria deletar essa frase de efeito, que funciona como título do parágrafo, e explicar diretamente no texto.


"4. CLAUDE.md também tem custo, e ninguém precificou. Instrução sempre ativa consome contexto em toda sessão e perde força em conversa longa." Problema: linguagem de efeito pouco clara. Melhor seria:
"Adicionar instruções no system prompt no CLAUDE.md gera um custo constante. Uma instrução adicionada dessa forma fica sempre ativa e consome contexto em toda sessão, além de perder força em conversas longas por esquecimento de contexto."

"O teste honesto é o turno 40, não o turno 1. Empurrar tudo para lá troca um problema de acionamento por um imposto de contexto.": linguagem de efeito em detrimento de precisão novamente. Melhor seria: "Um teste no turno 1 não avalia o problema do esquecimento de contexto. Para isso, é necessário um teste no turno elevado (ex: 40+)."

- Original:
"Fui direto nas duas perguntas: dá para estimar acessos de outra forma, e a lista de quem visitou a página está disponível por API."

- Problema:
"Fui direto nas duas perguntas:" não traz informação nenhuma, pode ser deletado da frase sem perda nenhuma. É só fluff.->"Podemos estimar acessos de outra forma e a lista de quem visitou a página está disponível por API."

- Original:

Alguns títulos de seção:

"Três coisas que provavelmente vão te surpreender"

"O princípio que decidiu o resto"

"Um número que muda o desenho da extração"

- Problema:

Todos são frases de efeito. Eu quero clareza nos meus relatórios, não clickbait de blog para atrair o leitor. Frase por frase:

"Três coisas que provavelmente vão te surpreender": Que coisas? Isso é uma frase de clickbait para fazer o leitor engajar com o texto, dando migalhas de informação ao invés de um título executivo que agilizaria a leitura e meu processo decisório. Eu quero informação, não perder tempo -> "Decisões principais do projeto"

"O princípio que decidiu o resto": Que princípio? Que resto? -> "Fundamento da arquitetura"

"Um número que muda o desenho da extração": Novamente, clickbait em detrimento da informação.->"Nota sobre a arquitetura do extrator"