---
title: 'Lync Server 2013 : configuration des interfaces réseau pour les serveurs Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e736a7782908479e670b7127c7518e044978ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configuration des interfaces réseau pour les serveurs Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Chaque serveur Edge est un ordinateur multirésident doté d’interfaces internes et externes. Les paramètres DNS (Domain Name System) de l’adaptateur varient selon qu’il y a des serveurs DNS dans le réseau de périmètre. Si les serveurs DNS existent dans le périmètre, ils doivent disposer d’une zone contenant un ou plusieurs enregistrements DNS A pour le serveur ou le pool du tronçon suivant (c’est-à-dire un directeur ou un pool frontal désigné), et pour les requêtes externes, ils reportent sur des recherches de noms à d’autres serveurs DNS publics. S’il n’existe aucun serveur DNS dans le périmètre, le ou les serveurs de périphérie utilisent des serveurs DNS externes pour résoudre les recherches de noms Internet et chaque serveur Edge utilise un hôte pour résoudre les noms de serveur du tronçon suivant en adresses IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" />Note de sécurité :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour des raisons de sécurité, nous vous recommandons de ne pas faire en sorte que vos serveurs Edge accèdent à un serveur DNS situé sur le réseau interne.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Pour configurer des interfaces avec des serveurs DNS dans le réseau de périmètre

1.  Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface côté interne et une pour l’interface côté externe.
    
    <div>
    

    > [!IMPORTANT]  
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux.

    
    </div>

2.  Sur l’interface externe, configurez trois adresses IP statiques sur le réseau de périmètre externe (également appelé DMZ, zone démilitarisée et sous-réseau filtré), puis pointez la passerelle par défaut vers l’interface interne du pare-feu externe. Configurez les paramètres DNS de la carte pour qu’ils pointent vers une paire de serveurs DNS de périmètre.
    
    <div>
    

    > [!NOTE]  
    > Il est possible d’utiliser une seule adresse IP pour cette interface, mais pour ce faire, vous devez modifier les affectations de Port aux valeurs non standard. Vous déterminez cela lorsque vous créez la topologie dans le générateur de topologie.

    
    </div>

3.  Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez pas de passerelle par défaut. Configurez les paramètres DNS de la carte pour qu’ils pointent vers au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.

4.  Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients, Lync Server 2013 et les serveurs de messagerie unifiée Exchange.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Pour configurer des interfaces sans serveurs DNS dans le réseau de périmètre

1.  Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface côté interne et une pour l’interface côté externe.
    
    <div>
    

    > [!IMPORTANT]  
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux.

    
    </div>

2.  Sur l’interface externe, configurez trois adresses IP statiques sur le sous-réseau du réseau de périmètre externe. Vous configurez également la passerelle par défaut sur l’interface externe. Par exemple, définissez le routeur accessible sur Internet ou le pare-feu externe comme passerelle par défaut. Configurez les paramètres DNS pour qu’ils pointent vers un serveur DNS, de préférence vers une paire de serveurs DNS externes.
    
    <div>
    

    > [!NOTE]  
    > Il est possible, mais pas recommandé, de n’utiliser qu’une seule adresse IP pour l’interface externe. Pour permettre cette opération, vous devez modifier les affectations de Port aux valeurs non standard, et loin du port 443 par défaut, généralement « pare-feu » pour la communication client. Vous déterminez le paramètre de l’adresse IP et les paramètres de port lors de la création de la topologie dans le générateur de topologie.

    
    </div>

3.  Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez pas de passerelle par défaut. Laissez les paramètres DNS de la carte vides.

4.  Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients ou serveurs Lync exécutant Lync Server 2013.

5.  Modifiez le fichier hôte sur chaque serveur Edge de sorte qu’il contienne un enregistrement pour le serveur du tronçon suivant ou l’adresse IP virtuelle (VIP) (l’enregistrement sera le directeur, le serveur Standard Edition ou un pool frontal configuré en tant qu’adresse du tronçon suivant du serveur Edge dans le générateur de topologie). Si vous utilisez l’équilibrage de la charge DNS, incluez une ligne pour chaque membre du pool du tronçon suivant.

</div>

</div>

<span> </span>

</div>

</div>

</div>

