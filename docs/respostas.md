SGBD Relacional vs NoSQL: Escolhemos o Relacional (PostgreSQL/MySQL) pois os dados acadêmicos possuem alta criticidade de integridade. As propriedades ACID garantem que um lançamento de nota (Score_Final) não seja perdido ou corrompido em acessos simultâneos, e as chaves estrangeiras impedem que uma matrícula exista sem um aluno real.

Uso de Schemas: A separação em academico (dados de notas e cursos) e seguranca (acesso e e-mails) permite aplicar regras de Privacidade e Governança. Isso isola dados sensíveis dos alunos, facilitando a conformidade com leis de proteção de dados (LGPD).

Concorrência (Locks): Caso dois operadores tentem alterar o Score_Final da mesma ID_Matricula, o SGBD aplica um Lock de Linha. O primeiro a salvar "bloqueia" o registro; o segundo aguarda a conclusão da transação (Isolamento), garantindo que o valor final seja o da transação concluída por último de forma íntegra.


![alt text](<Academic Enrollment-2026-04-15-230126.png>)

