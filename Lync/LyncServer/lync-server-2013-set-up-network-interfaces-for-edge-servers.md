---
title: 'Lync Server 2013 : Configuration des interfaces réseau pour les serveurs Edge'
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
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configuration des interfaces réseau pour les serveurs Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Chaque serveur Edge est un ordinateur multirésident doté d’interfaces externes et internes. Les paramètres de système de noms de domaine (DNS) d’adaptateur dépendent de la présence de serveurs DNS dans le réseau de périmètre. Si les serveurs DNS existent dans le périmètre, ils doivent disposer d’une zone contenant un ou plusieurs enregistrements DNS A pour le serveur de tronçon suivant ou le pool (c’est-à-dire, un directeur ou un pool frontal désigné) et pour les requêtes externes, elles font référence à des recherches de nom à d’autres serveurs DNS publics. S’il n’existe aucun serveur DNS sur le périmètre, le ou les serveurs de périphérie utilisent des serveurs DNS externes pour résoudre les recherches de noms Internet et chaque serveur Edge utilise un hôte pour résoudre les noms de serveurs de sauts suivants en adresses IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" />Note de sécurité :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour des raisons de sécurité, nous vous recommandons de ne pas que vos serveurs Edge accèdent à un serveur DNS situé dans le réseau interne.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Pour configurer des interfaces avec des serveurs DNS dans le réseau de périmètre

1.  Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface interne et une pour l’interface externe.
    
    <div>
    

    > [!IMPORTANT]  
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux.

    
    </div>

2.  Sur l’interface externe, configurez trois adresses IP statiques sur le réseau de périmètre externe (également connu sous le nom de DMZ, zone démilitarisée et sous-réseau à écran), puis pointez la passerelle par défaut vers l’interface interne du pare-feu externe. Configurez les paramètres DNS de l’adaptateur de façon à ce qu’ils pointent vers une paire de serveurs DNS de périmètre.
    
    <div>
    

    > [!NOTE]  
    > Il est possible d’utiliser une seule adresse IP pour cette interface, mais pour cela, vous devez remplacer les affectations de port par des valeurs non standard. Vous déterminez cela lorsque vous créez la topologie dans le générateur de topologie.

    
    </div>

3.  Dans l’interface interne, configurez une adresse IP statique sur le sous-réseau de périmètre interne et ne définissez aucune passerelle par défaut. Configurez les paramètres DNS de l’adaptateur de façon à ce qu’ils pointent vers au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.

4.  Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes dans lesquels résident les clients, Lync Server 2013 et les serveurs Exchange Unified Messaging (UM).

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Pour configurer des interfaces sans serveurs DNS dans le réseau de périmètre

1.  Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface interne et une pour l’interface externe.
    
    <div>
    

    > [!IMPORTANT]  
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux.

    
    </div>

2.  Sur l’interface externe, configurez trois adresses IP statiques sur le sous-réseau de périmètre externe. Vous configurez également la passerelle par défaut sur l’interface externe. Par exemple, définissez le routeur Internet ou le pare-feu externe comme passerelle par défaut. Configurez les paramètres DNS pour qu’ils pointent vers un serveur DNS, de préférence vers une paire de serveurs DNS externes.
    
    <div>
    

    > [!NOTE]  
    > Il est possible, mais déconseillé, d’utiliser autant qu’une seule adresse IP pour l’interface externe. Pour cela, vous devez remplacer les affectations de port par des valeurs non standard et quitter le port 443 par défaut, qui est généralement « compatible avec le pare-feu » pour la communication client. Vous déterminez le paramètre d’adresse IP et les paramètres de port lorsque vous créez la topologie dans le générateur de topologie.

    
    </div>

3.  Dans l’interface interne, configurez une adresse IP statique sur le sous-réseau de périmètre interne et ne définissez aucune passerelle par défaut. Laissez les paramètres DNS de l’adaptateur vides.

4.  Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes pour lesquels résident les clients ou serveurs Lync exécutant Lync Server 2013.

5.  Modifiez le fichier hôte sur chaque serveur Edge pour qu’il contienne un enregistrement pour le serveur du tronçon suivant ou l’adresse IP virtuelle (VIP) (l’enregistrement sera le directeur, Standard Edition Server, ou un pool frontal configuré en tant que serveur de périphérie du tronçon suivant dans le générateur de topologie). Si vous utilisez l’équilibrage de charge DNS, incluez une ligne pour chaque membre du pool de prochains tronçons.

</div>

</div>

<span> </span>

</div>

</div>

</div>

