---
title: Configuration requise pour le proxy inverse dans Lync Server 2013
TOCTitle: Configuration requise pour le proxy inverse dans Lync Server 2013
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945651(v=OCS.15)
ms:contentKeyID: 53095521
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour le proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-05_

Lync Server 2013 impose quelques exigences quant aux communications en provenance du client externe qui sont ensuite passées aux services web externes hébergées sur le directeur, le pool de directeurs, le serveur frontal ou le pool de serveurs frontaux. Le proxy inverse est également responsable de la publication du Office Web Apps Server, si vous offrez des services de conférence à vos utilisateurs.

> [!NOTE]  
> Lync Server 2013 ne spécifie pas de proxy inverse spécifique à utiliser. Lync Server 2013 définit uniquement des exigences opérationnelles que le proxy inverse doit respecter. En général, le proxy inverse déjà déployé dans votre infrastructure peut être en mesure de répondre à ces exigences.

## Exigences relatives au proxy inverse

Les opérations fonctionnelles qu’un proxy inverse doit être capable d’effectuer selon Lync Server 2013 sont les suivantes :

  - Utiliser le protocole SSL (Secure Socket Layer) et la sécurité TLS (Transport Layer Security) mis en œuvre à l’aide de certificats acquis auprès d’une autorité de certification publique pour se connecter aux services web externes publiés du directeur, pool de directeurs, serveur frontal ou pool de serveurs frontaux. Le directeur et le serveur frontal peuvent se trouver dans un pool à équilibrage de la charge matérielle.

  - Publier des sites web internes à l’aide de certificats pour le chiffrement ou les publier de manière non chiffrée en cas de nécessité.

  - Publier un site web hébergé en interne à l’aide d’un nom de domaine complet.

  - Publier tout le contenu du site web hébergé. Par défaut, vous pouvez utiliser la directive **/\***, qui est reconnue par la plupart des serveurs web comme signifiant « Publier tout le contenu sur le serveur web ». Vous pouvez également modifier la directive, par exemple **/Uwca/\***, ce qui signifie « Publier tout le contenu sous le répertoire virtuel Ucwa ».

  - Capacité à être configuré de façon à exiger des connexions SSL et/ou TLS avec les clients qui demandent du contenu depuis un site web publié.

  - Accepter les certificats avec des entrées d’autres noms du sujet.

  - Autoriser la liaison d’un certificat à une interface ou un écouteur par le biais duquel le nom de domaine complet des services web externes sera résolu. Les configurations d’écouteurs sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une même interface.

  - Autoriser la configuration de la gestion des en-têtes d’hôtes. Souvent, l’en-tête d’hôte d’origine envoyé par le client demandeur doit être passé de manière transparente au lieu d’être modifié par le proxy inverse.

  - Pontage du trafic SSL et TLS depuis un port défini de manière externe (par exemple TCP 443) vers un autre port défini (par exemple TCP 4443). Le proxy inverse peut déchiffrer le paquet lors de sa réception, puis le rechiffrer lors de l’envoi.

  - Pontage du trafic TCP non chiffré depuis un port (par exemple TCP 80) vers un autre (par exemple TCP 8080).

  - Autoriser la configuration d’Authentification NTLM, Aucune authentification et Authentification directe ou accepter celles-ci.

