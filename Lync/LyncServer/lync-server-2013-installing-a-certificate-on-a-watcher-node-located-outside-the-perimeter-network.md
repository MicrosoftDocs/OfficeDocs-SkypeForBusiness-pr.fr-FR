---
title: 'Lync Server 2013: installation d’un certificat sur un nœud FileSystemWatcher situé en dehors du réseau de périmètre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1479ffdd7f6652b96f3015e047194d76bf1e8978
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Installation d’un certificat sur un nœud d’observation situé hors du réseau de périmètre de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Les agents du gestionnaire d’opérations de System Center qui s’exécutent dans un réseau de périmètre (par exemple, un serveur Edge de Lync Server), en dehors de l’entreprise (par exemple, un nœud d’observateur de transactions synthétiques externes) ou sur une limite d’approbation des services de domaine Active Directory (AD DS), peuvent nécessitent la configuration d’un serveur de passerelle System Center Operations Manager. Ce rôle de serveur permet aux agents qui n’ont pas de relation d’approbation avec le serveur de gestion racine de déclencher des alertes. Pour plus d’informations, voir la section «gestion des serveurs de passerelles dans Operations Manager 2007» dans [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)la bibliothèque TechNet de System Center Operations Manager à l’adresse.

Si vous déployez un agent à l’un de ces emplacements, vous devrez également demander et configurer un certificat qui permet au nœud d’observation d’envoyer des alertes à System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et d’installer le type correct de certificat sur l’ordinateur de nœud d’observation. Pour plus d’informations, reportez-vous à l’article «obtention de certificats pour les agents non-domaines» en plus facilement avec l’Assistant [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)création de certificats.

</div>

<span> </span>

</div>

</div>

</div>

