# Desafio de Projeto
## Power BI Analyst

#### *Processando e Transformando Dados com Power BI*

Relatório da base em um banco de dados MySQL criado com os servidores Xampp e Phpmyadmin, Os dados foram analisados e formatados para um melhor aproveitamento.

Foram realizados nesse projeto:
- Realizada a junção dos colaboradores e respectivos nomes dos gerentes. Isso podia ser feito com consulta SQL ou pela mescla de tabelas com Power BI. No caso a consulta foi feita por código SQL e requisitada no Power BI, mais abaixo mostro o código usado.
- Mescla das colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
- Mescla dos nomes de departamentos e localização. Para que cada combinação departamento-local seja único.

**obs_1** - Código usado:
```SQL
select concat(g.Fname, ' ', g.Lname) as 'Gerente', concat(f.Fname, ' ', f.Lname) as 'Colaborador'
FROM
    employee AS g
INNER JOIN
    employee AS f ON g.Ssn = f.Super_ssn
ORDER BY
    g.Fname, g.Lname, f.Fname, f.Lname;
```
---

**obs_2** - Os códigos *script_db.sql* e *dados.sql* não são de autoria própria, eles foram fornecidos pelo programa de Análise de dados da DIO, mas foram alterados em relação ao matérial original.