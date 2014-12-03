
Les fonctions disponibles pour obtenir/transmettre de l'information du/au serveur
sont exposées par le module poooc. 

Ces fonctions sont au nombre de 4 :

### order(msg)

##### Ordonne un mouvement

:param move: ordre conforme à [<userid>]MOV<%offunits>FROM<cellid>TO<cellid>
:type move: chaîne de caractères (utf-8 string)

:Example:

"[0947e717-02a1-4d83-9470-a941b6e8ed07]MOV33FROM1TO4"

Le pourcentage des unités offensives utilise la divion entière. Par exemple : 25% de 50 égal à 50*25/100=12. Un ordre dont l'effectif d'unités off est nul (par ex., 33% de 2 unités) est ignoré, tout comme des ordres incorrects (cellule non occupée, cellules non adjacentes, etc.)

### state() 

##### Demande l'état courant du jeu

:return: état conforme à
STATE<matchid>IS<#players>;<#cells>CELLS:<cellid>[<owner>]<offunits>'<defunits>,...;\
<#moves>MOVES:<cellid><direction><#units>[<owner>]@<timestamp>'...<cellid>,...
:rtype: chaîne de caractères (utf-8 string)

:Example:

"STATE20ac18ab-6d18-450e-94af-bee53fdc8fcaIS2;3CELLS:1[2]12'4,2[2]15'2,3[1]33'6;4MOVES:1<5[2]@232'>6[2]@488'>3[1]@4330'2,1<10[1]@2241'3"

<timestamp> en millisecondes, donnée à vitesse x1 : top départ des unités de la cellule source. 
<direction> désigne le caractère '>' ou '<' et indique le sens des unités en mouvement en suivant la pointe de flèche.

### state_on_update()

##### Demande l'état du jeu modifié

La valeur de retour est identique à celle de la fonction state()
La principale différence provient du fait que le processus est mis en attente d'une mise à jour de l'état du jeu

L'appel de state_on_update() est bloquant

### etime()

##### Retourne le temps écoulé (elapsed time) depuis le début du match

:return: temps écoulé (elapsed time) en millisecondes
:rtype: entier

/!\ le temps indiqué n'est qu'une approximation (la plus précise possible)
