# Huffman-Compression

<h3>French version below</h3>

<h1>Huffman Compression</h1>

<h2>How to use</h2>
<h2>
________________________________________________________________________________________________

<h1>Compression de Huffman</h1>

<h2>Manuel :</h2>

Pour se servir de mon programme, il faut déjà le compresser. Pour
cela, dans le répertoire du fichier Huffman.c, lancer à l'aide du terminal la
commande suivante :

          gcc Huffman.c -o Huffman.exe
  
Puis lancer le programme avec :

          ./Huffman.exe
          
Vous aurez alors un menu qui vous propose de :

    · Compresser un fichier : taper son nom avec son extension, vous obtiendrez
    en sortie le fichier compressé du même nom suivi de « .huff »
    · Décompresser un fichier : non implanté. Le but était de taper le nom du
    fichier à décompresser en .huff, et de rendre en sortie le même fichier,
    décompresser, du même nom sans l’extension .huff,
    · Quitter

<h2>Démarche :</h2>

<p>Pour développer un programme capable de compresser un fichier
selon la méthode de Huffman, j’ai pensé qu’il était mieux de procéder par
étapes. Dans un premier temps, je me suis occupé de classer les
caractères d’un fichier dans un tableau selon leurs fréquences. Une fois
cela fait, j’ai construit, pour chaque lettre existante dans le fichier, un
noeud contenant la fréquence de celle-ci. C’est alors qu’est apparue la
première difficulté : l’arbre de Huffman. J’ai la aussi procédé par étapes
pour construire cet arbre :</p>

    · Je range chacun de mes noeuds dans un tableau
    · Je trie ce tableau en fonction des occurrences des noeuds, de
    manière à mettre les noeuds avec les plus petites fréquences au
    début du tableau.
    · Je construis un nouveau noeud ayant pour fils les deux premières
    cases du tableau.
    · Je range ce nouveau noeud dans la première case du tableau, et
    dans la deuxième case je mets le dernier noeud du tableau
    · Je diminue la taille du tableau de 1.
    
<p>Et je recommence ces étapes jusqu’à n’avoir qu’un tableau de taille 1.
La partie du DM m’ayant donnée le plus de difficulté est le codage
de chacun des caractères à partir de l’arbre de Huffman. C’est après de
nombreuses recherches sur internet et d’essais manqués que j’ai trouvé
un algorithme qui marchait. Le principe est, qu’en partant de la racine de
l’arbre, je fais un décalage des bits vers la gauche à chaque fois, en
ajoutant 1 quand je descends vers une feuille via une branche à droite.
Cela me donne un nouveau code entier pour chaque lettre, que j’ai
convertie en binaire dans un fichier texte a l’aide d’une fonction de
conversion.</p>

<p>Une fois le dictionnaire écrit grâce à ces algorithmes, la compression
du fichier était assez simple. Pour chaque caractère rencontré, je cherchais
le même dans le dictionnaire, prenais son code binaire, le convertissait en
entier, puis imprimais son ‘char’ dans le fichier compressé. Quand tout le
texte était parcouru, je copiais à la fin du fichier compressé le dictionnaire,
afin de pouvoir le décompresser dans le futur.</p>

<p>La décompression m’a donné plus de mal que prévu. Autant je
réussissais à récupérer un code binaire parfaitement cohérent avec le
dictionnaire, mais je n’arrivais pas à réattribuer à chaque suite de bits le
caractère que l’arbre de Huffman avait attribués lors de la compression.
Ce que je n’ai pas pu implémenter :</p>

      · Une libération de la mémoire à la fin de la compression, avec une
      fonction détruire_arbre par exemple
      · Le codage des caractères accentués. C’est tout un mystère mais les
      caractères accentués n’apparaissent pas dans mon dictionnaire, et
      je n’ai pas pu résoudre ce problème
      · Une décompression parfaitement fonctionnelle
      · Un code plus clair et des algorithmes mieux codés. Je suis conscient
      que certaines fonctions peuvent ne pas être très claires, cela est dû
      à plusieurs bricolages après certains bugs.
      · Une interface plus claire, avec la possibilité de nommer soit même
      son archive, etc. Cela est surtout dû à un manque de temps, j’ai
      préféré me consacrer à la décompression en priorité, en vain.
      
<h2>Mes difficultés :</h2>

<p>Durant ce DM, j’ai rencontré des difficultés à quasiment chaque étape des
codages, même si certaines ont été plus facilement surmontables que
d’autres. Néanmoins, ma principale difficulté a été de manipuler les
chaînes de caractères, et la navigation dans l’arbre de Huffman. Je n’ai pas
l’habitude de coder un programme aussi complexe, et j’ai souvent été
perdu dans la longueur de mon code.</p>
<p>Malgré ça, ce devoir restera une très bonne expérience. J’ai eu l’occasion
de manipuler quasiment tout ce que j’avais appris durant mes deux
années en CP2I, tout cela dans le but de créer un programme utile et dont
la méthode est très intéressante. Même si ce devoir est rendu, j’espère
pouvoir le terminer chez moi et le rendre fonctionnel, et pourquoi ne pas
lui rajouter quelques fonctionnalités.</p>

__________________________________________________________________________

