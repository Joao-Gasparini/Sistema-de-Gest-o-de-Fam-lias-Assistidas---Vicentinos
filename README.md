Sistema de Gestão de Famílias Assistidas – Vicentinos
1. Descrição do Sistema
O sistema tem como objetivo auxiliar os membros da Sociedade São Vicente de Paulo (Vicentinos) no controle das famílias atendidas em ações de assistência social.
Atualmente, o controle das famílias atendidas costuma ser feito de forma descentralizada, muitas vezes em anotações pessoais ou planilhas isoladas. Isso pode ocasionar situações em que duas ou mais pessoas atendem a mesma família sem saber, gerando duplicidade de assistência.
O sistema proposto funcionará como uma plataforma centralizada, onde cada vicentino poderá registrar as famílias que acompanha, consultar famílias já cadastradas e manter um histórico de atendimentos realizados.
Dessa forma, o sistema ajuda a melhorar a organização, a comunicação entre os membros e a transparência das ações realizadas.

2. Objetivo do Sistema
Objetivo Geral

Desenvolver um sistema web para registrar, organizar e acompanhar as famílias atendidas pelos vicentinos, evitando duplicidade de atendimentos e mantendo histórico das ações realizadas.
Objetivos Específicos
Centralizar o cadastro de famílias atendidas.
Permitir que cada vicentino registre as famílias sob sua responsabilidade.
Identificar possíveis duplicidades de famílias cadastradas.
Manter histórico de atendimentos realizados.
Facilitar a consulta de famílias já assistidas.
Melhorar a organização das ações sociais.

4. Usuários do Sistema

O sistema possuirá inicialmente dois tipos de usuários:

Vicentino
Usuário comum do sistema, responsável por registrar e acompanhar as famílias atendidas.
Poderá:
realizar login no sistema
cadastrar famílias atendidas
visualizar famílias cadastradas
registrar atendimentos realizados
consultar histórico de atendimentos

Administrador
Usuário responsável pela administração do sistema.
Poderá:
gerenciar usuários vicentinos
visualizar todas as famílias cadastradas
corrigir cadastros duplicados
alterar responsável por uma família
visualizar relatórios gerais

4. Requisitos Funcionais
Os requisitos funcionais representam as funcionalidades que o sistema deverá possuir.

RF01 – Cadastro de Vicentino
O sistema deverá permitir o cadastro de usuários vicentinos contendo:
nome completo
CPF
email
telefone
senha de acesso

RF02 – Login no Sistema
O sistema deverá permitir que o usuário acesse sua conta utilizando:
email
senha

RF03 – Cadastro de Famílias
O sistema deverá permitir que o vicentino registre famílias atendidas contendo informações como:
nome do responsável pela família
CPF do responsável (quando disponível)
telefone
endereço completo
quantidade de moradores
observações

RF04 – Consulta de Famílias
O sistema deverá permitir a busca de famílias cadastradas utilizando critérios como:
nome do responsável
CPF
telefone
endereço

RF05 – Verificação de Possível Duplicidade
Antes de cadastrar uma nova família, o sistema deverá verificar se já existe cadastro semelhante com base em:
CPF
endereço
telefone
nome do responsável
Caso exista, o sistema deverá alertar o usuário.

RF06 – Registro de Atendimentos
O sistema deverá permitir registrar atendimentos realizados para uma família, contendo:
data do atendimento
vicentino responsável
tipo de atendimento
descrição ou observações

RF07 – Histórico de Atendimentos
O sistema deverá permitir visualizar o histórico completo de atendimentos realizados para cada família.

RF08 – Atualização de Cadastro
O sistema deverá permitir que os dados da família sejam editados quando necessário.

RF09 – Controle de Responsável pela Família
Cada família cadastrada deverá possuir um vicentino responsável principal, que poderá ser alterado pelo administrador.

5. Requisitos Não Funcionais
RNF01 – Interface Web
O sistema deverá ser acessível através de navegadores web.

RNF02 – Autenticação de Usuário
Somente usuários cadastrados poderão acessar o sistema.

RNF03 – Segurança de Senhas
As senhas dos usuários deverão ser armazenadas no banco de dados utilizando criptografia (hash).

RNF04 – Banco de Dados
O sistema utilizará MySQL para armazenamento das informações.

RNF05 – Desempenho
O sistema deverá permitir consultas rápidas às famílias cadastradas.

RNF06 – Simplicidade de Uso
A interface deverá ser simples e intuitiva para facilitar o uso por pessoas com diferentes níveis de familiaridade com tecnologia.

6. Regras de Negócio
RN01
Cada vicentino deve possuir um cadastro único no sistema.

RN02
Cada família deve possuir apenas um cadastro principal no sistema, mesmo que seja atendida por diferentes vicentinos ao longo do tempo.

RN03
Cada família deve possuir um vicentino responsável principal.

RN04
Uma família pode possuir vários registros de atendimento ao longo do tempo.

RN05
O sistema deverá alertar o usuário caso exista possibilidade de duplicidade no cadastro de uma família.

7. Modelo Inicial do Banco de Dados
Tabela: vicentinos
Campos:
id
nome_completo
cpf
email
telefone
senha_hash
status
data_cadastro

Tabela: familias
Campos:
id
nome_responsavel
cpf_responsavel
telefone_principal
telefone_secundario
endereco
numero
complemento
bairro
cidade
cep
ponto_referencia
quantidade_moradores
observacoes
status
data_cadastro
vicentino_id

Tabela: atendimentos
Campos:
id
familia_id
vicentino_id
data_atendimento
tipo_atendimento
descricao
observacoes
data_registro

8. Tecnologias Utilizadas
O sistema poderá ser desenvolvido utilizando as seguintes tecnologias:
Backend
Python
Flask
SQLAlchemy
Banco de Dados
MySQL
Frontend
HTML
Bootstrap
JavaScript
