---
title: 'Lync Server 2013 : Composants et topologies utilisés pour une jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c589ff02717ad49ce89d0d4e3324f6fe993e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Composants et topologies utilisés pour une jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

La figure suivante illustre la topologie de trunking SIP dans Lync Server.

**Topologie de trunking SIP**

![Topologie de jonction SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologie de jonction SIP")

Comme le montre le diagramme, un réseau privé virtuel (VPN) IP est utilisé pour la connectivité entre le réseau d’entreprise et le fournisseur de services de réseau téléphonique commuté. L’objectif de ce réseau privé est de fournir la connectivité IP, d’améliorer la sécurité et (éventuellement) d’obtenir des garanties de qualité de service. En raison de la nature d’un VPN, vous n’avez pas besoin d’utiliser TLS pour le trafic de signalisation SIP, ni SRTP pour le trafic multimédia. De ce fait, les connexions entre l’entreprise et le fournisseur de services consistent en des connexions TCP ordinaires pour SIP et des connexions RTP ordinaires (avec le protocole UDP) pour les médias traités par tunnel via un réseau VPN IP. Veillez à ce que tous les pare-feu situés entre les routeurs VPN disposent de ports ouverts pour permettre aux routeurs VPN de communiquer. Par ailleurs, les adresses IP des périmètres externes des routeurs VPN doivent être publiquement routables.

<div>


> [!IMPORTANT]  
> Contactez votre fournisseur de services pour déterminer s’il fournit la prise en charge pour la disponibilité élevée, notamment le basculement. Si c’est le cas, vous devrez déterminer les procédures pour la configurer. Par exemple, avez-vous besoin de configurer une seule adresse IP et une ligne SIP Trunk sur chaque serveur de médiation, ou devez-vous configurer plusieurs ISL SIP sur chaque serveur de médiation ?<BR>Si vous disposez de plusieurs sites centraux, demandez-vous également si le prestataire de services peut activer les connexions vers et à partir d’un autre site central.



</div>

<div>


> [!NOTE]  
> Pour le trunking SIP, nous vous conseillons vivement de déployer des serveurs de médiation autonomes. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">déploiement de serveurs de médiation et définition d’homologues dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Sécurisation du serveur de médiation pour la jonction SIP

Pour des raisons de sécurité, vous devriez configurer un réseau local virtuel (VLAN) pour chaque connexion entre deux routeurs VPN. Le processus courant de configuration d’un VLAN varie d’un fabricant de routeur à l’autre. Pour plus d’informations, contactez le fournisseur de votre routeur.

Nous vous conseillons de suivre les directives suivantes :

  - Configurez un réseau local virtuel (VLAN) entre le serveur de médiation et le routeur VPN dans le réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré).

  - N’autorisez pas le transfert des paquets de diffusions ou de multidiffusions entre le routeur et le réseau local virtuel.

  - Bloquez les règles de routage qui acheminent le trafic du routeur vers n’importe où, mais le serveur de médiation.

Si vous utilisez un serveur VPN, bous vous conseillons de suivre les directives suivantes :

  - Configurez un VLAN entre le serveur VPN et le serveur de médiation.

  - N’autorisez pas la transmission des paquets de diffusions ou de multidiffusions du serveur VPN vers le réseau local virtuel.

  - Bloquer toutes les règles de routage qui routent le trafic du serveur VPN vers n’importe quel endroit, mais le serveur de médiation.

  - Chiffrez les données sur le réseau privé virtuel (VPN) à l’aide de l’encapsulation générique de routage (GRE).

</div>

</div>

<span> </span>

</div>

</div>

</div>

