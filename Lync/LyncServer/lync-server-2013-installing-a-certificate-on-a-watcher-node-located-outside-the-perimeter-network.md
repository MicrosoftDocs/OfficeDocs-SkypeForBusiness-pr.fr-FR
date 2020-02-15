---
title: 'Lync Server 2013 : installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d89b14b783e2b78050b2db8e71a1009c974384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Les agents System Center Operations Manager exécutés dans un réseau de périmètre (tel qu’un serveur Edge Lync Server), en dehors de l’entreprise (comme un nœud observateur de transaction synthétique externe) ou dans une limite d’approbation des services de domaine Active Directory, peuvent Exigez la configuration d’un serveur de passerelle System Center Operations Manager. Ce rôle serveur permet à des agents qui n’ont pas de relation d’approbation avec le serveur d’administration racine de déclencher des alertes. Pour plus d’informations, consultez la rubrique relative à la gestion des serveurs de passerelle dans Operations Manager 2007 dans [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)la bibliothèque TechNet de System Center Operations Manager à l’adresse.

Si vous déployez un agent à l’un de ces emplacements, vous devrez également demander et configurer un certificat qui permet au nœud observateur d’envoyer des alertes à System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et d’installer le type correct de certificat sur l’ordinateur du nœud observateur. Pour plus d’informations et pour télécharger ces utilitaires, voir l’article sur le blog « obtention de certificats pour les agents non joints à un domaine en plus [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)de l’Assistant génération de certificat » à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

