# Gerador de Relatórios (sem chat)

Página única que transforma a tabela de placeholders do app em relatório PDF no formato de celular.

**Como usar**
1. Abra a página: `https://natangomess1.github.io/gerador-relatorios/`.
2. Cole a tabela que o app gera (`__CLIENTE__ ...`) ou um JSON com os mesmos campos.
3. Toque em **Gerar relatório**.
4. Em "O que fizemos no mês", copie o histórico de atividades do seu sistema e cole no campo do canal certo (Perfil no Google, Anúncios, Site), uma ação por linha. Canal vazio não aparece.
5. Se quiser, escolha a **logo do cliente** (PNG com fundo transparente). Ela aparece pequena no topo da capa e fica guardada só no seu navegador, ligada ao nome do cliente.
6. Se souber, preencha o total de **avaliações** do Perfil. Revise os "Próximos passos".
7. Em **Mensagem para o WhatsApp**, confira o resumo de 3 linhas, coloque o nome de quem recebe e toque em **Copiar mensagem**. Se editar o texto, ele não é refeito sozinho; **Refazer texto** volta ao automático.
8. Toque em **Baixar PDF** e escolha "Salvar como PDF".

**No celular:** o menu do topo leva direto a cada parte (Dados, Mensagem, O que fizemos, Ajustes, Passos, Prévia), e a barra de baixo deixa Atualizar, Copiar mensagem e Baixar PDF sempre à mão.

**O que ela faz sozinha**
- Detecta os canais: só Ads, só GBP ou os dois. Páginas de canal ausente somem.
- Faz as contas: comparação com o mês anterior, custo por contato, contatos por dia, WhatsApp x ligação e cenários de retorno (a partir da hipótese de % e ticket).
- Escreve as frases por regra (manchete, tendência, maioria) e sugere 3 próximos passos.
- **Pedidos de rota** ficam fora da contagem por padrão (o Google infla esse número). Nesse caso, contato do Perfil = ligações + WhatsApp + site, e as estimativas usam esse total. Marque a caixa só para clientes em que a visita à loja importa.
- Avisa quando o Perfil tem menos de 10 avaliações: o relatório ganha uma página sobre isso e o passo "pedir avaliação aos clientes". O total pode vir do campo da tela ou de `__GBP_AVALIACOES__` na tabela.
- Escreve a mensagem do WhatsApp com a mesma manchete da capa, o número com comparação e o passo mais importante (avaliações primeiro, se o perfil tiver poucas). Não leva estimativa em R$, porque fora do PDF ela pode ser lida como promessa.
- Confere os dados e avisa só no painel, sem ir para o PDF: soma das campanhas diferente do total, partes que não fecham, falta de mês anterior ou de hipótese.

**Privacidade:** os dados ficam no navegador e não são enviados para lugar nenhum.

**Site (GA4/Search Console):** ainda não tem página. Quando o app gerar esses campos, a página é adicionada aqui.

**Regras de texto:** vêm do Agente de Relatórios (repositório `site-agropet`, pasta `agente-relatorios/` e skills em `.claude/skills/`). Ao mudar uma regra lá, atualize esta página também.

`grade.html` é uma página separada (Grade de Posições).
