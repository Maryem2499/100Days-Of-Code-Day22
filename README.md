# Building Pong : The famous arcade game 
## Principe 
c'est trés simple, en gros c'est juste un ballon qui traverse une table et 2 joueurs controlant chacun une pagaie faire rebondir le ballon d'avant en arriére ==> si vous manquez le ballon, l'autre joueurs marque un point.
dont j'ai divisée le probléme en 8 morceaux : 
## Créer l'écran 800px by 600px
Nous allons juste écrire l'écran de départ qui sera d'un H=600px et L=800px, couleur du fond noir.
## Créer et déplacer une pagaie 
la pagaie que nous allons créer va etre du bon coté avec : Width=20, Height=100, x_pos=350 et y_pos=0
Puis on va cliquer sur les touches haut et bas du clavier pour déplacer la pagaie, et pour chaque pression il doit etre deplacé 20px
## Créer un autre pagaie 
Pour que nous puissons avoir un jeu à deux personnes.
Nous allons avoir besoin de l'aide d'une classe de pagayage séparé 
Créer un pagaie droit et un pagaie gauche à partir de la classe paddle  : r_paddle =  Paddle() et l_paddle = Paddle() dans le main.py parce que les coordonnées du pagaie droit est différentes du pagaie gauche.
## Créer le ballon et le faire bouger 
ce ballon doit etre créer comme une classe de balle distincte et l'objet de la ballon que nous allons créer à partir d'elle aura une largeur de 20px, hauteur de 20px et c'est les positions x et y egaux à 0 ( commençeront au centre de l'écran), quand l'écranc se refraichit, le ballon va automatiquement se déplacer sur l'écran et il va monter à gauche et aussi à droite.
Ainsi les positions x et y changent à chaque refraichissement de l'écran.
## Comprendre quand le entre entre en collision avec un mur et le faire rebondir
Il suffit de détecter la collision sur les parois supérieurs et inférieurs parce que lorsque le ballon frappe les bords droit ou gauche du pon, il devrait en fait etre attrapé par une des pagaies. Et si ce n'est pas le cas, alors le joueur à manquécle ballon et c'est un point vers l'autre coté.
## Comment détecter une collision avec le pagaie pour savoir quand le faire rebondir 
Utiliser la méthode de distance pour vérifier qu'elle est la distance entre le ballon et le pagaie : ball.distance(paddle), en ajoutant une condition supplémentaire.
Nous pourrions bien vérifier si le ballon à dépassé certain point sur l'axe x, si il est allé assez loin vers la droite, et si elle se trouve à moins du 50px du pagaie, cela siqnifie qu'elle est entrée en contact avec la pagaie.
## Déterminer quand un utilisateur marque un point quand la pagaie manque le ballon 
Ce que nous vérifions, c'est que le ballon à depassé un certain point sur l'écran. Si oui, le ballon doit se positionner de nouveau au centre de l'écran. Puis réssayer le jeu du nouveau.
## Compter le score à l'aide d'un tableaud'affichage  "Keep Score"
