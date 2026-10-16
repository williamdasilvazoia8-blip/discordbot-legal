---
title: "Política de Privacidade — Veritas Bot"
permalink: /privacidade/
---

# Política de Privacidade — Veritas Bot

Última atualização: 16 de outubro de 2026

## 1. Responsável pelo tratamento e contacto

O responsável pelo tratamento dos dados pessoais tratados pelo Veritas Bot (“o bot”) é **William Z.**, contactável em **[williamdasilvazoia8@gmail.com](mailto:williamdasilvazoia8@gmail.com)**.

- Para o RGPD, sou o “responsável pelo tratamento”. Para a LGPD, sou o “controlador”.
- Não foi designado um encarregado de proteção de dados (DPO). O e-mail acima é o canal para qualquer questão ou pedido sobre dados pessoais.
- Os administradores de cada servidor Discord decidem que funcionalidades ativar e que ações de moderação aplicar, e são responsáveis pelas suas decisões de moderação.

## 2. Âmbito

Esta política aplica-se a quem interage com o Veritas Bot em servidores Discord onde ele foi adicionado: membros que escrevem mensagens nos canais a que o bot tem acesso, quem usa os seus comandos e quem é alvo de ações de moderação.

O bot oferece:

- respostas automáticas a referências bíblicas escritas em mensagens comuns (por exemplo, “João 3:16”) e comandos `/biblia`;
- liturgia diária, calendário litúrgico e santos do dia (`/liturgia`, `/calendario`);
- moderação (`/mute`, `/unmute`, `/mute-status`, `/kick`, `/ban`, `/unban`, `/purge`, `/modlogs`, `/configurar-silenciado`);
- anúncios agendados e recorrentes (`/agendar`) e configurações do servidor (`/config`).

O uso do Discord rege-se também pela [Política de Privacidade do Discord](https://discord.com/privacy). O bot não tem site, não usa cookies e não tem contas próprias de utilizador.

## 3. Dados que tratamos

O bot guarda apenas identificadores do Discord e os textos que moderadores e administradores escrevem nos comandos. Não guarda nomes de utilizador, e-mails, endereços IP de utilizadores nem o conteúdo das mensagens comuns.

| Categoria | O que é guardado | De quem | Onde |
| --- | --- | --- | --- |
| Registos de moderação | ID Discord do alvo e do moderador; tipo de ação (silenciar, expulsar, banir, desbanir, limpar mensagens); motivo escrito pelo moderador; duração, início, fim e estado; ID de quem levantou o silenciamento | Membros moderados e moderadores | Base de dados (Heroku Postgres) |
| Mensagens agendadas | Texto, título e cargos a mencionar escritos pelo administrador; ID de quem criou; canal, data, hora, fuso e recorrência; registo de cada envio (data, tentativas, ID da mensagem publicada pelo bot, erro) | Administradores | Base de dados (Heroku Postgres) |
| Registo de auditoria | ID de quem alterou configurações, agendamentos ou aplicou moderação; ID do alvo; detalhes da alteração (por exemplo, IDs de canais e cargos) | Moderadores e administradores | Base de dados (Heroku Postgres) |
| Configurações do servidor | ID do servidor, canais e cargos escolhidos, fuso horário, idioma e opções das funcionalidades | Administradores | Base de dados (Heroku Postgres) |
| Dados temporários em memória | Conteúdo e metadados de mensagens, dados de membros (nome, cargos, estado de silenciamento), IDs de mensagens já processadas | Todos os membros visíveis ao bot | Memória (RAM) do servidor do bot, nunca em disco |
| Logs técnicos | IDs de servidor, mensagens de erro e, em erros de comunicação com o Discord, o conteúdo que o bot tentava enviar | Moderadores e administradores, ocasionalmente | Registo de logs do Heroku |

O texto da Bíblia e os dados litúrgicos não são dados pessoais.

O bot recebe do Discord, a cada interação, o perfil público de quem a usa (ID, nome de utilizador, avatar). Desse perfil, só o ID é guardado, e apenas nos casos da tabela.

Os motivos de moderação e o texto dos agendamentos são texto livre. Podem conter outros dados pessoais se quem os escreve os incluir.

## 4. Conteúdo das mensagens

O bot lê o conteúdo das mensagens para detetar referências bíblicas, mas não o grava em base de dados, ficheiros nem logs.

- **Leitura.** O bot usa a permissão “Message Content” do Discord. Lê as mensagens dos canais a que tem acesso, exceto as de bots, de sistema e de webhooks (estes podem ser autorizados pelo servidor). Os administradores podem limitar os canais com `/biblia configuracao`.
- **Tratamento.** O texto é analisado em memória para encontrar referências como “João 3:16”. Se o servidor ativar a identificação de citações (desligada por padrão), o texto também é comparado com o texto bíblico. A resposta contém apenas texto bíblico.
- **Memória temporária.** O bot mantém em RAM as últimas 200 mensagens de cada canal, com o conteúdo, até serem substituídas por mensagens mais recentes ou até o bot reiniciar. Os IDs de mensagens já processadas ficam em memória para evitar respostas duplicadas. Nada disto é escrito em disco.
- **Exceções.** São guardados os textos escritos nos comandos de moderação (motivos) e de agendamento (mensagens agendadas), descritos na secção 3.
- **`/purge`.** Ao limpar mensagens, o bot lê as últimas 100 mensagens do canal para escolher quais apagar. Fica registado apenas o número de mensagens apagadas e o canal.

O bot nunca altera nem apaga mensagens de membros, exceto quando um moderador usa `/purge`.

## 5. Finalidades e fundamentos legais

Tratamos dados apenas para fazer funcionar as funcionalidades pedidas pelos servidores e para manter a segurança das comunidades. Não vendemos dados, não fazemos publicidade nem criação de perfis, e não tomamos decisões automatizadas com efeitos jurídicos.

| Finalidade | Dados | RGPD (art. 6.º, n.º 1) | LGPD (art. 7.º) |
| --- | --- | --- | --- |
| Responder a referências bíblicas e a comandos | Conteúdo das mensagens (só em memória), ID de quem usa o comando | Interesse legítimo (alínea f): prestar o serviço pedido pela comunidade | Legítimo interesse (inciso IX) |
| Moderação e registos de moderação | IDs do alvo e do moderador, motivo, datas | Interesse legítimo (alínea f): segurança e cumprimento das regras do servidor | Legítimo interesse (inciso IX) |
| Anúncios agendados | Texto e ID de quem criou | Interesse legítimo (alínea f) | Legítimo interesse (inciso IX) |
| Auditoria e segurança | IDs de quem altera configurações ou modera | Interesse legítimo (alínea f): responsabilização e prevenção de abusos | Legítimo interesse (inciso IX) |
| Diagnóstico de erros | Logs técnicos | Interesse legítimo (alínea f): manter o serviço a funcionar | Legítimo interesse (inciso IX) |

Estes tratamentos usam o mínimo de dados necessário (identificadores numéricos), são os que um membro pode razoavelmente esperar de um bot de comunidade e têm prazos limitados (secção 6). Pode opor-se a eles a qualquer momento (secção 9).

**Convicções religiosas.** O bot não recolhe nem regista a religião de ninguém. Como funciona em comunidades católicas, um registo de moderação pode indiretamente associar uma pessoa a uma comunidade religiosa. Para limitar esse risco, guardamos apenas identificadores numéricos e o motivo escrito pelo moderador, por prazo limitado. Não partilhamos estes registos fora do servidor Discord onde foram criados, exceto com os fornecedores da secção 7.

## 6. Prazos de conservação

Os dados são conservados apenas pelo tempo necessário. A eliminação dos registos em base de dados é feita manualmente pelo responsável, pelo menos uma vez por mês.

| Dados | Onde | Prazo |
| --- | --- | --- |
| Registos de moderação | Heroku Postgres | 12 meses após a data da ação |
| Registo de auditoria | Heroku Postgres | 12 meses após o registo |
| Mensagens agendadas e histórico dos seus envios | Heroku Postgres | 90 dias após o agendamento ser concluído ou cancelado |
| Configurações do servidor | Heroku Postgres | 30 dias após o bot ser removido do servidor |
| Tarefas na fila (contêm só identificadores internos e mensagens de erro) | Redis | Concluídas: até 7 dias. Falhadas: até 30 dias. Eliminação automática |
| Mensagens em memória | RAM | Até serem substituídas por mensagens mais recentes ou o bot reiniciar |
| Logs técnicos | Heroku | Até 1.500 linhas mais recentes, no máximo 1 semana ([Heroku](https://devcenter.heroku.com/articles/logging)) |
| Cópias de segurança automáticas da base de dados | Heroku Postgres | Período de recuperação do plano Heroku contratado; os dados eliminados desaparecem quando as cópias são substituídas |
| Mensagens publicadas no Discord (respostas, anúncios, registos no canal de moderação) | Discord | Até serem apagadas pelos administradores do servidor |

## 7. Serviços externos e subcontratantes

Apenas o Discord e o Heroku recebem dados pessoais. As APIs litúrgicas recebem só datas.

| Serviço | Que dados recebe | Papel |
| --- | --- | --- |
| [Discord](https://discord.com/privacy) (Discord Inc., EUA) | Todas as respostas do bot, ações de moderação (silenciar, expulsar, banir, apagar mensagens), anúncios e registos publicados no canal de moderação (ID e menção do alvo, moderador, motivo) | Plataforma onde o bot funciona; trata os dados segundo a sua própria política |
| [Heroku](https://devcenter.heroku.com/articles/gdpr) (Salesforce, Inc., EUA) | Tudo o que está na secção 3: servidor do bot, base de dados Heroku Postgres, fila Redis e logs | Subcontratante (RGPD) / operador (LGPD) |
| [Liturgia Diária (Dancrf)](https://github.com/Dancrf/liturgia-diaria) | Apenas a data pedida e o endereço IP do servidor do bot; nenhum dado de utilizadores | Fornecedor de conteúdo litúrgico |
| [Liturgical Calendar API (LitCal)](https://github.com/Liturgical-Calendar/LiturgicalCalendarAPI) | Apenas o ano, o calendário e o idioma, e o IP do servidor; nenhum dado de utilizadores | Fornecedor do calendário e dos santos do dia |

Não usamos serviços de análise, publicidade ou inteligência artificial. A ferramenta de base de dados Prisma, usada para aplicar atualizações ao arranque, pode enviar à Prisma dados técnicos anónimos de utilização (versão, sistema operativo), sem dados de utilizadores.

## 8. Transferências internacionais

Os dados são tratados nos Estados Unidos, o que constitui uma transferência internacional para utilizadores da União Europeia e do Brasil.

1. **Discord.** A Discord Inc. tem sede nos Estados Unidos. Tudo o que o bot lê e publica passa pelos servidores do Discord. O Discord descreve na sua [política de privacidade](https://discord.com/privacy) os mecanismos que usa para estas transferências, como as cláusulas contratuais-tipo e o EU-US Data Privacy Framework.
2. **Heroku.** O bot, a base de dados e os logs estão alojados na região dos Estados Unidos do Heroku. A Salesforce, dona do Heroku, está certificada no EU-US Data Privacy Framework e oferece cláusulas contratuais-tipo e regras vinculativas aplicáveis às empresas no seu [Acordo de Tratamento de Dados](https://devcenter.heroku.com/articles/gdpr).

No RGPD, estas transferências baseiam-se na decisão de adequação do EU-US Data Privacy Framework (art. 45.º) e, subsidiariamente, nas cláusulas contratuais-tipo (art. 46.º). Na LGPD, baseiam-se no art. 33.º, com as garantias contratuais oferecidas por estes fornecedores.

As APIs litúrgicas não recebem dados de utilizadores, por isso não há transferência de dados pessoais para elas.

## 9. Os seus direitos

Pode exercer os seus direitos enviando um pedido para **[williamdasilvazoia8@gmail.com](mailto:williamdasilvazoia8@gmail.com)**, com o seu ID de utilizador do Discord. Para confirmar que o pedido é seu, posso pedir-lhe que o confirme por mensagem a partir dessa conta.

- **Acesso e confirmação** de que tratamos dados seus (RGPD art. 15.º; LGPD art. 18.º, I e II).
- **Retificação** de dados inexatos (RGPD art. 16.º; LGPD art. 18.º, III).
- **Eliminação** (RGPD art. 17.º; LGPD art. 18.º, IV e VI).
- **Limitação** do tratamento (RGPD art. 18.º) e **anonimização ou bloqueio** (LGPD art. 18.º, IV).
- **Oposição** ao tratamento baseado em interesse legítimo (RGPD art. 21.º; LGPD art. 18.º, § 2.º).
- **Portabilidade** (LGPD art. 18.º, V; no RGPD, art. 20.º, apenas quando aplicável).
- **Informação** sobre com quem partilhamos dados (LGPD art. 18.º, VII) — ver secção 7.

**Como tratamos os pedidos.** Os pedidos são tratados manualmente pelo responsável, diretamente na base de dados. Respondemos no prazo de um mês, prorrogável nos termos do RGPD (art. 12.º, n.º 3). Nos pedidos ao abrigo da LGPD, a confirmação completa é dada em até 15 dias (art. 19.º, II).

**Limites.** Podemos conservar um registo de moderação enquanto for necessário para a segurança da comunidade ou para defesa em processos, dentro do prazo da secção 6. As mensagens que o bot publicou no Discord só podem ser apagadas pelos administradores do servidor. Os dados guardados pelo próprio Discord devem ser pedidos ao Discord.

## 10. Segurança

Aplicamos estas medidas:

- comandos de moderação, agendamento e configuração verificam as permissões e a hierarquia de cargos de quem os usa, além das restrições do Discord;
- os dados de cada servidor são separados pelo ID do servidor, e um servidor não acede aos dados de outro;
- as respostas do bot não mencionam ninguém automaticamente, e `@everyone` nunca é mencionado;
- as credenciais (token do Discord, acesso à base de dados) ficam nas variáveis de configuração do Heroku, fora do código;
- segundo a documentação do Heroku, o Heroku Postgres guarda os dados em discos cifrados.

Em caso de violação de dados com risco para os titulares, notificaremos a autoridade de controlo em 72 horas (RGPD art. 33.º) e a ANPD e os titulares em prazo razoável (LGPD art. 48.º).

## 11. Menores, alterações e reclamações

**Menores.** O bot só funciona dentro do Discord e segue a idade mínima definida pelos termos do Discord. Não pedimos nem registamos a idade de ninguém. Se souber que tratamos dados de uma criança sem fundamento adequado (LGPD art. 14.º; RGPD art. 8.º), contacte-nos para os eliminarmos.

**Alterações.** Podemos atualizar esta política. A data de “Última atualização” no topo indica a versão em vigor; recomendamos que a consulte periodicamente.

**Reclamações.** Pode apresentar reclamação a uma autoridade de proteção de dados:

- em Portugal, à [Comissão Nacional de Proteção de Dados (CNPD)](https://www.cnpd.pt);
- noutro Estado-Membro da UE, à autoridade do seu país;
- no Brasil, à [Autoridade Nacional de Proteção de Dados (ANPD)](https://www.gov.br/anpd).
