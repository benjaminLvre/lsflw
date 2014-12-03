#lsflw
=====

Depôt du groupe STFU pour le jeu Little Stars For Little War


http://madoc.univ-nantes.fr/course/view.php?id=29903

### Les règles du jeu

jeu de stratégie temps réel multi-joueurs

        Le terrain est généré par le système, avec une position de départ (une cellule unique) attribuée à chaque joueur/robot engagé ; 

        Chaque cellule occupée produit des unités offensives et défensives à concurrence de sa capacité et à une cadence définie par le système ;

        Chaque cellule neutre possède au départ un nombre d’unités défini par le système et ne produit aucune nouvelle unité ; 

        Une proportion quelconque de l’effectif offensif d’une cellule peut se déplacer vers une cellule adjacente, à une vitesse définie par le système ; 

        Si l’effectif d’une cellule (off+def) est inférieur strictement à l’effectif entrant, la cellule est conquise ; 

        Dans tous les cas, l’effectif de la cellule diminue de l’effectif courant (off+def) moins l’effectif arrivant (min=0); 

        Les unités consommées en priorité sont les unités offensives ; 

        Lorsqu'une cellule n'a plus aucune unité, elle redevient neutre.

        En transfert, les conflits entre unités ennemies qui se croisent sont résolus immédiatement;

#### Petit lexique

    ** Terrain ** : graphe géométrique planaire dont les n\oe uds sont les cellules du jeu
    ** Cellule ** : noeud du graphe, avec ses propriétés
        capacités offensive et défensive
        effectifs offensif et défensif
        cadences de production offensive et défensive

    ** Cellule occupée ** : cellule appartenant à un joueur
    ** Cellule neutre ** : cellule libre de toute occupation
    ** Conquête ** : prise d'une cellule par un joueur
    ** Unité offensive ** : unité mobile, pour la conquête
    ** Unité défensive ** : unité fixe, propre à une cellule et utilisée en cas de prise
    ** Capacité ** : nombre max. d'unités que peut accueillir une cellule
    ** Cadence de production ** : vitesse à laquelle sont créées les unités dans une cellule
