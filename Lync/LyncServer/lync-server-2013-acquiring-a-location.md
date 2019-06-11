---
title: 'Lync Server 2013 : Acquisition d’un emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Acquisition d’un emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-06_

Dans un déploiement Lync Server 2013 E9-1-1, chaque client Lync connecté en interne ou Lync Phone Edition acquiert activement son emplacement. Après l’inscription SIP, le client fournit toutes les informations de connectivité réseau qu’il connaît lui-même dans une demande d’emplacement du service d’information d’emplacement, qui est un service Web stocké par une base de données SQL Server répliquée. Chacun d’eux dispose d’un service d’information d’emplacement qui utilise les informations réseau pour rechercher un emplacement correspondant dans ses enregistrements. S’il existe une correspondance, le service d’informations d’emplacement renvoie un emplacement au client. Dans le cas inverse, l’utilisateur peut être invité à entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement). Les données d’emplacement sont retransmises au client dans un format XML normalisé IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).

Le client Lync Server inclut les données PIDF-LO dans le cadre d’un appel d’urgence, et ces données sont utilisées par le prestataire de services E9-1-1 pour déterminer le PSAPI approprié et acheminer l’appel vers ce PSAPI avec le bon ESQK, ce qui permet au répartiteur PSAPI d’obtenir le emplacement de l’appelant.

Le diagramme suivant montre comment un client Lync Server acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC du client tiers):

![Acquisition d’un diagramme d’emplacement par le client] (images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Acquisition d’un diagramme d’emplacement par le client")

Pour qu’un client acquière un emplacement, les étapes suivantes doivent se produire :

1.  L’administrateur remplit la base de données de service informations d’emplacement avec le Network Wiremap (tables qui mappent différents types d’adresses réseau aux emplacements de réponse d’urgence correspondants (ERLs)).

2.  Si vous utilisez un fournisseur de service E9-1-1 de jonction SIP, l’administrateur valide les parties d’adresse civile des ERL par rapport à la base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de service E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les ELIN dans la base de données ALI (Automatic Location Identification).

3.  Lors de l’inscription ou en cas de modification d’un réseau, un client connecté en interne envoie une demande d’emplacement contenant les adresses réseau découvertes du client au service d’informations d’emplacement.

4.  Le service d’informations d’emplacement interroge ses enregistrements publiés pour un emplacement et, si une correspondance est trouvée, renvoie la propriété ERL au client en format PIDF-Low.

</div>

<span> </span>

</div>

</div>

</div>

