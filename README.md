# Modelagem-Banco-de-Dados-Atividade-1
Atividade-01 Modelagem banco de dados
# P r o j e t o E R P — Lavanderia Sta. Bárbara
 
## 1 . I d e n t i f i c a ç ã o d a e q u i p e 
### Michael, Kaik, Iago, Enzo, Vinícius, Victor, Veronica, Leo
 
## 2 . C a r a c t e r i z a ç ã o d a e m p r e s a 
### Qual é o segmento?
Lavanderia, lavagem geral(Atende diferentes nichos) 
### O que ela vende ou oferece? 
Faz o serviço de lavagem, secagem, passagem de peças
E restaurações em casos específicos.
### Quem são seus principais clientes? 
Empresas e pessoas que buscam lavagens mais especializadas
### Quais são seus principais setores? 
Atendimento; Área para coleta; setor de lavagem; secagem; passagem

## 3 . J u s t i f i c a t i v a d a e s c o l h a 

Problemas Analisados:
 Os pedidos não seguem um padrão de registro, e os custos existem só na cabeça da Dona. Sem esses dados documentados, não dá para calcular prazos com precisão. falta de controle de despesas. A estratégia para levantá-los já está definida.

Não existe sistema de cadastro, então clientes e pedidos ficam dispersos. A sistematização dos processos é ocasional, sem etapas fixas do pedido à entrega.

É viável, começando pelo cadastro de pedidos. Ele padroniza o registro, guarda os custos e permite estimar prazos com base em dados. A implantação deve ser gradual, módulo por módulo.
 
## 4 . P r o b l e m a s i d e n t i f i c a d o s 

Raramente. O preço vem de fatores físicos do item, fáceis de verificar. O problema é a informação oculta no meio do processo, que só a Dona conhece.

Nada é digital. Todos os controles são manuais, exceto o contato com clientes, feito por celular.

## 5 . P r o c e s s o s d e n e g ó c i o 
### Cliente → Pedido → Serviços → Coleta → Pagamento

### O cliente chega ao atendimento, faz o pedido, ela anota em uma comanda o item(peça), o serviço que será realizado e um prazo de entrega.
### Dentro da empresa o item passa pelos processos oriundos do serviço, após a peça estar pronta para o cliente, ela avisa o cliente para retirar a peça.
### Em casos específicos, pode ser realizada uma entrega!
 
## 6 . R e q u i s i t o s f u n c i o n a i s 
### O sistema deverá cadastrar o cliente
### O sistema deverá alterar o cadastro do cliente
### O sistema deverá registrar o pedido
### O sistema deverá finalizar pedido
### O sistema deverá registrar pagamento
### O sistema deverá controlar o inventario 
### O sistema deverá gerenciar prazos
### O sistema deverá gerenciar processos internos  
### O sistema deverá traquear os pedidos no processo interno
### O sistema deverá permitir selecionar etapas do processo para um item 
### O sistema deverá permitir alterar etapas do processo para um item 
### O sistema deverá cadastrar novos itens e seus serviços
### O sistema deverá fazer a exclusão de dados do pedido em tempos
 
## 7 . R e q u i s i t o s n ã o f u n c i o n a i s 
O sistema deverá manter registros dos pedidos por no mínimo 6 meses
O sistema deverá cadastrar e finalizar pedidos através de um código de barras.
 
## 8 . R e g r a s d e n e g ó c i o 

Um Cliente pode realizar vários orçamentos

Em caso onde o cliente se encontra debilitado, as peças podem ser entregues.

A roupa só pode ser retirada pelo recibo do pedido.

Deve ter no mínimo uma peça para realizar um orçamento.

A roupa não pode ser retirada durante o processo de limpeza.

É obrigatório ter no cadastro do cliente o nome, CPF, telefone e endereço.

Todo pedido deve ser registrado no sistema.

Ao final do pagamento, a peça da roupa ficará armazenada em um tempo definido pelo cliente, e após 30 dias deste prazo definido, a peça é doada.

Haverá atualização do cadastro a cada 1 ano, caso não for atualizado, o cadastro é excluído.

o Orçamento e precificação podem ser realizadas presencialmente ou digitalmente.

 
## 9. Restrições e políticas organizacionais 

Apenas a Dona do estabelecimento vai fazer essas restrições. 
 
##	 	1	0	.	 	F	l	u	x	o	g	r	a	m	a	s 

                  [ INÍCIO ]
                      |
                      v
          +-----------------------+
          | Cliente realiza pedido|
          +-----------------------+
                      |
                      v
          < Há disponibilidade na agenda? >
             |                       |
            NÃO                     SIM
             |                       |
             v                       v
        [ FIM DO               < Cliente possui cadastro? >
          PROCESSO ]              |                 |
                                 NÃO               SIM
                                  |                 |
                                  v                 |
                      +-------------------+         |
                      | Cadastrar cliente |         |
                      +-------------------+         |
                                  |                 |
                                  +--------+--------+
                                           |
                                           v
                             +---------------------------+
                             | Registrar orçamento e     |
                             | precificação              |
                             +---------------------------+
                                           |
                                           v
                              < Cliente aprova o orçamento? >
                                  |                    |
                                 NÃO                  SIM
                                  |                    |
                                  v                    v
                             [ FIM DO        +-------------------------+
                               PROCESSO ]    | Registrar pedido e      |
                                             | emitir recibo e canhoto |
                                             +-------------------------+
                                                       |
                                                       v
                                             +-------------------------+
                                             | Realizar serviço        |
                                             | (atualiza status a cada |
                                             | etapa)                  |
                                             +-------------------------+
                                                       |
                                                       v
                                             +-------------------------+
                                             | Peça pronta: deixar em  |
                                             | espera                  |
                                             +-------------------------+
                                                       |
                                                       v
                                             +-------------------------+
                                             | Avisar o cliente        |
                                             +-------------------------+
                                                       |
                                                       v
                                             < Retirada ou entrega? >
                                                 |              |
                                              ENTREGA        RETIRADA
                                                 |              |
                                                 v              v
                                   +----------------+   +-----------------+
                                   | Agendar coleta |   | Cliente mostra  |
                                   | / entrega      |   | o recibo        |
                                   +----------------+   +-----------------+
                                                 |              |
                                                 +------+-------+
                                                        |
                                                        v
                                             +-------------------------+
                                             | Realizar pagamento      |
                                             +-------------------------+
                                                        |
                                                        v
                                             +-------------------------+
                                             | Entregar o pedido       |
                                             +-------------------------+
                                                        |
                                                        v
                                             +-------------------------+
                                             | ERP dá baixa no pedido  |
                                             +-------------------------+
                                                        |
                                                        v
                                                    [ FIM ]
 
##	 	1	1	.	 	E	n	t	i	d	a	d	e	s 
CLIENTE

ORÇAMENTO

PEDIDO

FLUXO DE CAIXA

ITEM PEDIDO

FUNCIONARIO

PROCESSO

SERVIÇO

COLETA

PAGAMENTOS A RECEBER

DISPESAS 

TABELA PREÇO


##	 	1	2	.	 	A	t	r	i	b	u	t	o	s 
CLINTE:
NOME
CPF
TELEFONE
ID_CLIENTE
ENDEREÇO (RUA E BAIRRO, NUMEROS, CEP)

ORÇAMENTO:
RECIBO
CANHOTO
ID_CLIENTE (FK)

PEDIDO: 
DATA DE CONCLUSÃO
VALOR TOTAL
DATA PEDIDO
STATUS
CPF (FK)
ID_PEDIDO(PK)

FLUXO DE CAIXA: 
ENTRADA_DINHEIRO
SAIDA_DINHEIRO

ITEM PEDIDO:
PREÇO UNITARIO
QUANTIDADE
ID_PRODUTO (FK)
ID_PEDIDO (FK)

FUNCIONÁRIO: 
ID_FUNCIONARIO
NOME
CPF
CARGO (DONA)
LOGRADOURO
EMAIL

PROCESSO:
LAVAGEM
CENTRIFUGAÇÃO
RESTAURAÇÃO
SECAGEM
PASSADORIA

SERVIÇO:
ARMAZENAMENTO
EMPACOTAMENTO

COLETA:
DATA AGENDADA
ID FUNCIONÁRIO 
TURNO AGENDADO
ID PEDIDO (FK)

PAGAMENTOS A RECEBER:
FORMA DE PAGAMENTO 
VALOR TOTAL

DISPESAS:
ALUGUEL
CONTA DE ÁGUA
CONTA DE LUZ
PRODUTOS NECESSARIOS 
MANUTENÇÃO DAS MAQUINAS
MÊS, ANO REFERENTE

TABELA PREÇO:
PREÇO ITEM
ID_PRODUTO (PK)

 
## 1 3 . R e l a c i o n a m e n t o s

CLIENTE SOLICITA ORÇAMENTO

ORÇAMENTO FAZ PEDIDO

PEDIDO CRIA FLUXO DE CAIXA

FLUXO DE CAIXA GERA DESPESAS

FLUXO DE CAIXA MOVIMENTA ITEM PEDIDO

ITEM PEDIDO ABRANGE TABELA DE PREÇO

ITEM PEDIDO INCLUI FUNCIONÁRIO

FUNCIONÁRIO REALIZA PROCESSO

PROCESSO EXECUTA SERVIÇO

SERVIÇO EFETUA COLETA

COLETA EMITI PAGAMENTOS A RECEBER

 
## 1 4 . C a r d i n a l i d a d e s 

CLIENTE SOLICITA ORÇAMENTO

(1:1) (1:N)

ORÇAMENTO FAZ PEDIDO

(1:1) (1:1)

PEDIDO CRIA FLUXO DE CAIXA

(1:1) (0:1)

FLUXO DE CAIXA GERA DESPESAS

(1:N) (1:1)

FLUXO DE CAIXA MOVIMENTA ITEM PEDIDO

(1:N) (1:1

PEDIDO CONTÉM ITEM PEDIDO

(1:N) (1:N)

ITEM PEDIDO ABRANGE TABELA DE PREÇO

(1:1) (1:1)

ITEM PEDIDO INCLUI FUNCIONÁRIO

(1:N) (1:N)

FUNCIONÁRIO REALIZA PROCESSO

(1:N) (1:N)

PROCESSO EXECUTA SERVIÇO

(N:N) (1:N)

SERVIÇO EFETUA COLETA

(1:N) (1:N)

COLETA EMITI PAGAMENTOS A RECEBER

(1:N) (1:1)
 
## 1 5 . D i c i o n á r i o d e d a d o s c o n c e i t u a l 

NÃO TEVE ENTIDADE ASSOCIATIVA 
 
##	 	1	6	.	 	D	E	R 

https://miro.com/app/board/uXjVHlapI-w=/?share_link_id=174316316973
 
## 1 7 . J u s t i f i c a t i v a s t é c n i c a s 

Cliente (1,1) — Orçamento (0,N): a regra diz que um cliente pode fazer vários orçamentos, e cada orçamento pertence a um único cliente. Um cliente recém-cadastrado pode ainda não ter nenhum.

Orçamento (1,1) — Pedido (0,1): nem todo orçamento vira pedido, mas todo pedido nasce de um orçamento, como exige a regra "todo pedido deve ser registrado no sistema".

Pedido — Item_Pedido como entidade própria: um pedido tem várias peças, e cada peça guarda sua quantidade e o preço cobrado na data. Isso resolve o problema da comanda genérica e respeita a regra de no mínimo uma peça por orçamento.

Item_Pedido — Tabela_Preço: a precificação funciona somando o valor base do item ao valor do serviço. Por isso a tabela de preço existe separada, para tirar o preço da cabeça da Dona e registrá-lo.
Funcionário — Processo (N:N) e Processo — Serviço (N:N): o mesmo funcionário atua em várias etapas e uma etapa é feita por vários funcionários. Um processo atende vários serviços, e um serviço passa por vários processos. Isso permite rastrear o pedido em cada fase.

Status no Pedido: o problema central é a falta de previsibilidade. O status registra em que etapa a peça está, para que alguém de fora possa acompanhá-la.

Dados mínimos do cliente (nome, CPF, telefone e endereço): atendem à regra de cadastro obrigatório e evitam a retirada baseada só no nome.

 
## 18. Conclusão

A Lavanderia Sta. Bárbara funciona bem na prática, mas depende do conhecimento oculto da Dona sobre custos, preços e prazos. Hoje não há cadastro de clientes, os controles são todos manuais e as comandas são genéricas. Por isso, ninguém além dela consegue rastrear um pedido ou prever seu andamento.

A modelagem transforma esse conhecimento em dados organizados: cadastro de clientes, orçamentos e pedidos padronizados, tabela de preços e acompanhamento por etapas do processo. O DER foi construído a partir dos processos, dos requisitos e das regras de negócio levantados, e cada decisão tem justificativa.

Esse modelo é a base para as próximas etapas (modelo lógico, normalização e modelo físico) e permite implantar o ERP de forma gradual, começando pelo cadastro de pedidos. Os pontos ainda em aberto, como os atributos de tecido, malha e costura na precificação, podem ser refinados com a Dona nas próximas fases.
