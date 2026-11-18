<div align="center">

<img src="assets/logo-github.png" alt="WD Ferragens" width="360">

# Portal B2B de Pedidos — WD Ferragens

**Plataforma de pedidos para revendas de ferragens para vidros temperados.**
O cliente monta o pedido com fotos, cores e os preços da sua tabela comercial, envia para orçamento
e a WD Ferragens recebe, responde e acompanha tudo por um painel administrativo completo.

![Node.js](https://img.shields.io/badge/Node.js-22-339933?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-4-000000?logo=express&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-node%3Asqlite-003B57?logo=sqlite&logoColor=white)
![Caddy](https://img.shields.io/badge/HTTPS-Caddy-1F88C0?logo=caddy&logoColor=white)
![Oracle Cloud](https://img.shields.io/badge/Hospedagem-Oracle%20Cloud-F80000?logo=oracle&logoColor=white)

</div>

> As imagens abaixo foram geradas com **dados fictícios** de demonstração (clientes, pedidos e preços inventados).
> O portal real é de uso **privado** da WD Ferragens e de seus clientes.

---

## Visão geral

<p align="center"><img src="docs/telas/01-login.jpg" alt="Tela de login" width="860"></p>

| Para o cliente (revenda) | Para a WD Ferragens (administração) |
|---|---|
| Catálogo com **várias fotos por produto**, busca e categorias | **Painel** com pedidos novos, faturamento do mês e destaques |
| Escolha de **cor/acabamento** (BC, BZ, NF, PT) | Cadastro de **produtos**, galeria de fotos, cores e preços |
| **Preços da tabela comercial** de cada cliente | **Tabelas de preço** por cliente, importação/exportação em **Excel** |
| Carrinho salvo na conta, com **recálculo instantâneo** | **Clientes**: cadastro, tabela exclusiva, preços especiais, bloqueio |
| Envio do pedido para orçamento + **envio pelo WhatsApp** com PDF | **Pedidos**: resposta ao orçamento, ajuste de preços, custo e margem |
| **Histórico**, repetir pedido e **pedido em PDF** | **Relatórios**: produtos mais vendidos, melhores clientes, cores, categorias |
| **Notificações** quando a WD ajusta ou responde um pedido | **Ajuste do pedido** já enviado: troca de produto/cor, quantidade, preço, itens |
| **Esqueci minha senha** com link por e-mail e espera crescente | **Alertas** de pedido de nova senha, com pop-up no painel |
| **Minha empresa**: o gestor convida e gerencia os colaboradores | Aprovação **uma vez por empresa** e papel de cada pessoa (gestor/comprador) |

---

## Experiência do cliente

### Catálogo
Busca por código, nome ou descrição, filtro por categoria e preço conforme a tabela do cliente.
<p align="center"><img src="docs/telas/02-catalogo.jpg" alt="Catálogo" width="860"></p>

### Produto com cor e acabamento
Cada ferragem é vendida nas cores Branco, Bronze, Natural fosco e Preto; a cor escolhida acompanha o item
no carrinho, no pedido e no PDF, com o preço da tabela comercial do cliente. Cada produto pode ter **várias fotos**
(galeria com miniaturas, deslizar no celular e clique para ampliar).
<p align="center"><img src="docs/telas/03-produto.jpg" alt="Página do produto" width="860"></p>

### Carrinho
Quantidade e totais são recalculados **na hora**, e o carrinho é salvo automaticamente na conta do cliente.
<p align="center"><img src="docs/telas/04-carrinho.jpg" alt="Carrinho" width="860"></p>

### Pedido enviado + WhatsApp
Ao finalizar, o cliente envia o pedido para a WD Ferragens pelo **WhatsApp** com um clique: a mensagem já
vai pronta, com o resumo dos itens e um **link seguro do PDF** do pedido.
<p align="center"><img src="docs/telas/05-pedido-whatsapp.jpg" alt="Pedido enviado" width="860"></p>

### Pedido em PDF
Documento pronto para salvar em PDF ou imprimir: quantidade, código, descrição, cor, preço unitário e total.
<p align="center"><img src="docs/telas/06-pdf-pedido.jpg" alt="Pedido em PDF" width="860"></p>

### Notificações: o cliente sabe o que mudou no pedido
Quando a WD Ferragens ajusta, responde ou muda a situação de um pedido, o cliente recebe uma **notificação no site**:
o menu ganha o item **Notificações** com um contador, e a página mostra **exatamente o que mudou** (cor, quantidade,
preço, item trocado, removido ou acrescentado), o **motivo** escrito pela equipe e um atalho para o pedido.
<p align="center"><img src="docs/telas/20-notificacoes.jpg" alt="Notificações do cliente" width="860"></p>

No próprio pedido aparece o quadro **"Ajustado pela WD Ferragens em …"** com o histórico das mudanças, e os itens e o
total abaixo já vêm atualizados. Abrir o pedido marca as notificações dele como lidas.
<p align="center"><img src="docs/telas/21-pedido-ajustado-cliente.jpg" alt="Pedido ajustado visto pelo cliente" width="860"></p>

### Esqueci minha senha
O cliente informa o e-mail e recebe um **link para criar uma nova senha** (válido por 60 minutos); ao trocar, recebe também
o aviso "Sua senha foi alterada". A mensagem é **a mesma para e-mail cadastrado ou não**, para o portal não revelar quem é
cliente, e a equipe da WD é avisada na hora.
<p align="center"><img src="docs/telas/13-esqueci-senha.jpg" alt="Esqueci minha senha" width="860"></p>

Contra abuso, cada e-mail tem uma **espera crescente entre pedidos: 1 → 5 → 15 → 60 minutos**, guardada no banco de dados
(continua valendo mesmo se o servidor reiniciar). Os e-mails saem da **caixa de e-mail própria da WD Ferragens**
(domínio wdferragens.com.br) — convites e "Esqueci minha senha" chegam por e-mail. E o **WhatsApp fica sempre como alternativa**:
a equipe pode mandar o link de nova senha direto no WhatsApp do cliente (veja *Alertas* no painel).
<p align="center"><img src="docs/telas/14-esqueci-senha-espera.jpg" alt="Espera entre pedidos de nova senha" width="860"></p>

### Empresa e colaboradores
No portal, **a empresa é o CNPJ**: todas as pessoas da mesma revenda compartilham a tabela de preço, os **preços especiais**
e os dados da empresa, mas cada uma tem o **próprio login** e um papel — **gestor** (dono ou T.I.) ou **comprador**.

**1. Cadastro da empresa.** Quem cadastra um CNPJ novo vira o **gestor** da empresa, e a WD Ferragens aprova a empresa **uma única vez**.
<p align="center"><img src="docs/telas/22-cadastro-empresa.jpg" alt="Cadastro da empresa" width="860"></p>

O formulário separa os **dados da empresa** da seção **Responsável (gestor da empresa)** — normalmente o dono, um sócio ou o T.I.,
que depois convida os compradores da equipe.
<p align="center"><img src="docs/telas/31-cadastro-responsavel.jpg" alt="Seção Responsável (gestor da empresa) no cadastro" width="860"></p>

**2. Pedido de acesso.** Se alguém se cadastra com um CNPJ que já existe, o cadastro vira um **pedido de acesso** à empresa:
a pessoa é avisada de que o gestor vai aprovar, e o gestor recebe uma **notificação** no site.
<p align="center"><img src="docs/telas/23-pedido-de-acesso.jpg" alt="Pedido de acesso enviado" width="860"></p>
<p align="center"><img src="docs/telas/24-notificacao-pedido-acesso.jpg" alt="Notificação de pedido de acesso para o gestor" width="860"></p>

**3. Minha empresa.** O gestor tem a página **Minha empresa** (com contador de pedidos de acesso no menu): vê todas as pessoas com
acesso, **aprova ou recusa** pedidos, **desativa e reativa**, **torna outra pessoa gestor**, **reenvia o acesso** e edita os
dados da empresa, que valem para todos.
<p align="center"><img src="docs/telas/25-minha-empresa.jpg" alt="Minha empresa com pedido de acesso pendente" width="860"></p>

**4. Convite com link — ninguém define a senha de outra pessoa.** Em *Adicionar colaborador*, o gestor informa nome, e-mail,
WhatsApp e papel. O colaborador recebe um **link para criar a própria senha**, que vale **7 dias** e funciona **uma única vez**.
O link vai **por e-mail** e, **mesmo com o e-mail ligado**, o gestor vê o link com os botões **Copiar link** e
**Mandar pelo WhatsApp** (mensagem pronta com o login e o link) — útil quando o e-mail cai no spam ou a pessoa prefere o WhatsApp.
A WD Ferragens recebe um aviso de cada novo colaborador.
<p align="center"><img src="docs/telas/36-convite-email-e-whatsapp.jpg" alt="Convite enviado por e-mail, com link e WhatsApp" width="860"></p>

Sem e-mail configurado, o convite continua funcionando só com o link e o WhatsApp:
<p align="center"><img src="docs/telas/26-convite-colaborador.jpg" alt="Convite de colaborador com link e WhatsApp" width="860"></p>
<p align="center"><img src="docs/telas/27-criar-senha.jpg" alt="Colaborador cria a própria senha" width="860"></p>

A equipe da empresa fica assim: gestores e compradores ativos, acessos desativados guardados (os pedidos continuam no histórico)
e a garantia de que a empresa **sempre tem pelo menos um gestor ativo**.
<p align="center"><img src="docs/telas/28-minha-empresa-equipe.jpg" alt="Equipe da empresa" width="860"></p>

**5. Pedidos da empresa.** O comprador vê os próprios pedidos; o gestor vê os **pedidos de todas as pessoas** da empresa, com o nome de quem comprou.
<p align="center"><img src="docs/telas/29-pedidos-da-empresa.jpg" alt="Pedidos da empresa" width="860"></p>

### Funciona no celular
<p align="center"><img src="docs/telas/12-celular.jpg" alt="Versão celular" width="300"></p>

---

## Painel administrativo

### Painel
Pedidos novos, clientes, faturamento do mês, produtos mais pedidos e melhores clientes.
<p align="center"><img src="docs/telas/07-admin-painel.jpg" alt="Painel administrativo" width="860"></p>

### Pedido com custo e margem
A equipe responde o orçamento, ajusta preços, muda a situação e gera o PDF do cliente ou o PDF interno com custo.
<p align="center"><img src="docs/telas/11-admin-pedido.jpg" alt="Pedido no admin" width="860"></p>

### Ajustar um pedido já enviado
Faltou estoque, o cliente pediu por telefone para mudar algo ou a equipe quer dar um desconto? Em **Responder / ajustar pedido**
a WD altera o pedido depois de enviado, numa única tela:
- **trocar o produto** (ex.: 3210 → 3211) ou a **cor** (ex.: Preto → Branco), com o preço da tabela do cliente aplicado automaticamente;
- mudar a **quantidade** (0 remove) e o **preço unitário**, marcar **Remover** ou **acrescentar** novos itens (preço em branco = preço da tabela);
- escrever o **motivo** que o cliente vai ler, mudar a situação e a resposta (prazo, pagamento, validade).

O pedido nunca fica sem itens (para desistir, usa-se "Cancelado"), e pedido **Aprovado** ou **Cancelado** só muda se o administrador
marcar uma confirmação extra.
<p align="center"><img src="docs/telas/17-ajustar-pedido.jpg" alt="Ajustar pedido" width="860"></p>

Ao salvar, o **total, o custo e a margem são recalculados** e o cliente é avisado em Notificações.
<p align="center"><img src="docs/telas/18-pedido-ajustado-admin.jpg" alt="Pedido ajustado no admin" width="860"></p>

Cada ajuste fica no **Histórico de ajustes** do pedido: o que mudou, o motivo, quem fez e quando.
<p align="center"><img src="docs/telas/19-historico-ajustes.jpg" alt="Histórico de ajustes" width="860"></p>

### Alertas de pedido de nova senha
Quando um cliente pede nova senha, o menu ganha **Alertas** com contador e o painel abre um **pop-up acessível**
(foco no primeiro botão, fecha com Esc): *"Pedido de nova senha: comprador — empresa (e-mail), às HH:MM"*, com as ações
**Enviar link por e-mail**, **Enviar link pelo WhatsApp**, **Abrir cliente**, **Já resolvi** e **Lembrar daqui a 10 min**.
A WD também recebe o aviso no **WhatsApp**.
<p align="center"><img src="docs/telas/32-alerta-email-whatsapp.jpg" alt="Pop-up de alerta com envio por e-mail ou WhatsApp" width="860"></p>

**Enviar link pelo WhatsApp** gera um link de nova senha que vale **24 horas** e funciona uma vez (os anteriores deixam de valer),
resolve o alerta e abre o **WhatsApp do cliente** com a mensagem pronta. O mesmo botão fica na página de cada cliente, em *Senha do cliente*.
<p align="center"><img src="docs/telas/33-link-senha-whatsapp.jpg" alt="Link de nova senha pronto para mandar pelo WhatsApp" width="860"></p>

Pop-up da versão anterior, com e-mail ainda desligado:
<p align="center"><img src="docs/telas/15-alerta-popup.jpg" alt="Pop-up de alerta no painel" width="860"></p>

A página **Alertas** mostra os pedidos em aberto e o histórico dos resolvidos (quando e por quem). Se o próprio cliente
troca a senha pelo link, o alerta se resolve sozinho.
<p align="center"><img src="docs/telas/16-alertas.jpg" alt="Página de alertas" width="860"></p>

### Clientes por empresa
A WD vê todas as pessoas agrupadas por empresa (CNPJ), com o **papel** de cada uma, a tabela, os pedidos e a situação.
Empresas novas aparecem como **aguardando aprovação**; a WD continua podendo editar qualquer pessoa (inclusive o papel) e bloquear qualquer acesso.
<p align="center"><img src="docs/telas/30-admin-clientes-empresas.jpg" alt="Clientes por empresa no painel" width="860"></p>

### Tabela de preço da empresa
A tabela de preço é **do CNPJ**, não de cada pessoa: vale para o gestor e para **todos os colaboradores, atuais e futuros**.
Na página do cliente, o quadro **Tabela de preço da empresa** mostra a tabela atual (exclusiva ou compartilhada) e tem
**Vincular à empresa** e, para empresa nova, **Vincular e aprovar empresa** — tudo num clique. Também dá para criar uma tabela
exclusiva a partir de outra. Aprovar uma empresa sem tabela pede confirmação (ela veria o catálogo sem preços).
Ao lado, em **Senha do cliente**: enviar o link de nova senha por e-mail (vale 1 h) ou pelo WhatsApp (vale 24 h).
<p align="center"><img src="docs/telas/34-empresa-tabela-de-preco.jpg" alt="Empresa nova aguardando: quadro Tabela de preço da empresa" width="860"></p>
<p align="center"><img src="docs/telas/35-empresa-vinculada-aprovada.jpg" alt="Tabela vinculada e empresa aprovada" width="860"></p>

### Tabelas de preço
Grade de preços por tabela, preenchimento por markup sobre o custo e importação/exportação em Excel.
<p align="center"><img src="docs/telas/10-tabela-precos.jpg" alt="Tabela de preços" width="860"></p>

### Relatórios
Faturamento por período, comparação com o período anterior, ticket médio e rankings.
<p align="center"><img src="docs/telas/08-relatorios.jpg" alt="Relatórios" width="860"></p>
<p align="center"><img src="docs/telas/09-relatorios-rankings.jpg" alt="Rankings" width="860"></p>

---

## Funcionalidades em detalhe

- **Cadastro de empresas** com validação de **CNPJ**, WhatsApp e endereço; quem cadastra vira **gestor** e a WD aprova a empresa **uma vez**.
- **Empresa e colaboradores:** várias pessoas por CNPJ, cada uma com o próprio login e papel (gestor ou comprador); o gestor convida
  (link de 7 dias e uso único, por e-mail ou WhatsApp), aprova pedidos de acesso, desativa/reativa, promove gestor e vê os pedidos de todos.
- **Preços por empresa (CNPJ):** tabela comercial (ex.: Tabela A, Tabela B), **tabela exclusiva** por cliente e **preços especiais** por produto.
  Cliente sem tabela vê "Preço sob consulta" e pode pedir mesmo assim — a equipe cota os itens.
- **Cores/acabamentos** (Branco, Bronze, Natural fosco e Preto); a cor aparece no carrinho, no pedido, no PDF e nos relatórios.
- **Importação do catálogo** a partir do PDF oficial (recorte automático das fotos) e da tabela de preços em Excel.
- **Pedidos:** situação (novo, em análise, orçamento enviado, aprovado, cancelado), resposta ao cliente, repetir pedido.
- **Ajuste de pedido pela WD:** trocar produto ou cor, mudar quantidade e preço, remover e acrescentar itens, com motivo;
  total recalculado, **histórico de ajustes** (o quê, quem, quando) e confirmação extra para pedidos aprovados ou cancelados.
- **Notificações do cliente** no site, com contador no menu, o que mudou e o motivo; marcadas como lidas ao abrir o pedido.
- **Recuperação de senha por e-mail:** link de uso único válido por 60 minutos, aviso de senha alterada, mesma resposta
  para e-mail cadastrado ou não e **espera crescente** (1 → 5 → 15 → 60 min) guardada no banco; e-mails saindo da caixa própria da WD.
- **WhatsApp como alternativa:** link de nova senha pelo WhatsApp do cliente (24 h, uso único) no alerta e na página do cliente;
  convite de colaborador sempre com link + "Mandar pelo WhatsApp".
- **Tabela de preço da empresa (CNPJ):** vincular à empresa ou vincular e aprovar num clique; vale para o gestor e todos os colaboradores.
- **Alertas para a equipe:** menu Alertas com contador, pop-up no painel com ações rápidas, lembrete em 10 minutos,
  histórico de resolvidos e aviso no WhatsApp.
- **LGPD:** política de privacidade e termos de uso com aceite registrado, download dos próprios dados e exclusão de conta
  (dados pessoais anonimizados; pedidos mantidos por obrigação fiscal).
- **Envio pelo WhatsApp** via link `wa.me` com mensagem pronta e PDF público protegido por código secreto.
- **Exportação** de pedidos para Excel e **relatórios** com gráficos acessíveis (tooltip e tabela de dados).
- **Equipe**: vários administradores, troca de senha, dados da empresa editáveis no PDF e no site.
- **Segurança:** senhas com bcrypt, sessão em cookie assinado (`httpOnly`, `sameSite`, `secure` em produção),
  escape automático de HTML, proteção contra tentativas repetidas de login e HTTPS.

## Tecnologia

| Camada | Escolha |
|---|---|
| Servidor | Node.js 22 + Express (páginas renderizadas no servidor) |
| Banco de dados | SQLite nativo do Node (`node:sqlite`) — sem serviços externos |
| Interface | HTML + CSS próprio (identidade visual WD: azul-marinho e laranja) + JavaScript leve |
| Planilhas | ExcelJS (importação/exportação) |
| Hospedagem | Oracle Cloud (Always Free), Ubuntu, systemd, Caddy com HTTPS automático (Let's Encrypt) |
| Operação | Backup diário automático do banco e das fotos; publicação por script que nunca toca nos dados |

## Código-fonte

Este repositório é uma **vitrine** do projeto: apresenta as telas e as funcionalidades.
O **código-fonte é privado** e pertence a **Gabriel Espindula** — não está disponível para download ou reutilização.

---

<div align="center">

© 2026 **WD Ferragens**. Todos os direitos reservados. Projeto privado — exibido apenas para fins de portfólio. Nenhuma parte deste material pode ser copiada ou reutilizada sem autorização.

Desenvolvido por **[Espindula](https://github.com/G-Espindula97)**

</div>
