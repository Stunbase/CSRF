DESCRIPTION
Cross Site Request Forgery est une vulnérabilité qui exploite la confiance que les sites web ont envers leurs users. L'attaque consiste à forcer un utilisateur à exécuter une action sur un site web à son insu .  Cette vuln exploite la confiance d'un site web des request venant d'un user authentifié. 


VERIFICATION 
La faille peut être vérifiée en forgeant une requéte HTTP valide et en verfiant si elle est acceptée par le serveur sans validation supplémentaire . Generalement on va utiliser des outils d'automatisation pour detecter que par exemple il n'y a pas de jeton token , ou meme pour detecter les requests HTTP forgées . 
Tools : nikto, burpsuite, outil de fuzzing

IMPACT
L'attaquant peut effectuer des actions malveillante comme changer le mdp , effectuer un achat, supprimer des datas , etc . 

EXPLOITATION METHODE
L'attaquant peut l'exploiter en incitant l'user à cliquer sur un lien ou à visiter une page Web contenant une requete forgée . Rq :  Interessant de faire un chaining de cette faille avec une HTMLi 
par exemple (xss , iframe injection, etc)

CORRECTION 
-Token anti CSRF , session valide et forte .   
-Dans le cas de modification de profile mettre en place verification des données precedentes . Exemple pour le password tu met oldpassword . 





























