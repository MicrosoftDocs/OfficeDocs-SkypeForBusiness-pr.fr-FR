---
title: 'Lync Server 2013 : configuration du routage des Location-Based pour les conférences'
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
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507801"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuration du routage des Location-Based pour les conférences dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-11_

L’application de conférence de routage de Location-Based s’appuie sur la configuration de Lync Server 2013 Location-Based le routage. Les configurations principales sont les suivantes :

  - L’emplacement des participants qui rejoignent une réunion est déterminé en fonction de leur site réseau. Un site réseau et ses sous-réseaux associés doivent être définis dans Lync Server afin de mettre en œuvre le routage des Location-Based.

  - Pour appliquer Location-Based routage des réunions, les participants Lync doivent être activés pour le routage des Location-Based.

  - Pour mettre en œuvre Location-Based routage des points de terminaison PSTN qui rejoignent des réunions, la jonction SIP utilisée pour connecter les points de terminaison PSTN doit être configurée pour le routage de Location-Based.

Pour plus d’informations sur le déploiement et la configuration de Lync Server 2013 Location-Based routage, veuillez vous reporter à la rubrique Configuring [location-based Routing](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Activation de l’application de conférence de routage de Location-Based

L’application de conférence de routage de Location-Based est désactivée par défaut. Avant d’activer cette application, vous devez déterminer la priorité appropriée à affecter à l’application. Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Lync Server Management Shell :

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

Dans cette applet de commande, \<Pool FQDN\> est le pool dans lequel l’application de conférence de routage de Location-Based doit être activée.

Cette applet de commande renvoie la liste des applications hébergées par Lync Server et la valeur de priorité pour chacune d’entre elles. L’application de conférence de routage Location-Based doit disposer d’une valeur de priorité supérieure à celle de l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’affecter au Location-Based application de conférence de routage une valeur de priorité d’un point supérieure à la valeur de priorité de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a une valeur de priorité « 2 », l’application « DefaultRouting » a une valeur de priorité « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité « 10 », vous devez alors affecter la valeur « 3 » à Location-Based la priorité. Cela placerait la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage (Priority : 3) Location-Based, autres applications (priorités : 4 à 8), « DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).

Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de conférence de routage de Location-Based, tapez l’applet de commande suivante pour chaque pool de Front-End ou serveur Standard Edition dont les utilisateurs sont activés pour le routage de Location-Based :

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Par exemple :

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Après avoir utilisé cette applet de commande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition où l’application de conférence de routage de Location-Based a été activée.

<div>


> [!IMPORTANT]  
> Location-Based l’application du routage aux conférences ou aux transferts consultatifs ne seront pas appliquées tant que tous les serveurs frontaux des pools applicables ou les serveurs Standard Edition Server ne sont pas redémarrés.



</div>

Une fois que l’application de conférence de routage Location-Based a été activée et que tous les serveurs Lync applicables ont été redémarrés, toutes les conférences organisées par des utilisateurs Lync activés pour le routage Location-Based seront surveillées pour empêcher le contournement de numéro de téléphone PSTN.

</div>

</div>

<span> </span>

</div>

</div>

</div>

