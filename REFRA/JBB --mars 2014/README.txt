Les samples ainsi que les orgues, ont �t� con�us avec le plugin VST SQ8L.

Le fichier "8bitSigned" doit �tre charg� avec l'option accessible au clic droit "Load with options" (pensez � cliquer sur le bouton *.*) avec les options suivantes :

Bits                 : 8BitSigned
Sample rate          : 44100
Skip header bytes    : 0
Big endian           : d�coch�

Mais qu'est-ce que ce fichier ?

En apprenant que Renoise pouvait tirer un sample de n'importe quel fichier (photo, texte, vid�o), je me suis dit : il doit y avoir � chaque valeur binaire une hauteur de son associ�e.

J'ai donc ouvert un �diteur hexad�cimal, et j'ai bidouill�.

J'ai d�couvert ceci :

FF : 0

de 01 � 7F : du plus bas au plus haut dans les valeur positive.

de 80 � FE : du plus haut au plus bas dans les valeurs n�gatives.

Ainsi le fichier "8bitSigned" a-t-il les valeurs binaires suivantes (commentaire entre crochets):

FF [valeur nulle] 0F [positif] F0 [n�gatif] 1F [positif] E0 [n�gatif] 2F [positif] D0 [n�gatif] 01 [d�but "courbe" positive] 51 61 71 72 73 74 75 76 78 79 [fin "courbe" positive] 80 [d�but "courbe" n�gative] D1 E1 F1 F2 F3 F4 F5 F6 F8 FE FF [fin "courbe" n�gative]

D�sormais vous savez comment �crire vos samples en hexad�cimal !