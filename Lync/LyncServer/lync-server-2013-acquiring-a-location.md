---
title: 'Lync Server 2013 : acquisition d’un emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e726424e9e24c223bc7e75346bd0c2188f29ee7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Acquisition d’un emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Dans un déploiement Lync Server 2013 E9-1-1, chaque client Lync ou Lync Phone Edition connecté en interne acquiert activement son propre emplacement. Une fois l’enregistrement SIP effectué, le client fournit toutes les informations de connectivité réseau qu’il connaît lui-même dans une demande d’emplacement auprès du service d’informations d’emplacement, qui est un service Web sauvegardé par une base de données SQL Server répliquée. Chaque pool de sites central dispose d’un service d’informations d’emplacement, qui utilise les informations réseau pour interroger ses enregistrements pour un emplacement correspondant. S’il existe une correspondance, le service d’informations d’emplacement renvoie un emplacement au client. Dans le cas inverse, le système peut demander à l’utilisateur d’entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement). Les données d’emplacement sont retransmises au client dans un format XML au standard IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).

Le client Lync Server inclut les données PIDF-LO dans le cadre d’un appel d’urgence, et ces données sont utilisées par le fournisseur de services E9-1-1 pour déterminer le PSAPI approprié et acheminer l’appel vers ce PSAPI avec le bon ESQK, ce qui permet au serveur de distribution PSAPI d’obtenir le emplacement de l’appelant.

Le diagramme suivant montre comment un client Lync Server acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC cliente tierce) :

![Comment le client acquiert un diagramme d’emplacement](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Comment le client acquiert un diagramme d’emplacement")

Pour qu’un client acquière un emplacement, les étapes suivantes doivent être effectuées :

1.  L’administrateur remplit la base de données du service informations d’emplacement avec le réseau câblage (tables qui mappent différents types d’adresses réseau aux emplacements de réponse d’urgence correspondants (Erl)).

2.  Si vous utilisez un fournisseur de services E9-1-1 de jonction SIP, l’administrateur valide les portions d’adresses géographiques des emplacements d’intervention d’urgence à partir d’une base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de services E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les numéros d’identification d’emplacement d’urgence vers la base de données ALI (Automatic Location Identification).

3.  Lors de l’inscription ou chaque fois qu’une modification réseau a lieu, un client connecté en interne envoie une demande d’emplacement qui contient les adresses réseau découvertes du client au service d’informations d’emplacement.

4.  Le service informations d’emplacement interroge ses enregistrements publiés à la recherche d’un emplacement et, si une correspondance est trouvée, renvoie l’ERL au client au format PIDF-LO.

</div>

<span> </span>

</div>

</div>

</div>

