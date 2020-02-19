---
title: Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server-tâches de site central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39b0d9e4d10f4e28afa2a01e02dc2fab4c842bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâches de site central

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Effectuez les tâches de cette section sur le site central. Si vous déployez un serveur Survivable Branch Server, ignorez la première tâche.

<div>


> [!IMPORTANT]
> Avant d’effectuer les tâches dans cette section, les conditions suivantes doivent être remplies : 
> <UL>
> <LI>
> <P>Lync Server doit être configuré sur le site central.</P>
> <LI>
> <P>Un technicien d’installation du site de succursale doit être ajouté au groupe RTCUniversalSBATechnicians.</P></LI></UL>En outre, nous vous recommandons d’effectuer ce qui suit :
> <UL>
> <LI>
> <P>Déployez un serveur DHCP sur chaque site de succursale pour permettre aux clients d’obtenir les adresses IP.</P>
> <LI>
> <P>En guise d’alternative au déploiement d’un serveur DHCP sur chaque site de succursale, vous pouvez activer le protocole DHCP Lync Server sur le Survivable Branch Appliance ou le serveur Survivable Branch Server à l’aide de la cmdlet Lync Server Management Shell <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>. Pour plus d’informations, reportez-vous à la section Configuration matérielle et logicielle requise <A href="lync-server-2013-branch-site-resiliency-requirements.md">pour la résistance des sites de succursale pour Lync Server 2013</A> dans la documentation de planification.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Ajouter des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

