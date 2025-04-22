# Sistema de Gestão de Perdas na Colheita de Cana-de-Açúcar

## Problema abordado no Agronegócio

Este projeto aborda um problema crítico no agronegócio brasileiro: as perdas durante a colheita mecanizada de cana-de-açúcar. Segundo estudos da SOCICANA, essas perdas podem chegar a 15% da produção quando realizada mecanicamente, enquanto na colheita manual raramente ultrapassam 5%. 

Considerando que o Brasil é o maior produtor mundial de cana-de-açúcar, com produção que atinge cerca de 620 milhões de toneladas por safra, essas perdas representam um prejuízo significativo para o setor. Apenas no estado de São Paulo, com aproximadamente 3 milhões de hectares plantados e produtividade média de 100 toneladas por hectare, essa perda equivale a um prejuízo anual estimado em R$ 20 milhões.

Este sistema visa gerenciar e analisar os dados de colheita de cana-de-açúcar, com foco na identificação e redução das perdas durante o processo de colheita mecanizada.

## Inovação proposta

A solução desenvolvida traz inovação para o setor ao:

1. Monitorar sistematicamente as perdas por máquina e operador
2. Identificar padrões de perdas relacionados a diferentes tipos de cana
3. Gerar relatórios analíticos que ajudam na tomada de decisão
4. Propor recomendações baseadas em uma análise dos dados coletados
5. Permitir o armazenamento e consulta de dados históricos para comparação entre safras

## Requisitos técnicos atendidos

O sistema foi desenvolvido em Python, contemplando os requisitos técnicos solicitados:

### Subalgoritmos (Capítulo 3)
- **Funções**: Implementação de diversas funções como `registrar_colheita()`, `analisar_perdas()`, `carregar_colheitas_arquivo()`, etc.
- **Procedimentos**: Implementação de procedimentos como `menu_principal()`, `visualizar_colheitas()`, etc.
- **Passagem de parâmetros**: Utilização de parâmetros em diversas funções, como `salvar_colheitas_arquivo(arquivo)`, `exportar_relatorio_txt(arquivo)`, etc.

### Estruturas de dados (Capítulo 4)
- **Lista**: Utilização da lista `colheitas` para armazenar todas as colheitas registradas
- **Tupla**: Definição da tupla `tipos_cana` com os diferentes tipos de cana disponíveis
- **Dicionário**: Uso de dicionários para representar cada colheita e para agregar estatísticas por máquina
- **Tabela de memória**: Gerenciamento de dados em memória através das estruturas acima

### Manipulação de arquivos (Capítulo 5)
- **Texto**: Exportação de relatórios em formato TXT através da função `exportar_relatorio_txt()`
- **JSON**: Persistência dos dados em formato JSON através das funções `salvar_colheitas_arquivo()` e `carregar_colheitas_arquivo()`

### Conexão com banco de dados Oracle (Capítulo 6)
- Implementação de conexão com banco Oracle através da biblioteca `cx_Oracle`
- Funções para criar tabelas, salvar e carregar dados do banco: `conectar_banco()`, `criar_tabelas()`, `salvar_colheita_banco()`, `carregar_colheitas_banco()`

## Como usar

1. Execute o script principal:
```
python sistema_gestao_cana.py
```

2. No menu principal, você pode:
   - Registrar uma nova colheita
   - Visualizar as colheitas registradas
   - Analisar perdas e obter recomendações
   - Exportar relatórios em formato TXT
   - Salvar e carregar dados em arquivos JSON
   - Acessar operações com banco de dados Oracle

## Configuração do Banco de Dados

Para utilizar as funcionalidades de banco de dados, é necessário:

1. Instalar a biblioteca cx_Oracle:
```
pip install cx_Oracle
```

2. Configurar os dados de conexão no arquivo principal, modificando:
```python
conn = cx_Oracle.connect(
    user="username",
    password="password",
    dsn="localhost:1521/orcl"
)
```

## Notas adicionais

- O sistema permite o uso offline (com arquivos JSON) ou conectado ao banco Oracle
- Validações são realizadas em todas as entradas do usuário para evitar erros
- Os relatórios gerados podem ajudar a identificar máquinas com desempenho abaixo do esperado
- As recomendações são baseadas em limites definidos para perdas aceitáveis (10%)

## Contribuições futuras

O sistema pode ser expandido para incluir:
- Interface gráfica para facilitar o uso
- Visualizações gráficas das perdas por máquina/período
- Integração com sensores IoT nas colhedoras para coleta automática de dados
- Algoritmos de machine learning para prever perdas com base em condições climáticas
