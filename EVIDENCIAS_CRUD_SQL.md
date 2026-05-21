# Evidências - INSERT, UPDATE e DELETE no banco db_em 
## Identificação 
Nome: Ana Julia
Turma: 3 ano A
Data: 21/05/26
--- 
# 1. SELECT final - Leituras do dia 2026-04-04 
Execute no DBeaver:
Trilha CRUD SQL - db_em - DBeaver 
```sql 
SELECT * 
FROM leituras 
WHERE timestamp >= '2026-04-04'  AND timestamp < '2026-04-05' 
ORDER BY timestamp ASC; 
``` 
Cole abaixo a saída obtida: 
9	EM-ARACATUBA-01	2026-04-04 08:00:00.000 -0300	23.4	76.2
10	EM-ARACATUBA-01	2026-04-04 09:00:00.000 -0300	25.2	72.0
11	EM-ARACATUBA-01	2026-04-04 10:00:00.000 -0300	25.9	70.5
--- 
# 2. SELECT final - Conferência do UPDATE Execute no DBeaver: 
```sql 
SELECT * 
FROM leituras 
WHERE station_id = 'EM-ARACATUBA-01'  AND timestamp = '2026-04-04 09:00:00'; ``` 
Cole abaixo a saída obtida: 
EM-ARACATUBA-01	10 10	2026-04-04 09:00:00.000 -0300	25.2 72
--- 
# 3. SELECT final - Conferência do DELETE Execute no DBeaver: 
```sql 
SELECT * 
FROM leituras 
WHERE station_id = 'EM-ARACATUBA-01'  AND timestamp = '2026-04-04 11:00:00'; ``` 
# 4. SELECT final - Todas as leituras ordenadas 
Execute no DBeaver: 
```sql 
SELECT * 
FROM leituras 
ORDER BY id ASC; 
``` 
Cole abaixo a saída obtida: 
1	EM-ARACATUBA-01	2026-04-01 08:00:00.000 -0300	24.5	72.1
2	EM-ARACATUBA-01	2026-04-01 09:00:00.000 -0300	25.8	69.4
3	EM-ARACATUBA-01	2026-04-01 10:00:00.000 -0300	27.2	65.8
4	EM-ARACATUBA-01	2026-04-02 08:00:00.000 -0300	23.8	73.5
5	EM-ARACATUBA-01	2026-04-02 09:00:00.000 -0300	24.6	71.2
6	EM-ARACATUBA-01	2026-04-02 10:00:00.000 -0300	25.4	68.9
7	EM-ARACATUBA-01	2026-04-02 11:00:00.000 -0300	26.1	66.4
8	EM-ARACATUBA-01	2026-04-02 12:00:00.000 -0300	27.0	63.8
9	EM-ARACATUBA-01	2026-04-04 08:00:00.000 -0300	23.4	76.2
10	EM-ARACATUBA-01	2026-04-04 09:00:00.000 -0300	25.2	72.0
11	EM-ARACATUBA-01	2026-04-04 10:00:00.000 -0300	25.9	70.5
--- 
# 5. Teste pela API 
Acesse no navegador: 
```text 
http://localhost:3000/api/leituras/data/2026-04-04 
``` 
Cole abaixo o resultado retornado pela API: 
{
  "mensagem": "API Estação Meteorológica",
  "descricao": "API para consulta de leituras meteorológicas armazenadas no PostgreSQL.",
  "rotasDisponiveis": {
    "listarTodasAsLeituras": "GET /api/leituras",
    "pesquisarLeiturasPorData": "GET /api/leituras/data/2026-04-01",
    "importarCsv": "npm run import:csv"
  },
  "formatoDaData": "YYYY-MM-DD",
  "exemploDeUso": "http://localhost:3000/api/leituras/data/2026-04-01"
}
--- 
# 6. Conclusão 
Explique com suas palavras a diferença entre INSERT, UPDATE e DELETE. Resposta: 
INSERT: usado para adi'cionar novos dados em uma tabela.
UPDATE: usado para modificar dados que já existem.
DELETE: usado para remover dados de uma tabela.