Transação 159 - Autorizar Emissão CNH
=====================================

Objetivo
--------

Autoriza emissão de nova CNH para um condutor BINCO.

Fluxo de Dados
--------------

.. image:: 159-envio-retorno.png

**Observações** *Autorizar Emissão CNH*

**1. CPF:** Não é permitida a duplicidade de CPF, quando ocorrer, o
DETRAN deverá encaminhar ao DENATRAN para que o mesmo inclua Bloqueio (D
– Medida Administrativa) para o condutor que estiver usando
indevidamente o CPF ou PGU. Caso a Duplicidade ocorra no
File-Impedimento-Cidadão será incluído o Impedimento 0 – Medida
Administrativa.

**2. Motivo-Requerimento:** Se informado E - Nova Habilitação Permissão,
a nova Data da Primeira Habilitação do Condutor passará a ser a data da
159 (parte fixa da Transação); e a Validade-CNH será a Data da Primeira
Habilitação (data da TR159) mais um ano. Exceto se Data-Validade exame
03 ou 04 for menor que 1 ano, situação em que a menor Data-Validade será
considerada para definição da Data- Validade-CNH (neste caso menor que 1
ano).

**3.** Para condutores cuja data da transação 151 seja igual ou superior
a 06/01/2014, com Motivo de Requerimento igual E - Reinicio de Processo
e habilitação na categoria B, será cobrado o curso 34 - Simulador de
Direção Veicular.

**4. Para o Motivo Requerimento 5** – Renovação de CNH, quando o
condutor Permissionário ainda não tiver cumprido o prazo de 1 ano de
permissão, (situação de validade de Exame inferior a um ano na primeira
habilitação) será autorizada emissão de nova CNH permissão com
Data-Validade complementar de acordo com a validade do novo exame
informado. Enquanto não for cumprido o período de um ano de
Permissionário será possível emitir CNH nessa condição (Permissionário).

**5. Para o Motivo de Requerimento 5** – Existindo no Prontuário do
Condutor Exame com Categoria superior a Categoria Atual e Resultado
Reprovado, será autorizada a Emissão na Categoria Atual, desde que o
Motivo de Requerimento 5 não esteja acompanhado de outro motivo de
requerimento. Quando a Categoria nos Exames e Cursos forem superior a
Categoria-Atual e o DETRAN comandar na 159 Motivo de Requerimento 5 -
Renovação (apenas) e Categoria igual à Categoria-Atual, a CNH será
autorizada.

**6.** Para cálculo de “Processo Vencido” quando do Motivo de
Requerimento E – Reinicio de Processo a data a ser considerada para
início de contagem do tempo será a do Evento mais antigo após o bloqueio
de cassação.

**7.** Com relação ao exercício de atividade remunerada, se existir o
exame 4 com observação 15 no prontuário do condutor, deverão ser
observadas as seguintes possibilidades:

a) Existe a observação 15 na tr 159 e existe novo evento exame 4 vigente
   com observação 15 = Autoriza emissão com nova validade.

b) Existe a observação 15 na tr 159 e não existe novo evento exame 4 com
   observação 15 = Autoriza com data de validade do exame cadastrado no
   prontuário.

c) Não existe a observação 15 na tr 159 = não autoriza. O DETRAN deverá
   alterar o exame 4 retirando a observação 15 e encaminhar nova 159 sem
   a observação.

**8.** Adição/Mudança de Categoria no Exterior: Neste caso o DETRAN
deverá:

1. Solicitar Autorização Especial de Adição/Mudança no Exterior;
2. Incluir o Exame prático através da transação 181: (campos
   obrigatórios: Código-Exame, UF-Exame – sempre igual a EX,
   Categoria-Pretendida e Permitida – Igual a Categoria informada na
   Autorização Especial, Observação e Data-Exame que passa a ser
   opcional a partir de 31/05/2010);
3. Enviar a transação 159 com Motivo de Requerimento 7 ou 6 dependendo
   da situação do condutor.

**9.** Para condutores cuja data da transação 151 seja igual ou superior
a 06/01/2014 [CSJ5] , com Motivo de Requerimento igual 7 - Adição de
Categoria (somente para categoria B), será cobrado o curso 34 -
Simulador de Direção Veicular.

**10.** Os valores possíveis para o campo “Tipo de Autorização” são:

1 – Papel

2 – Papel e Digital

**11.** Campo obrigatório quando o “Tipo de Autorização” é 2 (Papel e
Digital)

.. raw:: html

   <p>

12. Nome-Condutor:

.. raw:: html

   </p>

Nos casos em que o cidadão possui nome social, o campo Nome-Condutor
trará este valor; nos casos contrários o campo Nome trará o mesmo valor
do Nome Civil constante em registro de cartório. As verificações de
duplicidade e indícios de duplicidade, de impedimento, autorizações
especiais, mandado judicial serão feitas com base no nome civil
constante na BCA e informado anteriormente pelas transações 151, 152 ou
157.

.. raw:: html

   <p>

13. Filiação afetiva 1 e 2:

.. raw:: html

   </p>

O campo Filiação afetiva será informado para que possa constar em campo
específico da CNH, sem contudo fazer parte das validações de identidade
constantes no sistema. Sendo um campo opcional, terá as mesmas regras de
validações de formato e caracteres do nome, mas não será exigida
autorização especial para alterações.

.. raw:: html

   <p style="color:#0000FF">

Filiação afetiva 1: Deverá conter o nome do pai afetivo.

.. raw:: html

   </p>

.. raw:: html

   <p style="color:#0000FF">

Filiação afetiva 2: Deverá conter o nome da mãe afetiva.

.. raw:: html

   </p>

**Consistências** *Autorizar Emissão CNH*

**I.** Após a implantação da BCA não serão autorizadas emissões para
condutores que não tiverem com os Cursos e Exames completos no
Prontuário, inclusive os de formação. Exceto para Condutor Oriundo de
PGU ou Estrangeiro ou para Eventos ocorridos antes da implantação da
BCA.

**II.** Número-Registro: existir na BINCO.

**III.** Motivo-Impedimento: inexistência de indícios de Impedimento
Cidadão em relação ao Condutor.

**IV.** Bloqueio: inexistência no Prontuário do Condutor.

**V.** Motivo-Requerimento:

**1.** 1 – Primeira Habilitação, 3 – Registro Habilitação Estrangeira, e
4 – Registro PGU inexistentes;

**2.** 2 – 2a Via somente para Situação-CNH 4 – Confirmada ou 5 – Modelo
Antigo;

**3.** 5 – Renovação de Exames: Exames com Data-Validade vigente e
Data-Exame posterior a Data- Emissão-CNH da última CNH Emitida não
cancelada;

**4.** 6 – Mudança de Categoria e 7 – Adição de Categoria:

**4.1. Categoria, Categoria-Atual, Categoria-Autorizada,
Categoria-Rebaixada, Categoria-Pretendida e Categoria-Permitida:** as
possíveis movimentações são as seguintes:

**CATEGORIAS DE CONDUTORES**

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela52">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="64"/>

.. raw:: html

   <col width="28"/>

.. raw:: html

   <col width="28"/>

.. raw:: html

   <col width="28"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="31"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="31"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   <col width="31"/>

.. raw:: html

   <col width="30"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela521">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A1">

.. raw:: html

   <p class="P3">

Atual/ Rebaixada (1)

.. raw:: html

   </p>

.. raw:: html

   <p class="P3">

Retornos (2)

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="3" style="text-align:left;width:0.647cm; " class="Tabela52_A1">

.. raw:: html

   <p class="P6">

Mudanças

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_A1">

.. raw:: html

   <p class="P23">

Adições

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="14" style="text-align:left;width:0.697cm; " class="Tabela52_A1">

.. raw:: html

   <p class="P5">

Rebaixamentos/ Retornos (2)

.. raw:: html

   </p>

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela522">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P4">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

A+B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela522">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P4">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

B

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

B

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela522">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P4">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

C

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

C

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela522">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P14">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P7">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

D

.. raw:: html

   </p>

.. raw:: html

   <p class="P50">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P50">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P23">

D

.. raw:: html

   </p>

.. raw:: html

   <p class="P50">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P50">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P24">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P24">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_A2">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela526">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P9">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P8">

E

.. raw:: html

   </p>

.. raw:: html

   <p class="P36">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P36">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.684cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P8">

E

.. raw:: html

   </p>

.. raw:: html

   <p class="P36">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P49">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P24">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P24">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P24">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_A6">

.. raw:: html

   <p class="P26">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A13">

.. raw:: html

   <p class="P16">

AB

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B7">

.. raw:: html

   <p class="P31">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C13">

.. raw:: html

   <p class="P33">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P33">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D7">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E7">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G13">

.. raw:: html

   <p class="P31">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H13">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I13">

.. raw:: html

   <p class="P17">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J7">

.. raw:: html

   <p class="P12">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O7">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S7">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T7">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A14">

.. raw:: html

   <p class="P10">

AC

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B8">

.. raw:: html

   <p class="P33">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P33">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C14">

.. raw:: html

   <p class="P37">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P37">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D8">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E8">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G14">

.. raw:: html

   <p class="P31">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H14">

.. raw:: html

   <p class="P11">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I14">

.. raw:: html

   <p class="P45">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P45">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J8">

.. raw:: html

   <p class="P31">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K14">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L14">

.. raw:: html

   <p class="P17">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M14">

.. raw:: html

   <p class="P12">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O8">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S8">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T8">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A13">

.. raw:: html

   <p class="P10">

AD

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B9">

.. raw:: html

   <p class="P37">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P37">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D9">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E9">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G13">

.. raw:: html

   <p class="P33">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P33">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H13">

.. raw:: html

   <p class="P12">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I13">

.. raw:: html

   <p class="P45">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P45">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J9">

.. raw:: html

   <p class="P31">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K13">

.. raw:: html

   <p class="P11">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L13">

.. raw:: html

   <p class="P47">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P47">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M13">

.. raw:: html

   <p class="P31">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N13">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O9">

.. raw:: html

   <p class="P17">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P13">

.. raw:: html

   <p class="P18">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S9">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T9">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A14">

.. raw:: html

   <p class="P16">

AE

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B10">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D10">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E10">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G14">

.. raw:: html

   <p class="P37">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P37">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H14">

.. raw:: html

   <p class="P19">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I14">

.. raw:: html

   <p class="P43">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P43">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J10">

.. raw:: html

   <p class="P33">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P33">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K14">

.. raw:: html

   <p class="P12">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L14">

.. raw:: html

   <p class="P47">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P47">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M14">

.. raw:: html

   <p class="P31">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N14">

.. raw:: html

   <p class="P11">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O10">

.. raw:: html

   <p class="P47">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P47">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P10">

.. raw:: html

   <p class="P48">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P48">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q10">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R10">

.. raw:: html

   <p class="P17">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S10">

.. raw:: html

   <p class="P12">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T10">

.. raw:: html

   <p class="P12">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5211">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A13">

.. raw:: html

   <p class="P15">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B11">

.. raw:: html

   <p class="P13">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D11">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E11">

.. raw:: html

   <p class="P30">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P30">

+

.. raw:: html

   </p>

.. raw:: html

   <p class="P30">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J11">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O11">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S11">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T11">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A14">

.. raw:: html

   <p class="P16">

XB

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B12">

.. raw:: html

   <p class="P31">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C14">

.. raw:: html

   <p class="P31">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D12">

.. raw:: html

   <p class="P34">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P34">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G12">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H12">

.. raw:: html

   <p class="P12">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T12">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A13">

.. raw:: html

   <p class="P10">

XC

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B13">

.. raw:: html

   <p class="P32">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P32">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C13">

.. raw:: html

   <p class="P35">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P35">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D13">

.. raw:: html

   <p class="P39">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P39">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G13">

.. raw:: html

   <p class="P32">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P32">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H13">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I13">

.. raw:: html

   <p class="P17">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T13">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela527">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A14">

.. raw:: html

   <p class="P10">

XD

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B14">

.. raw:: html

   <p class="P35">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P35">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C14">

.. raw:: html

   <p class="P38">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P38">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G14">

.. raw:: html

   <p class="P12">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H14">

.. raw:: html

   <p class="P40">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P40">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I14">

.. raw:: html

   <p class="P44">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P44">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J14">

.. raw:: html

   <p class="P11">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K14">

.. raw:: html

   <p class="P40">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P40">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L14">

.. raw:: html

   <p class="P46">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P46">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M14">

.. raw:: html

   <p class="P11">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N14">

.. raw:: html

   <p class="P12">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O14">

.. raw:: html

   <p class="P17">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T14">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5215">

.. raw:: html

   <td style="text-align:left;width:1.455cm; " class="Tabela52_A15">

.. raw:: html

   <p class="P16">

XE

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_B15">

.. raw:: html

   <p class="P38">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P38">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.646cm; " class="Tabela52_C15">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.647cm; " class="Tabela52_D15">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:0.684cm; " class="Tabela52_E15">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_G15">

.. raw:: html

   <p class="P21">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_H15">

.. raw:: html

   <p class="P41">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P41">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_I15">

.. raw:: html

   <p class="P42">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_J15">

.. raw:: html

   <p class="P12">

D

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_K15">

.. raw:: html

   <p class="P20">

A C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_L15">

.. raw:: html

   <p class="P46">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P46">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_M15">

.. raw:: html

   <p class="P11">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_N15">

.. raw:: html

   <p class="P40">

A

.. raw:: html

   </p>

.. raw:: html

   <p class="P40">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_O15">

.. raw:: html

   <p class="P46">

X

.. raw:: html

   </p>

.. raw:: html

   <p class="P46">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_P15">

.. raw:: html

   <p class="P22">

B

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_Q15">

.. raw:: html

   <p class="P12">

A

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.697cm; " class="Tabela52_R15">

.. raw:: html

   <p class="P17">

X

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.699cm; " class="Tabela52_S15">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:0.679cm; " class="Tabela52_T15">

.. raw:: html

   <p class="P27">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

**- Categoria Atual** - Categoria da última CNH registrada no HEMI –
Histórico de emissões. Não existindo CNH no HEMI, mas tendo sido emitida
a CNH (situação de não povoamento no batimento gráficas) a categoria
Atual será a existente na BINCO, essa categoria estará em Branco no caso
de candidato.

**- Categoria Rebaixada** - Categoria de maior nível de CNH Emitida para
o Condutor e que foi Rebaixada.

**- Rebaixamentos** - Possibilidades de rebaixamentos em relação à
Categoria Atual do Condutor (última CNH do Histórico de Emissões).

**- Retornos** – possibilidades de Retornos até a Categoria de maior
nível que foi rebaixada.

**4.2.** Deverão ser atendidas as seguintes condições para Mudanças e
Adições de Categorias:

**Cursos:**

33 – Aulas Práticas 2 Rodas, para Adições A e X à Categoria Atual.

32 – Aulas Práticas 4 Rodas, para Adição de B à Categoria X ou A; e na
Mudança de Categoria.

**34 – Simulador de Direção Veicular - para condutores com data da
transação 151 igual ou superior a 06/01/2014 e adição de categoria B.**

**Exames:**

03 – Aptidão Física e Mental.

01 – Práticas de Direção Veicular 2 Rodas, para Adições A e X à
Categoria Atual.

02 – Práticas de Direção Veicular 4 Rodas, para Adição de B à Categoria
X ou A; e na Mudança de Categoria.

**Mudanças:**

-  Categoria B para C, estar 1 ano na Categoria B.

-  Categoria B para D:

   a) Categoria Atual igual a B: Estar a 2 anos na Categoria B e ter
      mais de 21 anos.

   b) Categoria Atual igual a C: Ter ficado na categoria B por 2 anos ou
      estar na categoria C a mais de 1 ano e ter 21 anos.

-  Categoria C para D, estar 1 ano na Categoria C e ter mais de 21 anos.

-  Categoria C para E, estar 1 ano na Categoria C e ter mais de 21 anos.

-  Categoria D para E, se categoria D proveniente de B vai para E com 1
   ano em D.

-  Categoria D para E, se categoria D proveniente de C, permitir.

Obs.: O prazo de carência em cada categoria para mudança só serão
cobrados para condutores com Data- primeira-habilitação posterior
03/03/2009 (implantação da BCA), nos demais casos será verificado o
tempo de habilitação.

**5. 8 – Alteração de Dado:**

Existência de alteração em dado impresso na CNH efetivado pela transação
157 ou 181. O condutor que tiver sua única CNH cancelada e passar a ter
Situação-CNH 0-Inexistente, para a nova habilitação deverá usar o motivo
de requerimento 8-Alteração de Dados. Nesse caso não será verificada a
existência de alterações de dados.

**6. 9 – Reabilitação:**

Curso 20–Reciclagem para Infratores existente.

Exame 03–Aptidão Física e Mental vigente com Data-Exame posterior a
última CNH Emitida.

Exame 01/02 - Prática de direção veicular correspondente à categoria com
Data-Exame posterior a última CNH Emitida.

Exame 04 - Avaliação psicológica com Data-Exame posterior a última CNH
Emitida.

Exame 07 – Teórico-Técnico para Reciclagem com Data-Exame posterior a
última CNH Emitida.

**7. C – CNH Definitiva:**

Exame 03 – Aptidão Física e Mental vigente.

**8. E – Nova Habilitação Permissão:**

Cursos exigidos:

31 – Aulas Teóricas – Legislação com Data-Curso posterior a última CNH
Emitida.

32/33 – Aulas Práticas correspondentes à Categoria com Data-Curso
posterior a última CNH Emitida.

**34 – Simulador de Direção Veicular - para condutores com data da
transação 151 igual ou superior a 06/01/2014 e habilitação na categoria
B.**

Exames exigidos:

01/02 – Prática Direção Veicular correspondentes à Categoria com
Data-Exame posterior a última CNH Emitida.

03 – Aptidão Física e Mental com Data-Exame posterior a última CNH
Emitida;

04 – Avaliação Psicológica com Data-Exame posterior a última CNH
Emitida;

05 – Teórico-Técnico de Formação com Data-Exame posterior a última CNH
Emitida.

**Observação:**

-  Os cursos e exames não atualizados pertinentes apenas a CNH anterior
   e que não utilizados na nova CNH, serão retirados do Prontuário e
   incluídos no HICOM, com origem transação BR.

-  Se no Bloqueio do Permissionário Cassado existir Prazo-Penalidade, a
   autorização de emissão só será possível após este prazo ser cumprido.

**9.** Deverão ser atendidas as definições do quadro abaixo, referente
às compatibilidades na informação de mais de um Motivo de Requerimento:

**MOTIVO-REQUERIMENTO X MOTIVO-REQUERIMENTOS COMPATÍVEIS**

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela53">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="368"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="51"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="51"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="51"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td colspan="10" style="text-align:left;width:8.417cm; " class="Tabela53_A1">

.. raw:: html

   <p class="P6">

MOTIVO-REQUERIMENTOXMOTIVO-REQUERIMENTOS COMPATÍVEIS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td rowspan="3" style="text-align:left;width:8.417cm; " class="Tabela53_A1">

.. raw:: html

   <p class="P3">

.. raw:: html

   </p>

.. raw:: html

   <p class="P3">

.. raw:: html

   </p>

.. raw:: html

   <p class="P3">

.. raw:: html

   </p>

.. raw:: html

   <p class="P7">

.. raw:: html

   </p>

.. raw:: html

   <p class="P8">

MOTIVOSDEREQUERIMENTOS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="9" style="text-align:left;width:1.155cm; " class="Tabela53_A1">

.. raw:: html

   <p class="P9">

MOTIVOSDEREQUERIMENTOSCOMPATÍVEIS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela533">

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B3">

.. raw:: html

   <p class="P4">

Todos (*)

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C3">

.. raw:: html

   <p class="P5">

2ª Via

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D3">

.. raw:: html

   <p class="P5">

Renovação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E3">

.. raw:: html

   <p class="P5">

Mudança

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F3">

.. raw:: html

   <p class="P5">

Adição

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G3">

.. raw:: html

   <p class="P5">

Alt. de Dados

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H3">

.. raw:: html

   <p class="P5">

Reabilitação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I3">

.. raw:: html

   <p class="P5">

Definitiva

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J3">

.. raw:: html

   <p class="P5">

Reinício de processo

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B4">

.. raw:: html

   <p class="P10">

-

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C4">

.. raw:: html

   <p class="P1">

2

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D4">

.. raw:: html

   <p class="P1">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E4">

.. raw:: html

   <p class="P1">

6

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F4">

.. raw:: html

   <p class="P1">

7

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G4">

.. raw:: html

   <p class="P1">

8

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H4">

.. raw:: html

   <p class="P1">

9

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I4">

.. raw:: html

   <p class="P1">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J4">

.. raw:: html

   <p class="P1">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A5">

.. raw:: html

   <p class="P15">

2 – 2aVia

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B5">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J5">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A6">

.. raw:: html

   <p class="P16">

5 –Renovação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B6">

.. raw:: html

   <p class="P12">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C6">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D6">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E6">

.. raw:: html

   <p class="P18">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F6">

.. raw:: html

   <p class="P19">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G6">

.. raw:: html

   <p class="P18">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H6">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I6">

.. raw:: html

   <p class="P18">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J6">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela537">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A7">

.. raw:: html

   <p class="P16">

6 –Mudança

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B7">

.. raw:: html

   <p class="P19">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C7">

.. raw:: html

   <p class="P12">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D7">

.. raw:: html

   <p class="P19">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E7">

.. raw:: html

   <p class="P18">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F7">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G7">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H7">

.. raw:: html

   <p class="P21">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I7">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J7">

.. raw:: html

   <p class="P12">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A8">

.. raw:: html

   <p class="P17">

7 –Adição

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B8">

.. raw:: html

   <p class="P20">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C8">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D8">

.. raw:: html

   <p class="P20">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E8">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F8">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G8">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H8">

.. raw:: html

   <p class="P22">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I8">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J8">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela539">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A9">

.. raw:: html

   <p class="P16">

8 –AlteraçãodeDados

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B9">

.. raw:: html

   <p class="P19">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C9">

.. raw:: html

   <p class="P12">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D9">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E9">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F9">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G9">

.. raw:: html

   <p class="P18">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H9">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I9">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J9">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5310">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A10">

.. raw:: html

   <p class="P16">

9 –ReabilitaçãoBloqueios2, 3, E ou F

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B10">

.. raw:: html

   <p class="P13">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G10">

.. raw:: html

   <p class="P23">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J10">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela531">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A11">

.. raw:: html

   <p class="P17">

C– Definitiva

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B11">

.. raw:: html

   <p class="P20">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C11">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D11">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E11">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F11">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G11">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H11">

.. raw:: html

   <p class="P22">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I11">

.. raw:: html

   <p class="P24">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J11">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5312">

.. raw:: html

   <td style="text-align:left;width:8.417cm; " class="Tabela53_A12">

.. raw:: html

   <p class="P25">

E –ReiniciodeProcessoBloqueios8ouAcomLiberação1, 3 ou6.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_B12">

.. raw:: html

   <p class="P14">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_C12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_D12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_E12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.155cm; " class="Tabela53_F12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_G12">

.. raw:: html

   <p class="P26">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_H12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.152cm; " class="Tabela53_I12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.157cm; " class="Tabela53_J12">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

N – Não se aplica, P – Opcional (*) As células em branco assumem o mesmo
conteúdo de Todos da sua linha.

**10.** Um Motivo-Requerimento, para ser aceito, deverá estar de acordo
com as mudanças efetivadas em atributos impressos na CNH pertinentes a
esse Motivo, e referentes aos dados da última CNH registrada no HEMI. No
quadro a seguir estão essas relações de pertinência:

**EMISSÃO DE NOVA CNH - MOTIVO-REQUERIMENTO X MUDANÇAS DE ATRIBUTOS
IMPRESSOS NA CNH**

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela54">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="229"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="50"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   <col width="49"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela541">

.. raw:: html

   <td colspan="13" style="text-align:left;width:5.242cm; " class="Tabela54_A1">

.. raw:: html

   <p class="P3">

EMISSÃODE NOVACNH-MOTIVO-REQUERIMENTOXMUDANÇASDE ATRIBUTOSIMPRESSONACNH

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela542">

.. raw:: html

   <td rowspan="2" style="text-align:left;width:5.242cm; " class="Tabela54_A1">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P5">

MOTIVOSDEREQUERIMENTOS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="12" style="text-align:left;width:1.131cm; " class="Tabela54_A1">

.. raw:: html

   <p class="P6">

MUDANÇADO ATRIBUTO

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela543">

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B3">

.. raw:: html

   <p class="P2">

Todos (*)

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C3">

.. raw:: html

   <p class="P2">

Nome Condutor

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D3">

.. raw:: html

   <p class="P2">

Nome Mãe

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E3">

.. raw:: html

   <p class="P2">

Nome Pai

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F3">

.. raw:: html

   <p class="P2">

Data Nascimento

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G3">

.. raw:: html

   <p class="P2">

CPF

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H3">

.. raw:: html

   <p class="P2">

Identidade

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I3">

.. raw:: html

   <p class="P2">

Data Validade CNH

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J3">

.. raw:: html

   <p class="P2">

Observações

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K3">

.. raw:: html

   <p class="P2">

Especialização Atualiza Cursos

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L3">

.. raw:: html

   <p class="P2">

UF

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

Habilitação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M3">

.. raw:: html

   <p class="P2">

Categoria

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela544">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A4">

.. raw:: html

   <p class="P7">

2. – 2aVia

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B4">

.. raw:: html

   <p class="P10">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M4">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela545">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A5">

.. raw:: html

   <p class="P8">

5 –Renovação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B5">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C5">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D5">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E5">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F5">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G5">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H5">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I5">

.. raw:: html

   <p class="P12">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J5">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K5">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L5">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M5">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela542">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A6">

.. raw:: html

   <p class="P8">

6 –Mudança

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B6">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C6">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D6">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E6">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F6">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G6">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H6">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I6">

.. raw:: html

   <p class="P12">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J6">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K6">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L6">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M6">

.. raw:: html

   <p class="P14">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela547">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A7">

.. raw:: html

   <p class="P9">

7 –Adição

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B7">

.. raw:: html

   <p class="P10">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C7">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D7">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E7">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F7">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G7">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H7">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I7">

.. raw:: html

   <p class="P16">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J7">

.. raw:: html

   <p class="P15">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K7">

.. raw:: html

   <p class="P15">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L7">

.. raw:: html

   <p class="P15">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M7">

.. raw:: html

   <p class="P15">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela542">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A8">

.. raw:: html

   <p class="P8">

8 –AlteraçãoDado

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B8">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M8">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela542">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A9">

.. raw:: html

   <p class="P8">

9 –-Reabilitação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B9">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C9">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D9">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E9">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F9">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G9">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H9">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I9">

.. raw:: html

   <p class="P12">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J9">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K9">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L9">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M9">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5410">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A10">

.. raw:: html

   <p class="P9">

C –Definitiva

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B10">

.. raw:: html

   <p class="P10">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I10">

.. raw:: html

   <p class="P13">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M10">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela542">

.. raw:: html

   <td style="text-align:left;width:5.242cm; " class="Tabela54_A11">

.. raw:: html

   <p class="P8">

E–ReinicioProcesso

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_B11">

.. raw:: html

   <p class="P11">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.125cm; " class="Tabela54_C11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_D11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_E11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_F11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_G11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_H11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_I11">

.. raw:: html

   <p class="P12">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.136cm; " class="Tabela54_J11">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_K11">

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_L11">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.131cm; " class="Tabela54_M11">

.. raw:: html

   <p class="P14">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

N – Não se Aplica, P – Opcional, O – Obrigatório (*) As células em
branco assumem o mesmo conteúdo de Todos da sua linha.

**Obs.:**

-  No Motivo-Requerimento 8 – Alteração de Dado, pelo menos um dos
   atributos Opcionais deverá ter sido mudado.

-  Na Reabilitação a mudança de Categoria somente poderá ocorrer para
   Rebaixamento e Retorno.

-  Se a CNHdo Condutor estiver vencida, o DETRAN deverá enviar a
   transação com o Motivo de Requerimento 5 – Renovação de Exames.

**1. Situação-CNH:** Deverá ser igual a 0-Inexistente, 4-Confirmada,
5-Modelo Antigo, ou 6-Alterada. As mudanças deverão ser de acordo com o
quadro a seguir:

**SITUAÇÃO-CNH E MUDANÇAS POSSÍVEIS**

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" width="70%" class="Tabela55">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="117"/>

.. raw:: html

   <col width="183"/>

.. raw:: html

   <col width="75"/>

.. raw:: html

   <col width="74"/>

.. raw:: html

   <col width="75"/>

.. raw:: html

   <col width="74"/>

.. raw:: html

   <col width="75"/>

.. raw:: html

   <col width="74"/>

.. raw:: html

   <col width="75"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela551">

.. raw:: html

   <td colspan="2" style="text-align:left;width:2.685cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P4">

SITUAÇÃO-CNH

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="7" style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P5">

SITUAÇÃO-CNHXTRANSAÇÃORECEBIDA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela552">

.. raw:: html

   <td rowspan="2" style="text-align:left;width:2.685cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P8">

ÚLTIMATR RECEBIDA

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

\**\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td rowspan="2" style="text-align:left;width:4.193cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P9">

.. raw:: html

   </p>

.. raw:: html

   <p class="P11">

ATUAL

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_C2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

INEXISTENTE

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_D2">

.. raw:: html

   <p class="P2">

EMISSÃO AUTORIZADA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_E2">

.. raw:: html

   <p class="P2">

EM EMISSÃO

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_F2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

EMITIDA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_G2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

CONFIRMADA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_H2">

.. raw:: html

   <p class="P2">

MODELO ANTIGO

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_I2">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

ALTERADA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela553">

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_C3">

.. raw:: html

   <p class="P12">

0

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_D3">

.. raw:: html

   <p class="P14">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_E3">

.. raw:: html

   <p class="P68">

2

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_F3">

.. raw:: html

   <p class="P68">

3

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_G3">

.. raw:: html

   <p class="P68">

4

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_H3">

.. raw:: html

   <p class="P68">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_I3">

.. raw:: html

   <p class="P68">

6

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela554">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A4">

.. raw:: html

   <p class="P18">

(1)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

152, 176

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

176c,177

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

177c,181

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_B4">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P16">

.. raw:: html

   </p>

.. raw:: html

   <p class="P25">

0-INEXISTENTE

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_C4">

.. raw:: html

   <p class="P13">

(2)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

152

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_D4">

.. raw:: html

   <p class="P15">

.. raw:: html

   </p>

.. raw:: html

   <p class="P26">

(3)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

155

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

159

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_E4">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_F4">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_G4">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_H4">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_I4">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela555">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P18">

(4)

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

155

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

159

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P32">

.. raw:: html

   </p>

.. raw:: html

   <p class="P33">

1-EMISSÃOAUTORIZADA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P13">

(5)

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

176

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P27">

(6)

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

152

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

(7)

.. raw:: html

   </p>

.. raw:: html

   <p class="P20">

171

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

(8)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P26">

(9)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P34">

(10)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

177

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela556">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A6">

.. raw:: html

   <p class="P21">

(11)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

171

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_B6">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P48">

2-EM EMISSÃO

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_C6">

.. raw:: html

   <p class="P49">

(12) 176c

.. raw:: html

   </p>

.. raw:: html

   <p class="P51">

177c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_D6">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_E6">

.. raw:: html

   <p class="P35">

(13)

.. raw:: html

   </p>

.. raw:: html

   <p class="P43">

152

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_F6">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P34">

(14)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

172

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_G6">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

(15)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_H6">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P26">

(16)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_I6">

.. raw:: html

   <p class="P6">

.. raw:: html

   </p>

.. raw:: html

   <p class="P50">

(17) 177c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela557">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P22">

(18)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

172

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P52">

.. raw:: html

   </p>

.. raw:: html

   <p class="P53">

3-EMITIDA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P37">

(19)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P54">

(20) 174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P36">

(21)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P3">

(22)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

180

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P28">

(23)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P37">

(24)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela558">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A8">

.. raw:: html

   <p class="P19">

(25)

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

180

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_B8">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P7">

.. raw:: html

   </p>

.. raw:: html

   <p class="P55">

4-CONFIRMADA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_C8">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P38">

(26)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_D8">

.. raw:: html

   <p class="P29">

(27)

.. raw:: html

   </p>

.. raw:: html

   <p class="P56">

159*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P57">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_E8">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_F8">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_G8">

.. raw:: html

   <p class="P59">

(28)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

181

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_H8">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P30">

(29)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_I8">

.. raw:: html

   <p class="P39">

(30)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P44">

181

.. raw:: html

   </p>

.. raw:: html

   <p class="P45">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela559">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P18">

(31)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

180

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P24">

177*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P60">

5-MODELOANTIGO

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P40">

(32)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P15">

.. raw:: html

   </p>

.. raw:: html

   <p class="P26">

(33)

.. raw:: html

   </p>

.. raw:: html

   <p class="P56">

159*\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P58">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P15">

.. raw:: html

   </p>

.. raw:: html

   <p class="P34">

(34)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P43">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_A1">

.. raw:: html

   <p class="P41">

(35)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P44">

181

.. raw:: html

   </p>

.. raw:: html

   <p class="P46">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5510">

.. raw:: html

   <td style="text-align:left;width:2.685cm; " class="Tabela55_A10">

.. raw:: html

   <p class="P18">

(36)

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P61">

181

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

181

.. raw:: html

   </p>

.. raw:: html

   <p class="P23">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:4.193cm; " class="Tabela55_B10">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P17">

.. raw:: html

   </p>

.. raw:: html

   <p class="P62">

6-ALTERADA

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_C10">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_D10">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P10">

.. raw:: html

   </p>

.. raw:: html

   <p class="P34">

(37)

.. raw:: html

   </p>

.. raw:: html

   <p class="P44">

159

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.707cm; " class="Tabela55_E10">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_F10">

.. raw:: html

   <p class="P66">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_G10">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P63">

(38) 157\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P64">

181\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.702cm; " class="Tabela55_H10">

.. raw:: html

   <p class="P1">

.. raw:: html

   </p>

.. raw:: html

   <p class="P65">

(39) 157\*

.. raw:: html

   </p>

.. raw:: html

   <p class="P64">

181\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.706cm; " class="Tabela55_I10">

.. raw:: html

   <p class="P35">

(40)

.. raw:: html

   </p>

.. raw:: html

   <p class="P42">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P47">

181

.. raw:: html

   </p>

.. raw:: html

   <p class="P45">

157

.. raw:: html

   </p>

.. raw:: html

   <p class="P44">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

-  \*157 ou 181 que retornam os dados do Prontuário para a mesma posição
   da CNH emitida não cancelada.

-  \**2a via.

-  \**CNH definitiva, quando não tiver sido alterado dado da CNH do
   HEMI, exceto para 5 – Modelo Antigo.

-  \***Última transação recebida que possibilita a mudança de situação
   da CNH.

-  Transações 157 e 181 não sublinhadas mudam a Situação-CNH. Exceto se
   status da Situação-CNH for 6 – Alterada, permanecendo neste caso com
   o mesmo status. Estas transações alteram dados da CNH.

-  Transações 152, 157, e 181 sublinhadas não alteram dados da CNH
   Habilitada/Autorizada/Emitida não cancelada, não mudando, portanto, a
   Situação-CNH.

Dados que se alterados mudam a CNH atual e exige a emissão de nova CNH:

-  Nome Condutor;

-  Nome da Mãe;

-  Nome do Pai;

-  Data Nascimento;

-  CPF;

-  Identidade;

-  UF Domínio;

-  Inclusão e Substituição Atualização/Especialização que mude a
   Situação-CNH para 6;

-  Data Validade nos Exames 03 – Aptidão Física e Mental e 04 –
   Avaliação Psicológica, se altera data de Validade da CNH;

-  Observações que são impressas na CNH;

-  Alteração da Categoria no Prontuário, que conclui o processo de
   efetivação de uma nova; Categoria;

-  Data Primeira Habilitação.

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela56">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="78"/>

.. raw:: html

   <col width="119"/>

.. raw:: html

   <col width="577"/>

.. raw:: html

   <col width="48"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela561">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A1">

.. raw:: html

   <p class="P75">

Célula

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_A1">

.. raw:: html

   <p class="P76">

Transação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2" style="text-align:left;width:13.203cm; " class="Tabela56_A1">

.. raw:: html

   <p class="P77">

Descrição

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela562">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A2">

.. raw:: html

   <p class="P17">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B2">

.. raw:: html

   <p class="P17">

152

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C2">

.. raw:: html

   <p class="P78">

AlteraçãodedadosCadastrais após ocancelamentodeumaHabilitaçãoAutorizada
(176/176c).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D2">

.. raw:: html

   <p class="P79">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela563">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A3">

.. raw:: html

   <p class="P89">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B3">

.. raw:: html

   <p class="P89">

176

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C3">

.. raw:: html

   <p class="P80">

Cancelamentode umaHabilitaçãoAutorizadaantes da171.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D3">

.. raw:: html

   <p class="P80">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela564">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A4">

.. raw:: html

   <p class="P90">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B4">

.. raw:: html

   <p class="P90">

176c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C4">

.. raw:: html

   <p class="P81">

Cancelamentode umaHabilitaçãoAutorizadaapós a171eantesda172.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D4">

.. raw:: html

   <p class="P81">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela565">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A5">

.. raw:: html

   <p class="P17">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B5">

.. raw:: html

   <p class="P17">

177

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C5">

.. raw:: html

   <p class="P91">

CancelamentodeAutorizaçãodeEmissãoantesda171semexistênciadeCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D5">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela562">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A6">

.. raw:: html

   <p class="P17">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B6">

.. raw:: html

   <p class="P17">

177c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C6">

.. raw:: html

   <p class="P92">

CancelamentodeAutorizaçãodeEmissãoapósa171semexistênciadeCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D6">

.. raw:: html

   <p class="P79">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela565">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A7">

.. raw:: html

   <p class="P68">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B7">

.. raw:: html

   <p class="P68">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C7">

.. raw:: html

   <p class="P93">

ÚltimaAtualizaçãodeEvento
(181)antesdaHabilitação/AutorizaçãodeEmissão(155/159).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D7">

.. raw:: html

   <p class="P94">

Ca Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela565">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A8">

.. raw:: html

   <p class="P96">

1

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B8">

.. raw:: html

   <p class="P96">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C8">

.. raw:: html

   <p class="P97">

Cancelamentoda únicaCNHexistente
noHistóricodeEmissões(HEMI)apósa172/180.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D8">

.. raw:: html

   <p class="P82">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela562">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A9">

.. raw:: html

   <p class="P17">

2

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B9">

.. raw:: html

   <p class="P5">

152,157ou

.. raw:: html

   </p>

.. raw:: html

   <p class="P29">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C9">

.. raw:: html

   <p class="P99">

AlteraçõesdeDadosCadastrais/Eventosaceitassemrestriçõesa
qualquermomento.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D9">

.. raw:: html

   <p class="P94">

Ca Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela565">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A10">

.. raw:: html

   <p class="P68">

3

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B10">

.. raw:: html

   <p class="P68">

155

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C10">

.. raw:: html

   <p class="P101">

Habilitação(após o
prontuárioestarcomtodasasinformaçõesexigidaseatualizadasconformeMotivo-Requerimento).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D10">

.. raw:: html

   <p class="P83">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela565">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A11">

.. raw:: html

   <p class="P102">

3

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B11">

.. raw:: html

   <p class="P102">

159

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C11">

.. raw:: html

   <p class="P103">

AutorizaçãodaEmissãoapós
oprontuárioestarcomtodasasinformaçõesexigidaseatualizadasconformeMotivo-Requerimento.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D11">

.. raw:: html

   <p class="P84">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela564">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela56_A12">

.. raw:: html

   <p class="P90">

4

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela56_B12">

.. raw:: html

   <p class="P90">

155

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela56_C12">

.. raw:: html

   <p class="P81">

Habilitação.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela56_D12">

.. raw:: html

   <p class="P81">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

.. raw:: html

   <p class="P137">

.. raw:: html

   </p>

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela57">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="78"/>

.. raw:: html

   <col width="119"/>

.. raw:: html

   <col width="577"/>

.. raw:: html

   <col width="48"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

4

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

159

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

AutorizaçãodaEmissão.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela572">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

4

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P105">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa172/180 (Motivo deCancelamentoB – ErroGráfica).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela573">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P106">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P106">

176

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P85">

CancelamentodaHabilitação(155)antesda171.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P85">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

177

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P107">

CancelamentodaAutorizaçãodaEmissão(159)antes
da171semexistênciadeCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela575">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

6

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P5">

152,157ou

.. raw:: html

   </p>

.. raw:: html

   <p class="P29">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P99">

AlteraçõesdeDadosCadastrais/Eventosaceitassemrestriçõesa
qualquermomento(nãoalteramdados daCNHautorizada).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P94">

Ca Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

7

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

171

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P108">

SolicitaçãodeEmissão
pelaGráficaapósHabilitação/AutorizaçãoEmissão/CancelamentoGráfica
(155/159/174G).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P95">

Ca Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

8

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P109">

177*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P112">

CancelamentoapósaAutorizaçãodaEmissão (159)deuma 2ª ViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela575">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

9

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P109">

177*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P112">

CancelamentoapósaAutorizaçãodaEmissão (159)deuma 2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

10

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

177

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P113">

CancelamentoapósaAutorizaçãodaEmissão
(159)eexistindoCNHnoHistóricodeEmissão(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

11

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

171

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P79">

SolicitaçãodeEmissão pelaGráfica.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P94">

Ca Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P90">

12

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P90">

176c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P81">

CancelamentodaHabilitação(155)apósa171.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P81">

Ca

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela575">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

12

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

177c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P114">

CancelamentodaAutorizaçãodaEmissão(159)após
a171semexistênciadeCNHnoHistóricode Emissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

13

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P6">

152,157ou

.. raw:: html

   </p>

.. raw:: html

   <p class="P29">

181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P99">

AlteraçõesdeDadosCadastrais/Eventosaceitassemrestriçõesa
qualquermomento(nãoalteramdados da CNHautorizada).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

14

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P17">

172

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P79">

InformaçãopelaGráficadaConclusãodaEmissão daCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P95">

Ca Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela573">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P90">

15

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P115">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P81">

Cancelamentoapósa171 deuma 2ª ViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P81">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

16

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P116">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa171 deuma 2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

17

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

177c

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P119">

Cancelamentoapósa171 eexistindoCNHnoHistóricodeEmissão(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

18

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

172

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

InformaçãopelaGráficadaConclusãodaEmissão daCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

19

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P97">

Cancelamentoda únicaCNHexistente noHistóricodeEmissões(HEMI)apósa172.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

20

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P105">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa172 (Motivo deCancelamentoB –ErroGráfica).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

21

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P120">

157ou 181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P99">

AlteraçõesdeDadosCadastrais/Eventosaceitassemrestriçõesa
qualquermomento(nãoalteramdados da CNHautorizada).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela573">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

22

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P110">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa172 deuma 2ª ViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

22

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

180

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P123">

InformarNúmero-Registro/Número-Formulário-CNH
aoDETRANapósa172,ConclusãodaEmissão daCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

23

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P110">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa172 deuma 2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela574">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

24

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P68">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P124">

Cancelamentoapósa172quandoexistirmaisde
umaCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela571">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

25

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

180

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

InformarNúmero-Registro/Número-Formulário-CNH aoDETRAN.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela572">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P89">

25

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P110">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Cancelamento2ªViaModelo Atual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela57_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

.. raw:: html

   <p class="P137">

.. raw:: html

   </p>

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela58">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="78"/>

.. raw:: html

   <col width="119"/>

.. raw:: html

   <col width="577"/>

.. raw:: html

   <col width="48"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

25

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P110">

177*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

CancelamentoAutorização da Emissão(159)de2ªViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P68">

25

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P117">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P125">

CancelamentoAutorização daEmissão(159)após a171de2ª ViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P96">

26

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P96">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P97">

Cancelamentoda únicaCNHexistente noHistóricodeEmissões(HEMI)apósa180.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P82">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P126">

27

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P111">

159*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P86">

AutorizaçãodaEmissãodeuma2ª ViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P86">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

27

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P105">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa180 (Motivo deCancelamentoB –ErroGráfica).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P68">

28

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P120">

157ou 181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P100">

AlteraçõesdeDadosCadastrais/Eventosaceitassemrestriçõesa
qualquermomento(nãoalteramdados da CNHautorizada).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

28

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P110">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa180 deuma 2ª ViaModeloAtual.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela588">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

29

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P110">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa180 deuma 2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P90">

30

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P121">

157 ou 181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P81">

AlteraçõesdeDadosCadastrais/Eventosquealterem dados daCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P81">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P96">

30

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P96">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P124">

Cancelamentoapósa180quandoexistirmaisde
umaCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P82">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P90">

31

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P90">

180

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P81">

InformarNúmero-Registro/Número-Formulário-CNH aoDETRAN.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P81">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

31

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P110">

174*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Cancelamento2ªViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela588">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

31

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P110">

177*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

CancelamentoAutorização Emissão(159)de2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5814">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

31

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P118">

177c*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P127">

CancelamentoAutorização Emissão(159) apósa171 de2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P68">

32

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P68">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P98">

Cancelamentoda únicaCNHexistente noHistóricodeEmissões(HEMI)apósa180.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P83">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela581">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P126">

33

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P111">

159*\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P86">

AutorizaçãodaEmissãodeuma2ª ViaModeloAntigo.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P86">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela588">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

33

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P105">

174G

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Cancelamentoapósa180 (Motivo deCancelamentoB –ErroGráfica).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5814">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

34

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P55">

157e181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P99">

AlteraçõesdeDadosCadastrais/Eventosaceitassemrestriçõesa
qualquermomento(nãoalteramdados da CNHautorizada).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela588">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P89">

35

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P122">

157 ou 181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

AlteraçõesdeDadosCadastrais/Eventosquealterem dados daCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P80">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5814">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

35

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P124">

Cancelamentoapósa180quandoexistirmaisde
umaCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

36

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P5">

157, 181

.. raw:: html

   </p>

.. raw:: html

   <p class="P31">

157ou181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P128">

AlteraçõesdeDadosCadastrais/Eventosquealteraramou nãodadosdaCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5814">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

36

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

174

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P129">

Cancelamentoapósa172/180 quando
existirmaisdeumaCNHnoHistóricodeEmissões(HEMI).

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P130">

37

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P130">

159

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P104">

AutorizaçãodaEmissãoapós
oprontuárioestarcomtodasasinformaçõesexigidaseatualizadasconformeMotivo-Requerimento.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P87">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5824">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P22">

.. raw:: html

   </p>

.. raw:: html

   <p class="P3">

38

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P22">

.. raw:: html

   </p>

.. raw:: html

   <p class="P131">

157\* e181\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P132">

AlteraçõesdeDadosCadastrais/Eventosquealterem dados
daCNHequevoltamaseridênticosaos daúltima
emissãoregistradanoHistóricodeEmissões –HEMI.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P22">

.. raw:: html

   </p>

.. raw:: html

   <p class="P88">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5824">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P22">

.. raw:: html

   </p>

.. raw:: html

   <p class="P3">

39

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P22">

.. raw:: html

   </p>

.. raw:: html

   <p class="P131">

157\* e181\*

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P132">

AlteraçõesdeDadosCadastrais/Eventosquealterem dados
daCNHequevoltamaseridênticosaos daúltima
emissãoregistradanoHistóricodeEmissões –HEMI.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P22">

.. raw:: html

   </p>

.. raw:: html

   <p class="P88">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela582">

.. raw:: html

   <td style="text-align:left;width:1.783cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P17">

40

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:2.734cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P5">

157, 181

.. raw:: html

   </p>

.. raw:: html

   <p class="P29">

157ou181

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:13.203cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P133">

AlteraçõesdeDadosCadastrais/Eventosquealterem ou nãodadosdaCNH.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.088cm; " class="Tabela58_A1">

.. raw:: html

   <p class="P79">

Co

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

Ca: Candidato

Co: Condutor

1.  CPF: válido em relação à Base de Óbitos (INSS). (Ainda não
    implementado)

2.  CPF: válido em relação à Base da Receita Federal. (Ainda não
    implementado)

3.  UF-Origem-Transação: igual à UF-Domínio do Condutor.

4.  Data-Validade: quando obrigatório, deve estar vigente para os Cursos
    e Exames exigidos, em conformidade com os Motivo-Requerimento
    informados. O Exame 03 – Aptidão Física e Mental deverá estar
    vigente para todo os Motivo-Requerimento.

5.  Validade-CNH: vencida há mais de 5 anos será exigido um novo Curso
    30–Atualização para Renovação da CNH.

6.  Categoria-Autorizada: será a maior categoria informada nos eventos
    de Curso/Exame que preencher todos os requisitos necessários à
    autorização da Emissão da nova CNH.

7.  Nome-Pai e “Endereço”: os dados dos atributos obrigatórios da
    transação 151, na versão BINCO Ampliada, referentes ao Nome-Pai
    (quando existente) e Endereço, deverão constar no Prontuário. Não
    constando, deverão ser incluídos pela transação 157 antes do envio
    da transação 159.

8.  Categoria: nos Cursos exigidos deverão estar compatíveis e serem
    iguais ou superiores à Categoria- Permitida mais inferior dos
    Exames.

9.  Campo OBSERVAÇÕES: dentro deste campo deverão constar as restrições
    médicas e a informação sobre o exercício de atividade remunerada,
    todos em formato padronizados e abreviados conforme Anexo II desta
    Resolução(850/2021);” (NR) Art. 3º Ficam revogados os códigos 11,
    12, 13, 14, 17, 18 e 19 previstos na TABELA DE ABREVIATURAS A SEREM
    IMPRESSAS NA CARTEIRA NACIONAL DE HABILITAÇÃO constante no ANEXO II
    da Resolução CONTRAN nº 598, de 2016. Art. 4º Esta Resolução entra
    em vigor na data de sua publicação.” Os Cursos especiais deixam de
    fazer parte do campo observações CNH.

10. Os cursos/atualizações deverão ser realizados a cada 5 anos
    independente da validade da CNH.

11. Resultado: Existindo Exame com resultado Inapto ou Inapto Temporário
    não será autorizada a Emissão da CNH.

12. Se informado a Observação 44 no Exame 03 – Aptidão Física e Mental
    será obrigatório estar registrado no Prontuário do Condutor Exame
    Prático de Direção 02 rodas com data posterior a do Exame 03.

13. Se informado a Observação 45 no Exame 03 – Aptidão Física e Mental
    será obrigatório estar registrado no Prontuário do Condutor Exame
    Prático de Direção 04 rodas com data posterior a do Exame 03.

14. Se informado a Observação 46 no Exame 03 – Aptidão Física e Mental a
    Data Validade poderá ser alterado usando apenas o Motivo de
    Requerimento 8 – Alteração Dados.

15. Código-Curso X Motivo-Requerimento, e Código-Exame X
    Motivo-Requerimento: nos quadros abaixo estão condições que deverão
    estar atendidas no Prontuário, informadas via transações 181.

**CURSO X MOTIVO-REQUERIMENTO**

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela59">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="265"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   <col width="62"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela591">

.. raw:: html

   <td rowspan="3" style="text-align:left;width:6.068cm; " class="Tabela59_A1">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P21">

.. raw:: html

   </p>

.. raw:: html

   <p class="P86">

CURSOS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="9" style="text-align:left;width:1.418cm; " class="Tabela59_A1">

.. raw:: html

   <p class="P87">

MOTIVOSDEREQUERIMENTOS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela592">

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Todos (*)

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C2">

.. raw:: html

   <p class="P4">

2a. Via

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Renovação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Mudança

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Adição

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Alt. de Dados

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Reabilitação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I2">

.. raw:: html

   <p class="P4">

Reinic. Processo

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

Definitiva

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela593">

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B3">

.. raw:: html

   <p class="P43">

-

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C3">

.. raw:: html

   <p class="P28">

2

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D3">

.. raw:: html

   <p class="P114">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E3">

.. raw:: html

   <p class="P114">

6

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F3">

.. raw:: html

   <p class="P114">

7

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G3">

.. raw:: html

   <p class="P114">

8

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H3">

.. raw:: html

   <p class="P114">

9

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I3">

.. raw:: html

   <p class="P88">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J3">

.. raw:: html

   <p class="P114">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela593">

.. raw:: html

   <td style="text-align:left;width:6.068cm; " class="Tabela59_A4">

.. raw:: html

   <p class="P95">

20.ReciclagemparaInfratores

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B18">

.. raw:: html

   <p class="P43">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C18">

.. raw:: html

   <p class="P29">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D18">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E18">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F18">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G18">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H18">

.. raw:: html

   <p class="P107">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I18">

.. raw:: html

   <p class="P89">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J18">

.. raw:: html

   <p class="P83">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela5919">

.. raw:: html

   <td style="text-align:left;width:6.068cm; " class="Tabela59_A19">

.. raw:: html

   <p class="P108">

30.AtualizaçãoparaRenovaçãodaCNH

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B19">

.. raw:: html

   <p class="P91">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C19">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D19">

.. raw:: html

   <p class="P16">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E19">

.. raw:: html

   <p class="P16">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F19">

.. raw:: html

   <p class="P16">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G19">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H19">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I19">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J19">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela591">

.. raw:: html

   <td style="text-align:left;width:6.068cm; " class="Tabela59_A20">

.. raw:: html

   <p class="P95">

31.AulasTeóricas–Legislação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B20">

.. raw:: html

   <p class="P89">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I20">

.. raw:: html

   <p class="P89">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J20">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela599">

.. raw:: html

   <td style="text-align:left;width:6.068cm; " class="Tabela59_A21">

.. raw:: html

   <p class="P97">

32.AulasPráticas04 Rodas

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B21">

.. raw:: html

   <p class="P93">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C21">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D21">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E21">

.. raw:: html

   <p class="P84">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F21">

.. raw:: html

   <p class="P84">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G21">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H21">

.. raw:: html

   <p class="P109">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I21">

.. raw:: html

   <p class="P93">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J21">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela599">

.. raw:: html

   <td style="text-align:left;width:6.068cm; " class="Tabela59_A22">

.. raw:: html

   <p class="P97">

33.AulasPráticas02 Rodas

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B22">

.. raw:: html

   <p class="P93">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C22">

.. raw:: html

   <p class="P32">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D22">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E22">

.. raw:: html

   <p class="P84">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F22">

.. raw:: html

   <p class="P84">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G22">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H22">

.. raw:: html

   <p class="P109">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I22">

.. raw:: html

   <p class="P93">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J22">

.. raw:: html

   <p class="P115">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela597">

.. raw:: html

   <td style="text-align:left;width:6.068cm; " class="Tabela59_A23">

.. raw:: html

   <p class="P110">

34.SimuladordeDireçãoVeicular

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_B23">

.. raw:: html

   <p class="P94">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_C23">

.. raw:: html

   <p class="P33">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_D23">

.. raw:: html

   <p class="P85">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_E23">

.. raw:: html

   <p class="P85">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_F23">

.. raw:: html

   <p class="P85">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_G23">

.. raw:: html

   <p class="P85">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_H23">

.. raw:: html

   <p class="P94">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.418cm; " class="Tabela59_I23">

.. raw:: html

   <p class="P85">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.415cm; " class="Tabela59_J23">

.. raw:: html

   <p class="P85">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

N – Não se aplica, P – Opcional, O – Obrigatório (*) As células em
branco assumem o mesmo conteúdo de Todos da sua linha.

Obs.:

-  No Motivo de Requerimento 5 – Renovação, poderá ser informado o Curso
   30 - Atualização para Renovação da CNH ou o Exame 06 - Teórico
   Técnico para Atualização.

-  Na inexistência de registro de Curso obrigatório para condutores
   RENACH será necessária Autorização Especial do DENATRAN.

-  Para PGU os cursos não informados na transação 155 não serão
   obrigatórios na transação 159 exceto para Adição e Mudança de
   Categoria.

**EXAME X MOTIVO-REQUERIMENTO**

.. raw:: html

   <table border="0" cellspacing="0" cellpadding="0" class="Tabela60">

.. raw:: html

   <colgroup>

.. raw:: html

   <col width="295"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="52"/>

.. raw:: html

   <col width="60"/>

.. raw:: html

   </colgroup>

.. raw:: html

   <tr class="Tabela601">

.. raw:: html

   <td rowspan="3" style="text-align:left;width:6.745cm; " class="Tabela60_A1">

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P2">

.. raw:: html

   </p>

.. raw:: html

   <p class="P80">

.. raw:: html

   </p>

.. raw:: html

   <p class="P79">

EXAMES

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td colspan="10" style="text-align:left;width:1.185cm; " class="Tabela60_A1">

.. raw:: html

   <p class="P81">

MOTIVOSDEREQUERIMENTOS

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela602">

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B2">

.. raw:: html

   <p class="P4">

Todos (*)

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C2">

.. raw:: html

   <p class="P4">

2ª Via

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D2">

.. raw:: html

   <p class="P4">

Renovação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E2">

.. raw:: html

   <p class="P4">

Mudança

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F2">

.. raw:: html

   <p class="P4">

Adição

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G2">

.. raw:: html

   <p class="P4">

Alteração

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H2">

.. raw:: html

   <p class="P4">

Reabilitação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I2">

.. raw:: html

   <p class="P4">

Definitiva

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J2">

.. raw:: html

   <p class="P4">

Reinicio Proc.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K2">

.. raw:: html

   <p class="P4">

.. raw:: html

   </p>

.. raw:: html

   <p class="P4">

OBS.

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela603">

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B3">

.. raw:: html

   <p class="P16">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C3">

.. raw:: html

   <p class="P92">

2

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D3">

.. raw:: html

   <p class="P82">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E3">

.. raw:: html

   <p class="P17">

6

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F3">

.. raw:: html

   <p class="P41">

7

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G3">

.. raw:: html

   <p class="P92">

8

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H3">

.. raw:: html

   <p class="P29">

9

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I3">

.. raw:: html

   <p class="P92">

C

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J3">

.. raw:: html

   <p class="P17">

E

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K3">

.. raw:: html

   <p class="P85">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela603">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A4">

.. raw:: html

   <p class="P86">

01.PráticadeDireçãoVeicular2Rodas

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B4">

.. raw:: html

   <p class="P16">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C4">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D4">

.. raw:: html

   <p class="P40">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E4">

.. raw:: html

   <p class="P16">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F4">

.. raw:: html

   <p class="P40">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G4">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H4">

.. raw:: html

   <p class="P28">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I4">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J4">

.. raw:: html

   <p class="P16">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K4">

.. raw:: html

   <p class="P85">

1, 2, 3

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela605">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A5">

.. raw:: html

   <p class="P87">

02.PráticadeDireçãoVeicular4Rodas

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B5">

.. raw:: html

   <p class="P16">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C5">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D5">

.. raw:: html

   <p class="P40">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E5">

.. raw:: html

   <p class="P16">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F5">

.. raw:: html

   <p class="P40">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G5">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H5">

.. raw:: html

   <p class="P28">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I5">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J5">

.. raw:: html

   <p class="P16">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K5">

.. raw:: html

   <p class="P85">

1, 2, 3

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela606">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A6">

.. raw:: html

   <p class="P83">

03. AptidãoFísicaeMental

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B6">

.. raw:: html

   <p class="P77">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J6">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K6">

.. raw:: html

   <p class="P88">

4, 5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela607">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A7">

.. raw:: html

   <p class="P84">

04.AvaliaçãoPsicológica

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B7">

.. raw:: html

   <p class="P78">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C7">

.. raw:: html

   <p class="P78">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D7">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E7">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F7">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G7">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H7">

.. raw:: html

   <p class="P30">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I7">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J7">

.. raw:: html

   <p class="P78">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K7">

.. raw:: html

   <p class="P78">

5

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela607">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A8">

.. raw:: html

   <p class="P83">

05.TeóricoTécnicoFormação

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B8">

.. raw:: html

   <p class="P77">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H8">

.. raw:: html

   <p class="P27">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J8">

.. raw:: html

   <p class="P77">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K8">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela606">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A9">

.. raw:: html

   <p class="P83">

06.TeóricoTécnicoparaAtualização

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B9">

.. raw:: html

   <p class="P77">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C9">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D9">

.. raw:: html

   <p class="P39">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E9">

.. raw:: html

   <p class="P77">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F9">

.. raw:: html

   <p class="P39">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G9">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H9">

.. raw:: html

   <p class="P27">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I9">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J9">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K9">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr class="Tabela607">

.. raw:: html

   <td style="text-align:left;width:6.745cm; " class="Tabela60_A10">

.. raw:: html

   <p class="P84">

07.TeóricoTécnicoparaReciclagem

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_B10">

.. raw:: html

   <p class="P78">

P

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_C10">

.. raw:: html

   <p class="P78">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_D10">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_E10">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_F10">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_G10">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.189cm; " class="Tabela60_H10">

.. raw:: html

   <p class="P30">

O

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.187cm; " class="Tabela60_I10">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.185cm; " class="Tabela60_J10">

.. raw:: html

   <p class="P78">

N

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   <td style="text-align:left;width:1.383cm; " class="Tabela60_K10">

.. raw:: html

   <p class="P93">

.. raw:: html

   </p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

N – Não se aplica, P – Opcional, O – Obrigatório (*) As células em
branco assumem o mesmo conteúdo de Todos da sua linha.

**Observação:**

**1.** Renovação Opcional para PGU.

**2.** Alteração de Dados obrigatório se Situação-CNH igual 0 –
Inexistência.

**3.** Para os Motivos 6 e 7 pelo menos um dos Exames será obrigatório.

**4.** Exame deverá estar vigente.

[STRIKEOUT:5. A validade da CNH será definida pela menor Data-Validade
entre o Exame 03 – Aptidão Física e Mental, e Data Validade do Exame, se
informada, 04 – Avaliação Psicológica.]

**5.** A validade da CNH segundo o CTB, “Art. 159. § 10. A validade da
Carteira Nacional de Habilitação está condicionada ao prazo de vigência
do exame de aptidão física e mental.”

**6.** Quando o Motivo de Requerimento for 5 – Renovação, 6 – Mudança ou
7 adição deverá existir no Prontuário do o Exame 03 – Aptidão Física e
Mental com Data-Exame posterior a ultima emissão.

**Reaproveitamento de Imagens na 2a.via e CNH definitiva**

O reaproveitamento de imagens será passível de acontecer para dois
motivos de requerimento apenas:

**2**- 2a. via

**C**- CNH Definitiva

Para a 2a.via existindo imagem na base que já tenha passado por
aprovação automática com percentual >=90% ou aprovada manualmente as
mesmas serão reaproveitadas, sem considerar a existência de nova imagem
coletada.

Caso as mesmas não tenham passado pelo processo de validação, possuam
percentual de similaridade = 0 ou ainda a CNH base para 2a.via não
possua imagens, será exigida nova coleta de imagens.

Para CNH definitiva o reaproveitamento se dará mesmo sem a validação
facial automática ou manual, uma vez que as permissões no momento da
emissão,não possuíam foto para uso na validação facial; contudo neste
caso a preferência se dará a nova coleta de imagens, caso ela exista.

Em ambos os casos:

Desta forma havendo reaproveitamento de imagens, as imagens da CNH
anterior serão associadas a CNH desta nova emissão.

Caso a CNH anterior não possua imagens ou as mesmas não atendam aos
padrões de formato, tamanho e resolução estabelecidos ou ainda não
atendam os critérios acima para reaproveitamento, não será possível
reaproveitar a imagem e uma nova coleta deverá ser feita.

.. raw:: html

   <style type="text/css">
   .tg  {border-collapse:collapse;border-spacing:0;}
   .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;}
   .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;}
   .tg .tg-xldj{border-color:inherit;text-align:left}
   .tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
   .markdown-section{
     overflow: visible;
   }
   @media screen and (max-width: 767px) {.tg {width: auto !important;}.tg col {width: auto !important;}.tg-wrap {white-space:pre !important; overflow-x:scroll !important;}}</style>
