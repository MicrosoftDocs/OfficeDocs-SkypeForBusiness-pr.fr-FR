---
title: 'Lync Server 2013 : configuration du routage géodépendant pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc901b9ef1b4b358771427f44d220631e4a40ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuration du routage géodépendant pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-11_

L’application de conférence de routage basée sur l’emplacement repose sur la configuration de l’acheminement géodépendant de Lync Server 2013. Les configurations principales sont les suivantes :

  - L’emplacement des participants qui rejoignent une réunion est déterminé en fonction de leur site réseau. Un site réseau et ses sous-réseaux associés doivent être définis dans Lync Server afin d’appliquer le routage géodépendant.

  - Pour appliquer le routage géodépendant des réunions, les participants Lync doivent être activés pour le routage géodépendant.

  - Pour appliquer le routage géodépendant des points de terminaison PSTN joignant des réunions, la jonction SIP utilisée pour connecter les points de terminaison PSTN doit être configurée pour le routage géodépendant.

Pour plus d’informations sur le déploiement et la configuration du routage géodépendant de Lync Server 2013, reportez-vous à la rubrique Configuring [location-based Routing](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Activation de l’application de conférence de routage basée sur l’emplacement

L’application de conférence de routage basée sur l’emplacement est désactivée par défaut. Avant d’activer cette application, vous devez déterminer la priorité appropriée à affecter à l’application. Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Lync Server Management Shell :

Get-CsServerApplication-Identity service : Registrar\<: nom de domaine complet du pool\>

Dans cette applet de \<commande,\> le nom de domaine complet du pool est le pool dans lequel l’application de conférence de routage basée sur l’emplacement doit être activée.

Cette applet de commande renvoie la liste des applications hébergées par Lync Server et la valeur de priorité pour chacune d’entre elles. L’application de conférence de routage basée sur l’emplacement doit disposer d’une valeur de priorité supérieure à celle de l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’affecter à l’application de conférence de routage basée sur l’emplacement une valeur de priorité supérieure d’un point à la valeur de priorité de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a une valeur de priorité « 2 », l’application « DefaultRouting » a une valeur de priorité « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité de « 10 », puis vous devez attribuer à l’application de conférence de routage basée sur l’emplacement une valeur de priorité de « 3 ». Cette opération placerait la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage basée sur l’emplacement (Priority : 3), autres applications (priorités : 4 à 8), " DefaultRouting "(Priority : 9)," ExumRouting "(Priority : 10) et" OutboundRouting "(Priority : 11).

Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de conférence de routage basée sur l’emplacement, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition dont les utilisateurs sont activés pour le routage géodépendant :

New-CsServerApplication-Identity service : Registrar\<: pool\>de nom de \<domaine complet\> /LBRouting-Priority Application Priority enabled $true-URI Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting

Par exemple :

New-CsServerApplication-Identity service :Registrar :LS2013CU2LBRPool. contoso. com/LBRouting-Optional 3-enabled $true-URI $true-URIhttps://www.microsoft.com/LCS/LBRouting

Après avoir utilisé cette applet de commande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition où l’application de conférence de routage basée sur l’emplacement a été activée.

<div>


> [!IMPORTANT]  
> Les conditions de routage géodépendant des conférences ou des transferts consultatifs ne sont pas appliquées tant que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition Server ne sont pas redémarrés.



</div>

Une fois que l’application de conférence de routage basée sur l’emplacement a été activée et que tous les serveurs Lync concernés ont été redémarrés, toutes les conférences organisées par des utilisateurs Lync activés pour le routage géodépendant sont surveillées pour empêcher le contournement de numéro de téléphone PSTN.

</div>

</div>

<span> </span>

</div>

</div>

</div>

