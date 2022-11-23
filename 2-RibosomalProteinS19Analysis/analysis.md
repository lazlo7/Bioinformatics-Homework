# Протеин: Ribosomal Protein S19  

## Исходные данные
1\. `fasta` файл с аминокислотными последовательностями генов находится в `./files/sequences.fasta`  

## Выравнивания
2\. Выравнивание через ClustalW и Muscle.  
![Выравнивание через ClustalW](./pics/sequences_aligned_clustalw.png "ClustalW")
![Выравнивание через Muscle](./pics/sequences_aligned_muscle.png "Muscle")
Есть ли разница в выравниваниях? Да, есть.  

## Филогенетические деревья
3\. Для алгоритма Maximum Likelihood использовалось bootstrap-значение = 200 (для более быстрого выполнения).    
Для остальных алгоритмов использовалось bootstrap-значение = 500.  
Для получения детальных картинок деревьев использовалась программа `FigTree` (построенные деревья экспортировались из `MEGA`, использовался `Newick` формат).  
В `./pics` дополнительно представлены `bootstrap consensus tree` после постройки филогенетического дерева.

ClustalW.  
UPGMA:
![ClustalW: UPGMA](./pics/tree_clustalw_upgma_original.jpg "ClustalW: UPGMA")
NJ:
![ClustalW: NJ](./pics/tree_clustalw_nj_original.jpg "ClustalW: NJ")
ML:
![ClustalW: ML](./pics/tree_clustalw_ml_original.jpg "ClustalW: ML")

Muscle.  
UPGMA:
![Muscle: UPGMA](./pics/tree_muscle_upgma_original.jpg "Muscle: UPGMA")
NJ:
![Muscle: NJ](./pics/tree_muscle_nj_original.jpg "Muscle: NJ")
ML:
![Muscle: ML](./pics/tree_muscle_ml_original.jpg "Muscle: ML")

## Выводы
Q: Какой алгоритм выравнивания лучше сработал - `ClustalW` или `Muscle`?  
A: В общем, чуть лучшие выравнивания получил алгоритм `Muscle` (взять, например, `ClustalW/Neighbor-Joining` и `Muscle/Neighbor-Joining`, в последнем bootstrap-значения получились, в среднем, выше).

Q: Одинаковая ли получилась топология деревьев при построении разными методами?  
A: Топологии деревьев различаются. Например, в `ClustalW/UPGMA` Lizard и Turtle расположены ближе, чем в `ClustalW/Neighbor-Joining`

Q: Одинаковые ли получились бутстрэп-значения?  
A: bootstrap-значения получились разные.

Q: Совпадают ли деревья, построенные по одному гену с принятыми деревьями видов?  
A: Нет, не совпадают. Например, в `ClustalW/Neighbor-Joining` Zooteca Vivipara (Живородящая ящерица, пресмыкающиеся) расположена ближе к Antechinus flavipes (Желтоногая сумчатая мышь, млекопитающие), чем к Gopherus flavomarginatus (Мексиканский гофер, пресмыкающиеся).