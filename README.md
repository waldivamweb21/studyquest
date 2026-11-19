📚 StudyQuest

Aplicativo de estudos para concursos que roda no navegador do celular e funciona sem internet. Você carrega o seu banco de questões uma vez e passa a estudar por assunto, fazer simulados, revisar erros e acompanhar o seu avanço até o dia da prova.

Versão atual: 2.5 · Sem servidor, sem conta e sem anúncios. Tudo fica no seu aparelho.

✨ Recursos

Estudo

Estudar por assunto: lista de tópicos por disciplina, com cores de progresso: 🟢 resolvido, 🟡 em andamento, 🔴 não resolvido (ex.: 5/12).
Simulado completo: 10, 20, 30 ou 50 questões sorteadas, com resultado e tempo por questão no final.
Filtros: Todas, Não respondidas e Respondidas.
Navegação livre: botões Anterior e Próxima; ao voltar, o resultado da questão continua visível.
Continuar de onde parou: se você sair no meio, a sessão é retomada na mesma questão.
Toques nas alternativas: 1 toque seleciona; 2 toques seguidos riscam a alternativa (2 de novo desriscam). Depois é só tocar em Responder.
Marcar para revisão: o botão fica verde quando a questão está marcada.

Revisão

Separada por Básicas e Específicas.
Grupos dentro de cada categoria: ✘ Errei, ★ Acertei, mas marquei e ★ Marcadas sem responder.
A questão sai da lista quando você a acerta na revisão (e a marca é retirada). Se errar de novo, ela volta para Errei.

Painel

Constância nos estudos: um quadrado por dia, do primeiro dia de estudo até a prova (🟩 estudou, 🟥 não estudou, 🟨 hoje, ⬜ dias futuros, 🟪 dia da prova), com sequência atual e recorde.
Data da prova: nome, banca e data, com contagem de dias restantes calculada sozinha.
Avanço no edital: pizza com a porcentagem de tópicos resolvidos (verde) e dos que faltam (vermelho), mais uma barra por disciplina.
Acertos e erros (geral e de hoje), radar de acertos por disciplina ou assunto, e tabela de acertos por assunto.
Tempo de estudo: foco do pomodoro e tempo gasto em questões, separado por estudo, simulado e revisão.

Pomodoro

Bip no início do intervalo e outro ao fim do ciclo (gerados no próprio app).
Foco, intervalo, intervalo longo e ciclos configuráveis; pode iniciar junto com as questões.

Outros

Modo escuro e claro.
Backup em arquivo .json (sem limite de tamanho) e restauração que soma ao que já existe, sem duplicar.
Instalável como app (PWA) e com funcionamento offline.
🚀 Como publicar (GitHub Pages)
Coloque os arquivos deste repositório na raiz da branch principal.
Vá em Settings > Pages, escolha Deploy from a branch, branch main e pasta / (root), e salve.
Em 1 a 2 minutos o site fica em https://SEU_USUARIO.github.io/NOME_DO_REPOSITORIO/.
Instalar no Android
Abra o endereço no Chrome.
Toque em ⋮ > Instalar app (ou Adicionar à tela inicial).
Abra o StudyQuest pelo ícone e carregue o banco de questões (veja abaixo).
🗂️ Banco de questões

⚠️ Este repositório não inclui questões. O app é só o programa: o conteúdo é seu. Use apenas material que você tem o direito de usar e não publique questões protegidas por direitos autorais.

Na primeira abertura, o app pede o arquivo do banco (questoes-mobile.json). Ele é guardado no próprio aparelho (IndexedDB) e depois o app funciona sem internet. Para trocar de banco, use Revisar > Importar outro banco.

O arquivo é uma lista (array) de questões neste formato:

json
[
  {
    "i": "bas-1.1-001",
    "k": "Básicas",
    "d": "Língua Portuguesa",
    "t": "Interpretação de textos",
    "n": "Fácil",
    "s": "Enunciado da questão…",
    "o": { "A": "…", "B": "…", "C": "…", "D": "…", "E": "…" },
    "a": "C",
    "e": "Comentário / explicação (opcional)"
  }
]
Campo	Significado
i	Identificador único e estável da questão (usado no progresso e nos backups)
k	Categoria: use Básicas ou Específicas (as abas de Revisar usam esses dois nomes)
d	Disciplina
t	Assunto / tópico (base do avanço no edital)
n	Dificuldade (opcional)
s	Enunciado
o	Alternativas, de A a E
a	Letra do gabarito
e	Comentário (opcional)
💾 Backup do progresso

Seu progresso (respostas, marcações, configurações e dados da prova) fica somente neste navegador. Limpar os dados do Chrome apaga tudo, então faça backup de vez em quando:

Revisar > Backup do progresso > Salvar arquivo: abre o menu de compartilhar do Android (Drive, WhatsApp, Arquivos). Guarda tudo, sem limite de tamanho.
Restaurar de arquivo: soma as respostas do arquivo ao que você já tem. Importar duas vezes não duplica nada.
Evite colar o backup em apps de notas: muitos cortam o texto perto de 20.000 caracteres.
🔄 Como atualizar uma versão
Substitua os arquivos no repositório (Add file > Upload files).
Em sw.js, troque o nome do cache (const CACHE='studyquest-vN') para um número novo. Sem isso, o celular continua mostrando a versão antiga guardada.
No celular, abra e feche o app duas vezes. O rodapé do Painel mostra a versão instalada.
🧱 Estrutura e tecnologias
index.html              aplicativo inteiro (HTML + CSS + JavaScript)
manifest.webmanifest    dados de instalação do PWA
sw.js                   service worker (funcionamento offline)
icon-192.png            ícones do app
icon-512.png
icon-maskable-512.png
HTML, CSS e JavaScript puros, sem dependências e sem etapa de build.
localStorage para o progresso e IndexedDB para o banco de questões.
Service Worker para uso offline e Web Audio para os bips do pomodoro.
🔒 Privacidade

Não há servidor, conta, rastreamento ou envio de dados. O repositório é público, mas não contém questões nem dados pessoais: tudo o que você estuda fica no seu aparelho.

📝 Histórico de versões
Versão	Novidades
2.5	Revisão separada em Errei, Acertei, mas marquei e Marcadas sem responder
2.4	1 toque seleciona e 2 toques riscam alternativas; botão de revisão verde; questão sai da revisão ao acertar; cabeçalho compacto
2.3	Constância nos estudos, data da prova com contagem de dias e cores por disciplina
2.2	Backup em arquivo e restauração que soma sem apagar
2.1	Tópicos coloridos (verde, amarelo, vermelho) e gráfico de avanço no edital
2.0	Navegação entre questões, continuar de onde parou, radar de acertos, tempo por atividade, revisão por categoria, pomodoro integrado e modo escuro
1.x	Primeira versão para celular: estudo, simulado, painel e pomodoro
📄 Licença

Projeto pessoal de estudo. Defina uma licença (por exemplo, MIT) antes de compartilhar o código com outras pessoas.
