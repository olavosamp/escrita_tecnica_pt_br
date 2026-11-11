---
name: escrita_tecnica
description: Escreve e reescreve texto técnico em português do Brasil com foco em informação, precisão e concisão, sem linguagem de efeito, sem clickbait e sem enfeite de IA. Vale para documentação de código, README, comentário, docstring, descrição de PR, mensagem de commit, plano de implementação, relatório técnico e o resumo que você escreve no chat ao terminar uma tarefa. Use sempre que o texto for técnico e o leitor for um perfil técnico, mesmo que ninguém peça um estilo. Use também quando pedirem texto que não pareça escrito por IA, texto direto ao ponto, sem firula, sem marketing, ou quando reclamarem de título de efeito e frase vazia. Não use em escrita criativa, marketing, nem em texto onde a voz do autor importe.
---

# escrita_tecnica

Escreva para um leitor técnico que quer a informação e não quer ser convencido a ler.

Esta skill trata de **estilo**. Ela não verifica se o conteúdo é verdadeiro. Texto vazio continua
vazio depois de aplicada.

Não vale para: escrita criativa, marketing, post de divulgação, texto institucional, nem
qualquer texto onde a voz do autor faça parte do produto. Não vale para código, identificador nem sintaxe de comando. Esses ficam como estão.

**Idioma.** As regras de português nas seções 3, 6 e 7 valem para texto em português. Em
repositório cujo idioma predominante é o inglês, escreva em inglês e aplique só o que independe
de idioma: informação em vez de efeito (seção 1), corte do que não carrega informação (seção 2),
precisão (seção 4), frase e parágrafo (seção 5). Siga sempre o idioma predominante do repositório
e não traduza conteúdo que já existe.

Para texto em inglês, use a skill `ste-writing`. 

## Hierarquia de decisão

Quando duas regras desta skill entrarem em conflito, decida nesta ordem:

1. **Precisão.** Nunca sacrifique precisão por concisão. Um termo específico nunca vira um termo
   genérico para a frase ficar mais curta.
2. **Concisão.** Corte tudo que não carrega informação.
3. **Fluência.** Dentro do que sobrou, escolha a construção mais fácil de ler.

Texto que segue essa ordem fica mais seco. É o preço, e é aceitável.

## 1. Informação, não efeito

Esta é a regra que mais muda o texto. Título, abertura de seção e primeira frase de parágrafo
existem para localizar a informação, não para criar curiosidade.

Não escreva título que esconde o assunto para o leitor ter que ler o parágrafo:

- "Três coisas que provavelmente vão te surpreender" → "Decisões principais do projeto"
- "O princípio que decidiu o resto" → "Fundamento da arquitetura"
- "Um número que muda o desenho da extração" → "Nota sobre a arquitetura do extrator"
- "Cinco regras que não mudam desde o primeiro dia" → "Cinco regras que não mudam"

Não use frase de efeito como título de parágrafo, nem aforismo, nem antítese, nem paralelismo de
impacto. Se a frase de efeito resume o parágrafo, ela é redundante: apague e diga a coisa
diretamente.

- "Você mirou no sotaque; o defeito é a veracidade." → "O problema não está no vocabulário. Está
  em afirmar que o código funciona sem ter rodado."
- "O teste honesto é o turno 40, não o turno 1." → "Um teste no turno 1 não mede esquecimento de
  contexto. Para isso é necessário um teste em turno alto, por exemplo no turno 40."

A antítese aparece em várias superfícies e todas contam:

- "X não é A, é B"
- "X em vez de Y" ("As hipóteses mereceram medição em vez de opinião")
- "menos A, mais B"
- "A, não B"
- "não se trata de A, e sim de B"
- "o problema não é A, o problema é B"

Em todas, escreva a afirmação direta no lugar: "As hipóteses foram testadas por medição. O
resultado está abaixo."

Título nomeia o assunto. Palavra-chave em primeiro lugar. Evite título de uma palavra quando ele
ficar ambíguo: "Autenticação" → "Opções de autenticação do sistema". Sem gerúndio em título
("Configurando o ambiente" → "Configuração do ambiente"). Sem pontuação no fim do título.

### Teste do encurtamento

Este é o teste principal, e é mecânico. Encurte o título até o menor sintagma que ainda nomeia o
assunto. Se o encurtamento não perder informação, as palavras cortadas eram efeito.

Reprovados, porque encurtar não perde nada:

- "A conta que torna a extração completa inviável" → "Custo da extração completa"
- "O problema, nomeado" → "O problema"
- "O segredo da extração rápida" → "Extração rápida"
- "Três coisas sobre a extração" → "A extração"
- "A verdadeira causa da lentidão" → "Causa da lentidão"

Aprovados, porque encurtar perde o fato que o título carrega:

- "A API não entrega acesso", em que o encurtamento perderia a negação
- "O que a API não entrega"
- "Fatia 6: acesso real via analytics", em que o número identifica a fatia
- "Comparação de estratégias de extração", em que "comparação" diz o que a seção faz

### Gramática não é o teste

Não reprove um título por ser oração com verbo conjugado, nem por ter dois-pontos ou vírgula.
"A API não entrega acesso" é oração e é bom. "Fatia 6: acesso real" tem dois-pontos e é bom.
"A verdadeira causa" é sintagma nominal e é ruim. A forma gramatical não separa informação de
efeito, e usá-la como teste reprova título bom e aprova título ruim.

### Teste do índice

Quando o encurtamento for ambíguo, aplique este: o título funciona sozinho num índice, lido por
quem não leu o documento? Se for preciso ler a seção para saber do que ela trata, reescreva.

### Construções bloqueadas em título

Lista fechada, por serem quase sempre efeito. Independem da forma gramatical.

| Construção | Exemplo | Troque por |
|---|---|---|
| "O segredo de", "A verdade sobre", "O que ninguém conta" | "O segredo do cache" | "Funcionamento do cache" |
| "O verdadeiro X", "O X real", "O X que importa" | "A verdadeira causa" | "Causa" |
| "N coisas", "N motivos", "N lições" | "Três coisas sobre o deploy" | "Deploy" |
| Aposto que comenta o título | "O problema, nomeado" | "O problema" |
| "Por que X é Y", quando a seção não argumenta | "Por que o cache é lento" | "Latência do cache" |
| Metáfora | "O elefante na sala" | o nome da coisa |

### Capitalização

Duas formas aceitas, e uma rejeitada. Escolha uma e mantenha no documento inteiro.

```
Certo:  Comparação de estratégias de extração
Certo:  Comparação de Estratégias de Extração
Errado: comparação de estratégias de extração
```

Na segunda forma, preposição e artigo curtos ficam em caixa baixa: "de", "da", "do", "e", "em",
"para", "por".

## 2. Corte o que não carrega informação

Apague a frase inteira se ela puder sair sem perda:

- "Fui direto nas duas perguntas: podemos estimar acessos de outra forma e a lista está
  disponível por API." → "Podemos estimar acessos de outra forma e a lista está disponível por API."

Exemplos de tipos de frases por categoria que podem ser cortadas, não é uma lista exaustiva:

- **Anúncio do que você vai fazer**: "Vamos analisar", "Nesta seção veremos", "Antes de mais nada".
- **Meta-comentário sobre o próprio texto**: "vale ressaltar", "é importante notar", "cabe destacar",
  "note que", "convém observar".
- **Intensificador vazio**: realmente, simplesmente, basicamente, efetivamente, extremamente,
  bastante, muito, bem mais, diretamente, totalmente.
- **Hedge preventivo**: "de certa forma", "em geral", "de modo geral", "pode-se dizer que",
  "provavelmente", quando não há incerteza real a comunicar. Incerteza real fica: escreva qual é.
- **Adjetivo de marketing**: robusto, poderoso, elegante, sofisticado, de ponta, inovador,
  revolucionário, incrível, completo, intuitivo, sem esforço, perfeito.
- **Perífrase**: "de forma clara" → "claramente" ou nada; "de maneira a possibilitar" → "para";
  "no sentido de" → "para"; "a fim de" → "para"; "com o objetivo de" → "para".
- **Nominalização**: "realizar a validação da configuração" → "validar a configuração";
  "fazer a leitura do arquivo" → "ler o arquivo". Uma ação, um verbo.
- **Parágrafo-resumo final** que repete o que já foi dito. Termine no último fato.
- **Tríade retórica**: três itens quando dois bastam, só pelo ritmo.

Não corte: números, nomes de arquivo, nomes de variável, versões, condições, restrições, unidades,
nomes de serviço. Esses são a informação.

## 3. Voz, pessoa e tempo

**O sujeito é a coisa técnica, nunca uma pessoa.** Presente do indicativo.

- "O notebook busca as predições publicadas via `ClassePredict`. Ele não reextrai dados."
- "A latência caiu 30% depois da mudança no cache."
- "O parser lê o arquivo e valida os campos obrigatórios."

Proibido:

- Primeira pessoa: "medimos", "vamos ver", "acredito que", "no nosso caso".
- Indeterminação com `-se`: "observou-se", "pretende-se", "buscam-se", "verificou-se que houve".
- Futuro de intenção falando sobre situação presente: "o protocolo deverá examinar" → "o protocolo examina".
- "Devemos" / "é preciso que se faça" → corte e diga o que o sistema faz, ou use imperativo.
- Gerundismo, que é o gerúndio usado para marcar futuro ou intenção: "vamos estar verificando",
  "vou estar enviando". Use o tempo simples: "o job verifica", "o job envia". O gerúndio continua
  correto quando marca ação em curso: "o job está rodando agora".

**Passo de procedimento vai no imperativo**, nunca no infinitivo: "Defina os três parâmetros",
não "Definir os três parâmetros". Uma ação por passo.

A passiva analítica é permitida quando o agente é irrelevante ou desconhecido: "O arquivo é
gravado no bucket". Se o agente for conhecido e relevante, use-o como sujeito.

## 4. Precisão

- **Foco em Dados**: Se você tiver informações numéricas, concretas para apoiar uma sentença, use-as. "O modelo teve desempenho pior"->"A acurácia do modelo caiu de 88% para 83%", "A empresa teve turnover alto no último trimestre"->"O turnover foi de 8% no último trimestre, um valor alto."
- **Nada de específico vira genérico.** "Mover para Key Vault ou variável de ambiente" não vira
  "mover para outro lugar". "A query demora 8s" não vira "a query está lenta".
- **Um nome para cada coisa.** Fixado um termo, use o mesmo termo até o fim. Não alterne
  sinônimos para variar.
- **Defina antes de usar.** Nenhum termo, sigla ou objeto aparece antes de ter sido definido, ou
  com referência explícita à definição adiante. Introduza pela forma por extenso com a sigla entre
  parênteses, nunca pela sigla: "*Fiber Distributed Data Interface* (FDDI)". Depois use só a sigla.
- **Não defina por exemplo.** Primeiro a definição, depois o exemplo.
- **Separe o quê do como.** A abertura de um documento ou seção diz o que a coisa faz e por quê.
  Detalhe de implementação vem depois.
- **Estas palavras não são sinônimos**: esquema, modelo, método, política, mecanismo, metodologia,
  algoritmo, implementação, arquitetura. Escolha a certa.
- **Substitua vago por medida.** "melhora bastante o desempenho" → "reduz o tempo de resposta de
  400 ms para 90 ms". Se você não tem o número, diga o que sabe e não estime.

## 5. Frase e parágrafo

- Uma ideia por frase. Frase descritiva até ~30 palavras, passo de procedimento até ~24. Os
  limites são mais altos que os de guias em inglês porque o português gasta mais palavras para
  dizer a mesma coisa. São teto, não meta: não quebre uma frase boa só para caber.
- Não escreva a frase que muda de ideia no meio. Se ao reler você precisar voltar para entender o
  sujeito, quebre em duas ou três frases, uma por fator.
- Junte com "e", "nem", "mas", "ou" o que é uma ideia só. "Este notebook não reextrai dados nem
  refita modelos", não duas frases negativas seguidas.
- Um assunto por parágrafo, com a ideia-núcleo na primeira frase. Assunto novo, parágrafo novo.
- Ordem cronológica e causal. Não relate antes o que acontece depois. A informação nova se liga à
  anterior.
- Não comece frase com conectivo ("E o serviço...", "Mas a interface...").
- Não comece a primeira frase de uma seção com sujeito implícito no título. Repita o sujeito.
- Sujeito oculto é normal em português e é bem-vindo dentro do parágrafo. Só repita o substantivo
  quando dois referentes puderem se confundir.

## 6. Português — construções a evitar

- **Ondismo**: "onde" só para lugar. Use "em que", "no qual", "quando".
- **"O mesmo" como pronome**: "salve o arquivo e feche o mesmo" → "salve o arquivo e feche-o" ou
  repita o nome.
- **"Isto é"**: reescreva a frase e elimine.
- **"Não-algo"**: "a não necessidade de X" → "prescinde de X"; "a não entrega" → "o descumprimento
  do prazo".
- **"Foi feito"**: "ferramenta que foi feita em Java" → "ferramenta escrita em Java".
- **Decalque do inglês**: "assumir" no sentido de supor → pressupor, considerar, admitir;
  "endereçar um problema" → tratar; "performance" → desempenho; "eventualmente" no sentido de
  *eventually* → no fim, mais tarde; "entrada na tabela" → elemento da tabela.
- **Verbos errados**: "o programa roda" → é executado; "a figura descreve" → a figura mostra,
  indica, ilustra.
- **Adverbialização em -mente** empilhada. Uma por parágrafo, no máximo.
- **Anglicismo de efeito**: seamless, game changer, state-of-the-art, best-in-class. Termo técnico
  já estabelecido em inglês fica em inglês: commit, deploy, build, branch, merge, log, cache,
  endpoint, pipeline, container. Prefira "fazer o deploy" a "deployar".
- **Redução de fala**: tá, pra, né, vc, dá pra. As contrações obrigatórias (do, na, ao, pelo, num,
  deste) são gramática e ficam.
- **Repetição sonora**: rima, aliteração, cacofonia ("subiu rua acima"), excesso de "que".
- Ortografia do Brasil: arquivo, usuário, tela, salvar, baixar. Nunca ficheiro, utilizador, ecrã.

## 7. Pontuação e forma

- Sem ponto e vírgula no texto corrido. Escreva duas frases.
- Travessão: Evitar usar porque IA não tem uma relação boa com essa ferramenta. Os únicos casos POSITIVOS: como aposto ("você - meu amigo - falou isso") ou ressalva ("Ele era belo - apesar de ser tolo"). NEGATIVOS: Não é pausa de efeito nem substituto de ponto ("Explique o porquê, não o quê — o código já diz o quê" deveria ser "Explique o porquê, não o quê. O código já diz o quê"). 
- Cabeçalho na inicial maiúscula com o resto em caixa baixa, ou em Caixa Alta de Título. Ver a
  seção 1. Caixa baixa em tudo é erro.
- Decimal com vírgula, data em dd/mm/aaaa, fora de código e arquivo de configuração.
- Número: 0 a 9 por extenso no texto corrido; 10 ou mais em algarismo; sempre algarismo quando vem
  com unidade (3 MIPS, 8 s, 24 MB) ou em referência estrutural (Passo 4, Seção 6.2).
- Lista com marcador para itens sem ordem, lista numerada para sequência. Até nove itens; acima
  disso, divida. Introduza a lista com uma frase terminada em dois-pontos.
- Sem negrito para enfatizar afirmação. Negrito só para nome de campo, comando, opção de menu e
  termo que está sendo definido.
- Sem emoji. Ícones informativos são permitidos quando agregarem a visualização da informação. Exemplos comuns permitidos: ✅, ❌,ℹ️, ⚠️ e ícones similares.

## 8. Por gênero

**Documentação, README, docstring.** Abra dizendo o que a coisa faz, em uma frase. Depois o que
ela não faz, se isso evitar um erro comum. Depois como usar. Parâmetro se apresenta na ordem em
que é usado, com nome, tipo de valor e exemplo.

**Comentário de código.** Explique o porquê, não o quê — o código já diz o quê. Uma linha quando
der. Em `TODO`, mantenha a solução pretendida com o nome exato do recurso, não uma paráfrase.

**Descrição de PR.** O que mudou e por quê, em prosa curta. Depois o que o revisor precisa olhar.
Sem repetir o diff arquivo por arquivo.

**Mensagem de commit.** Conventional Commits: `tipo(escopo): descrição`. Descrição no imperativo,
minúscula, sem ponto final, curta. As regras de frase e parágrafo desta skill não se aplicam ao
assunto do commit; aplicam-se ao corpo, se houver.

**Resumo de tarefa no chat.** Diga o que mudou, onde, e o que ficou pendente. Sem abertura de
cortesia, sem recapitular passo a passo o que o usuário acompanhou, sem parágrafo final de
conclusão. Se algo não foi verificado, diga que não foi.

A primeira frase é o fato mais importante, e nunca uma frase sobre o próprio resumo. "Cinco coisas
mereceram medição em vez de opinião" anuncia o conteúdo sem entregar nada. "As hipóteses foram
testadas por medição, abaixo" entrega. Melhor ainda: comece pelo resultado da medição.

**Plano.** Passos numerados, um resultado observável por passo, e o que fica fora de escopo.

> Estas três últimas seções — PR, commit e resumo — ainda não foram calibradas com exemplos reais.
> Trate-as como provisórias e corrija-as conforme o uso.

## 9. Onde é fácil errar para o outro lado

Cortar demais também é erro. Não faça isso:

- Trocar o termo exato por um genérico para encurtar.
- Transformar todo parágrafo em frases de sete palavras. Isso vira um novo sotaque, tão
  reconhecível quanto o que estamos removendo.
- Apagar a condição ou a ressalva que muda o sentido ("apenas em produção", "quando o cache está
  frio").
- Apagar a repetição que existe para desambiguar. Repetir o substantivo é preferível a um "ele"
  que aponta para dois candidatos.

Na dúvida entre uma frase mais longa e clara e uma mais curta e ambígua, fique com a longa.

## 10. Autoverificação

Antes de entregar, passe por esta lista:

1. Cada título passa no teste do encurtamento da seção 1? Encurte e veja se perde informação.
   Se não perder, use a versão curta. Confira também a lista de construções bloqueadas em título.
2. Alguma frase de efeito, aforismo ou antítese em qualquer das superfícies da seção 1?
   Diga a coisa diretamente.
3. Alguma frase pode ser apagada inteira sem perda? Apague.
4. Alguma pessoa como sujeito, "-se" de indeterminação, futuro de intenção ou primeira pessoa?
   Ponha a coisa técnica como sujeito, no presente.
5. Algum passo de procedimento no infinitivo? Passe para o imperativo.
6. Algum termo específico virou genérico na reescrita? Volte o termo.
7. Alguma sigla ou termo usado antes de ser definido? Defina antes.
8. A mesma coisa com dois nomes? Escolha um.
9. Nominalização no lugar do verbo, intensificador vazio, meta-comentário, adjetivo de marketing?
   Corte.
10. Ponto e vírgula, negrito de ênfase, emoji não informativo? Corrija.
11. Cada travessão introduz aposto ou ressalva? Se o que vem depois for oração independente, com
    sujeito e verbo próprios, é pausa de efeito: troque por ponto. Contar travessão não basta,
    porque um só já pode ser efeito.
12. O último parágrafo repete o que já foi dito? Apague.
13. No resumo em chat, a primeira frase entrega um fato ou anuncia o conteúdo? Entregue o fato.
14. Alguma frase ficou ambígua depois do corte? Devolva a palavra que faltou.

Escreva apenas o texto pedido. Sem preâmbulo e sem comentário final sobre o que você fez.
Exceção: no resumo de tarefa dentro do chat, o texto é o próprio turno de conversa.

## 11. Lista viva de construções bloqueadas

As regras acima são fixas. As construções que **este usuário** rejeita variam, e a lista cresce
com o uso.

Ao começar, procure o arquivo de bloqueios nesta ordem e leia o primeiro que existir:

1. `.claude/escrita-bloqueios.md` na raiz do projeto
2. `~/.claude/escrita-bloqueios.md`

Se ele existir, trate cada entrada como regra desta skill.

Durante a sessão, acrescente uma entrada quando — e apenas quando — o usuário rejeitar uma
construção que você escreveu, reescrever um trecho seu, ou apontar um vício. Não invente entradas,
não registre preferência que você deduziu sozinho e não registre a mesma construção duas vezes.

Formato, uma linha por entrada:

```
- <construção rejeitada> → <o que usar no lugar>  (dd/mm/aaaa)
```

Se o arquivo não existir e a sessão produzir a primeira entrada, pergunte ao usuário se ele quer
criar o arquivo. Não crie sem um sim. Se ele recusar, siga sem o arquivo e não pergunte de novo na
mesma sessão.

Limite conhecido: isso só funciona nas sessões em que a skill está carregada e em que o usuário dá
a correção de forma explícita. Não é um loop de feedback fechado. Serve para acumular vocabulário
proibido específico do usuário sem depender de ferramenta externa.

---

Fontes: Hexsel, *Pequeno Manual da Escrita Técnica* (UFPR, 2004); Ercília Maria, *Escrita
Acadêmica: Princípios Básicos* (UFSM, 2019); Guia de Estilo de Publicações Técnicas da Alterdata.
