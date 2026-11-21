# Banco de questões com gabaritos — Petrobras, Transpetro e ANSA

## Arquivos principais
- `banco_questoes_operacao_dutos_app.json`: banco integral, com texto, alternativas, classificação, fonte, localização no PDF e gabarito.
- `correlacao_questoes_app.json`: mapa de junção entre questões, conteúdo programático, Pareto e gabarito.
- `questoes_operacao_dutos_app.jsonl`: uma questão JSON por linha, para ingestão em lote.
- `banco_questoes_operacao_dutos_app.txt`: espelho textual do JSON principal.
- `gabaritos_extraidos_270_questoes.json`: gabaritos isolados por prova.
- `gabaritos_extraidos_270_questoes.csv`: tabela plana em UTF-8 com BOM, separador ponto e vírgula.

## Como ler o gabarito
- CESGRANRIO / múltipla escolha: `correct_option_label` contém A–E e `correct_option_text` contém o texto extraído da alternativa correta.
- CEBRASPE / certo ou errado: `correct_judgment` contém `CERTO` ou `ERRADO`; `answer_key.value` conserva a marca original C/E do gabarito.
- Questão anulada: `answer_key.status = annulled`, `correct_answer = ANULADA` e `answer_key.value = null`. Não atribuir alternativa correta nem contabilizar como item com resposta válida.

## Status e ressalvas de fonte
- Transpetro 2018 Operação: gabarito alterado em 09/05/2018.
- Petrobras 2023.1 Operação (Ênfase 7): o arquivo recebido é identificado como gabarito oficial preliminar.
- Petrobras 2023.2 Operação (Ênfase 8): gabarito oficial definitivo. Itens X foram marcados como anulados.
- Transpetro 2023.1 Dutos e Terminais (Prova 2): questão 49 alterada para E após recursos; a tabela original apresentava C e foi preservado em `previous_value`.
- ANSA 2026 Operação (Ênfase 22): o arquivo recebido é identificado como gabarito oficial preliminar.

## Chaves de integração
Use `question_id` como identificador estável. Para localizar por contexto, use a chave composta `exam_id + question_number` ou `app_lookup_key`. Nunca use apenas o número da questão, pois a numeração se repete entre provas.

## Cobertura
270 registros: 5 provas distintas. Cada registro foi associado a um valor/status de gabarito. A prova Petrobras 2023.1 e a ANSA mantêm o status preliminar porque esse é o status que consta nos PDFs fornecidos.
