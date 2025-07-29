# 🔧 Sistema de Gestão de Ordens de Serviço - Oficina Mecânica

## 🧾 Descrição do Projeto
Este repositório apresenta o modelo conceitual para um **Sistema de Controle e Gerenciamento de Ordens de Serviço** em uma oficina mecânica. A modelagem foi realizada com base em uma narrativa descritiva fornecida como desafio, contemplando todas as entidades e relacionamentos principais envolvidos no processo.

## 🧩 Contexto da Narrativa
- Clientes levam **veículos** à oficina para manutenção ou revisões.
- Cada veículo é designado a uma **equipe de mecânicos** que inspeciona e gera uma **ordem de serviço (OS)**.
- A OS possui **data de emissão, status, valor e data prevista para conclusão**.
- Os serviços são definidos com base em uma tabela de **referência de mão de obra** e podem incluir **peças**.
- Os serviços e peças compõem o custo final da OS.
- A equipe é responsável tanto por identificar quanto por executar os serviços.
- Cada **mecânico** possui código, nome, endereço e especialidade.

## 🗃️ Entidades do Modelo
- **Cliente**: id_cliente, nome, telefone, email
- **Veículo**: id_veiculo, placa, modelo, ano, id_cliente
- **Equipe**: id_equipe, nome
- **Mecânico**: id_mecanico, nome, endereço, especialidade, id_equipe
- **Ordem de Serviço (OS)**: id_os, data_emissao, data_conclusao, valor_total, status, id_veiculo, id_equipe
- **Serviço**: id_servico, descrição, valor_mao_obra
- **Peça**: id_peca, descrição, preço
- **Serviço Executado**: id_os, id_servico, quantidade
- **Peça Utilizada**: id_os, id_peca, quantidade

## 🔗 Relacionamentos
- Um **cliente** pode possuir vários **veículos** (1:N)
- Um **veículo** pode gerar várias **ordens de serviço** (1:N)
- Uma **equipe** pode ser atribuída a várias **OSs** (1:N)
- Uma **equipe** pode ter vários **mecânicos** (1:N)
- Uma **OS** pode conter vários **serviços executados** e **peças utilizadas** (1:N)

## 🖼️ Diagrama Conceitual
O modelo foi representado no seguinte arquivo:
```
/docs/oficina_modelo_conceitual.png
```

## 📁 Estrutura do Repositório
```
/oficina-os/
|-- /docs/                   # Diagramas e modelagens
|-- /sql/                    # Scripts SQL (opcional)
|-- README.md                # Este documento
```

## ⚙️ Observação
Alguns dados não foram explicitamente definidos na narrativa (ex: telefone de cliente, modelo do veículo), mas foram adicionados para enriquecer a representação e funcionalidade do sistema.

---

**Fylipe Araújo**
