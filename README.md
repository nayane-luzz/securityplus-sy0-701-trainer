# Security+ SY0-701 Trainer

Simulador de estudo para a certificação **CompTIA Security+ (SY0-701)**, em português, em uma única página HTML, sem backend e sem dependências.

## Funcionalidades

- **Modo Estudo**: correção imediata, com a explicação da resposta certa e de cada alternativa errada.
- **Modo Simulado**: correção só no final, com cronômetro de 1 minuto por questão, como no exame real (90 questões em 90 minutos).
- **Nota estimada na escala 100–900**, com o acerto ponderado pelo peso de cada domínio do SY0-701 (12/22/18/28/20%), e marcações de aprovação (750) e meta (800).
- **Desempenho por domínio** e lista **"O que revisar"**, ordenada por taxa de erro × peso do domínio.
- **Flashcards** gerados automaticamente a partir dos erros: "Já sei" tira o card do baralho, "Revisar de novo" manda para o fim da fila.
- **Banco de erros acumulado**, opção de refazer só o que errou e histórico de notas.
- **Zerar progresso** com confirmação.
- **Importação de banco próprio** (JSON), carregado só no navegador.
- Tema claro/escuro e layout responsivo.

## Como usar

Acesse pelo GitHub Pages ou abra o `index.html` direto no navegador. O progresso fica salvo no `localStorage` do navegador.

O app vem com **questões de exemplo originais** (`data/sample-questions.json`). Para estudar com o seu próprio material, use **Banco de questões → Importar banco (.json)** na tela inicial.

> Não publique neste repositório questões de materiais protegidos por direitos autorais (livros, cursos pagos, dumps). Mantenha bancos privados fora do Git; o `.gitignore` já ignora a pasta `data/private/`.

## Plano de estudos adaptativo

O arquivo [`plano-security-plus.html`](plano-security-plus.html) é um cronograma que se refaz sozinho até a data da prova:

- distribui os 28 objetivos do SY0-701 em cinco passadas (teoria, questões, revisão em 7 dias, aprofundamento em 14 e revisão final em 21);
- mostra um painel de viabilidade e o ritmo diário necessário;
- tem botões "Não estudei hoje" e "Perdi a semana" que replanejam o restante;
- tem visão de hoje, da semana, mês a mês e um mapa de constância;
- registra questões e simulados de qualquer plataforma, com índice de acerto por domínio;
- reserva simulados completos na reta final;
- exporta e restaura os dados em JSON.

Para ajustar, edite o bloco `CFG` no início do `<script>`: `dataProva`, `capacidade` (minutos por dia, de domingo a sábado) e `metaQuestoesDia`.

## Formato do banco (JSON)

Um array de questões:

```json
[
  {
    "id": "EX1",
    "ex": "A",
    "n": 1,
    "obj": "1.1 Security Controls",
    "d": "1",
    "q": "Enunciado da questão",
    "o": { "A": "Opção A", "B": "Opção B", "C": "Opção C", "D": "Opção D" },
    "a": ["A"],
    "e": "Explicação da resposta correta",
    "w": { "B": "Por que B está errada", "C": "...", "D": "..." },
    "en_q": ""
  }
]
```

| Campo | Descrição |
|---|---|
| `id` | Identificador único |
| `ex` | Conjunto/simulado (`A`, `B`, `C`...). Use `P` para questões práticas (PBQ) adaptadas |
| `obj` | Objetivo do exame (`"2.4 Password Attacks"`) |
| `d` | Domínio (`"1"` a `"5"`) |
| `a` | Lista de letras corretas (mais de uma = "Selecione N") |
| `w` | Explicação de cada alternativa errada (opcional) |
| `en_q` | Enunciado original em outro idioma (opcional) |

## Domínios do SY0-701

1. Conceitos Gerais de Segurança (12%)
2. Ameaças, Vulnerabilidades e Mitigações (22%)
3. Arquitetura de Segurança (18%)
4. Operações de Segurança (28%)
5. Gestão e Supervisão do Programa de Segurança (20%)

## Aviso

A nota é uma estimativa: a CompTIA não divulga o cálculo exato da escala. Projeto pessoal de estudo, sem vínculo com a CompTIA. CompTIA e Security+ são marcas registradas da CompTIA, Inc.

## Licença

Código sob licença MIT.
