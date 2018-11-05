---
title: 'Lync Server 2013 : Acquisition d’un emplacement'
TOCTitle: Acquisition d’un emplacement
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205110(v=OCS.15)
ms:contentKeyID: 49298308
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Acquisition d’un emplacement dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-06_

Dans un déploiement Lync Server 2013 E9-1-1, chaque client Lync ou Lync Phone Edition connecté en interne acquiert de manière active son propre emplacement. Après l’inscription SIP, le client fournit toutes les informations de connectivité réseau le concernant et dont il a connaissance dans une demande d’emplacement envoyée au service d’informations sur l’emplacement, qui est un service web secondé par une base de données SQL Server répliquée. Chaque pool de site central a un service d’informations sur l’emplacement, qui utilise les informations réseau pour interroger ses enregistrements afin de trouver un emplacement correspondant. S’il trouve une correspondance, le service d’informations sur l’emplacement renvoie un emplacement au client. Dans le cas inverse, l’utilisateur peut être invité à entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement). Les données d’emplacement sont retransmises au client dans un format XML normalisé IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).

Le client Lync Server inclut les données PIDF-LO dans le cadre d’un appel d’urgence et ces données sont utilisées par le fournisseur de service E9-1-1 pour déterminer le centre téléphonique de sécurité publique (PSAP, Public Safety Answering Point) approprié et acheminer l’appel vers ce centre PSAP avec l’ESQK correct, ce qui permet au répartiteur PSAP d’obtenir l’emplacement de l’appelant.

Le schéma suivant montre comment un client Lync Server acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC de client tiers) :

![Diagramme : comment le client acquiert un emplacement](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Diagramme : comment le client acquiert un emplacement")

Pour qu’un client acquiert un emplacement, les étapes suivantes doivent se produire :

1.  L’administrateur remplit la base de données du service d’informations sur l’emplacement avec le schéma de câblage réseau (tables qui mappent différents types d’adresses réseau à des emplacements ERL (Emergency Response Locations) correspondants.

2.  Si vous utilisez un fournisseur de service E9-1-1 de jonction SIP, l’administrateur valide les parties d’adresse civile des ERL par rapport à la base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de service E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les ELIN dans la base de données ALI (Automatic Location Identification).

3.  Durant l’inscription ou chaque fois qu’une modification réseau a lieu, un client connecté en interne envoie au service d’informations sur l’emplacement une demande d’emplacement qui contient les adresses réseau découvertes du client.

4.  Le service d’informations sur l’emplacement recherche un emplacement dans ses enregistrements publiés et, s’il en trouve un, renvoie l’ERL au client au format PIDF-LO.

