Reference : https://book.hacktricks.xyz/pentesting-web/csrf-cross-site-request-forgery 
Regarder note lab portswigger . 




EXPLOITATION
- Sans defense : Tu peux l'exploiter sans prise de tete étant donné qu'il y a rien qui t'en en empêche 
- CSRF Token : 
	-  Enlever le parametre Token et regarder si l'application accepte la requete . 
	-  Changer la methode de la request et regarder si ca passe .  
	-  Verifier si le token est relié à la session , si non on peut utiliser celui géneré pour le compte de l'attaquant pour la victime . 



![[Pasted image 20230309200619.png]]        Balise pour request http forgée , souvent pour les formulaires GET ou pour file stocké sur server externe . C'est surtout pour un chaining avec une XSS . 