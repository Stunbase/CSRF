Commencer par un nitko ou autre outil d'automatisation . 

PARAMETRE VULNERABLE  
Le but : (exemple: exploit CSRF pour change l'email )
Les credentials : .....

ANALYSE 
Pour une requete CSRF soit possible : 
- Action pertinente : (ex: changer mdp d'un user )
- Gestion basée sur un cookie : basée sur authentification (plupart du temps cookie de session)
- Pas de paramétres de request imprevisible : (du moins essayer de bypass)

Test des CSRF Tokens : 
1. Supprimer le token CSRF et regarder si l'application accepte la request
2. Changer la methode de la requete 
3. Regarder si la CSRF est lié à la session de l'user si non utiliser le token du compte attaquant

Test CSRF Tokens et CSRF cookies : 
1.  Verifier si le token CSRF est lié au cookie CSRF .
	- Submit un token CSRF invalide
	- Submit un token CSRF valide d'au autre user . 
 2. Submit un token CSRF valide et le cookie d'un autre user (evil account)

Afin d'exploiter cette vuln , nous devons effectuer ces 2 choses : 
1. Injecter un cookie CSRF dans la session de l'user (HTTP Header injection )
2. Envoyer une attaque CSRF à la victime avec le jeton CSRF connu .

Parenthese : Regarder si la verification se base à ce que le cookie de csrf doit être  egale au csrf token . Si oui , generer un csrf random et mettre le meme aux deux (CSRF token et CSRF cookie)


Test CSRF basé sur le header referrer : 
1. Supprimer le header refferer et regarder si la requete passe 
2. Tester quelle partie du header refferer est celui qui valide , et donc essayer de faire une redirection de notre serveur attaquant vers le refferer validant . 
<head>
<meta name="referrer" content="never">
</head>
