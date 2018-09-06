# MUC
Метрика, основанная на ссылках.
**Recall** = Для всех сущностей k_i в gold разметке K и для всех совпадающих с ними сущностями r_i в выдаче системы R считается количество потерянных ссылок и делится на количество ссылок между сущностями в разметке K. Summ_(k_i in K) (|k_i| - |p(k_i)|) / Summ_(k_i in K) (|k_i| - 1) . p(k_i) - пересечение ссылок k_i и r_i
**Precision** = количество ссылок которые есть в R но нет в K, делённое на количество ссылок в R. по сути - recall с заменой k_i на r_i
$inline$
 - Для muc нет разницы, если добавлена неправильная ссылка между двумя одиночными сущностями или двумя сущностями, имеющими кучу других связей. Хотя во втором случае, эта ошибка гораздо серьёзней.
 - Метрика чрещмерно поощряет соединение сущностей, если соединить все правильно выделенные сущности между собой, MUC recall может быть 100%, и F1 соответственно тоже будет завышена.
# B^3
B-cubed is entity-oriented cross-document coreferencing measure ([Bagga and 
Baldwin, 1998]). B-cube is a more complicated harmonic mean of recall a nd precision.
To compute B3 one needs to compute the recalli and precisioni for each mention, 
and then to take an average of these pre-recall and pre-precision values to obtain the 
overall recall and precision.
Mention precision is a number of correct elements in the system output chain 
containing the mention divided by the number of elements in the system output chain 
containing the mentioni
Mention recalli  is a number of correct elements in the system output chain con-
taining the mention divided by the number of elements in the golden standard chain 
containing the mentioni.
Hence, to compute overall recall and overall precision you need to average all 
mention recalls and mention precision respectively.
# CEAF
In [Luo 2005] it was shown the main problem of B3 algorithm: B3 may use all chains 
more than once when computing recall and precision. Luo proposes 2 metrics which 
aligns entities in golden standard and system output. First of all CEAF requires the estab-
lishing of all one-to-one corresponding alignments between the chains in G(d) and the 
chain s in S(d). CEA F uses the funct ion j to compute t he similarit y between Gi and Sj where 
Gi and Sj are the chains from golden standard and system output respectively. Further-
more, the algorithm proposes the best alignment using the Kuhn-Munkres algorithm 
## CEAF_M
## CEAF_E

 - Which Coreference Evaluation Metric Do You Trust? A Proposal for a Link-based Entity Aware Metric (https://www.aclweb.org/anthology/P16-1060)
 - Evaluation Metrics For End-to-End Coreference Resolution Systems (http://www.aclweb.org/anthology/W10-4305)