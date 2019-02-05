# ESTIAM-ElasticTP

Guillouzic Julien E4A

Merci de lire ce document "README" avant de lancer les requêtes des questions 1 à 9 !

Lors de mes requêtes sur les champs : nom, cuisine et borough, j'ai remarquer que les résultats n'étaient pas pertinents.
En effet, quand je requète sur une ville qui est d'un nom composé comme "New york" (qui est un exemple parfait),j'avais  2 résultat au lieu d'un seul sur cette ville : un pour "New" et un pour "York".
De plus, ce soucis était présent sur la cuisine (comme pour "japanese" qui retournait parmis les résultats, un résultat avec pour cuisine "japanese chinese") et de même pour le nom.

Afin de palier a ce soucis, j'ai changé le mapping de l'index afin d'ajouter un champ "raw" de type "keword" a ces 3 champs (cuisine, nom, borough).
	Quand on effectue une recherche de borough.raw j'ai bien en résultat "New york" et non deux résultat avec "New" et un autre avec "york"


De plus, afin que vous puissier lancer les requêtes, et que ces dernières soient fonctionnelles, je vous invite à re-créé l'index avec le mapping correspondant grâce à la commande suivante :
	curl -X PUT "localhost:9200/restaurants?pretty" -H 'Content-Type: application/json' --data-binary @CreationIndexMappingRestaurant.json
	

Enfin, j'ai ajouté à la fin de certaines requêtes un "size" afin d'optimisé le nombre de résultat voulus. Ce "size" est utilisé surtout dans les requêtes d'aggrégations afin
de rendre plus "visible" le résultats et l'affichage de ces dernières.


Fin du README
