---
title: 'Lync Server 2013 : Configuration requise pour l’infrastructure Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c583fd751bf70814f9aa2fae5f6cfe08bec0202
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Avant de commencer le processus de préparation des services de domaine Active Directory pour Lync Server 2013, assurez-vous que votre infrastructure Active Directory répond aux conditions préalables suivantes:

  - Tous les contrôleurs de domaine (qui incluent tous les serveurs de catalogue global) dans la forêt où vous déployez Lync Server exécutent l’un des systèmes d’exploitation suivants:
    
      - Système d’exploitation Windows Server 2012 R2
    
      - Système d’exploitation Windows Server 2012
    
      - Système d’exploitation Windows Server 2008 R2
    
      - Système d’exploitation Windows Server 2008
    
      - Windows Server 2008 entreprise 32 bits
    
      - versions 32 ou 64 bits du système d’exploitation Windows Server 2003 R2
    
      - versions 32 ou 64 bits du système d’exploitation Windows Server 2003

  - Tous les domaines dans lesquels vous déployez Lync Server sont déclenchés à un niveau de fonctionnalité de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

  - La forêt dans laquelle vous déployez Lync Server est déclenchée à un niveau de fonctionnalité de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.
    
    <div>
    

    > [!NOTE]  
    > Pour modifier le niveau de fonctionnement de votre domaine ou forêt, voir «augmentation des niveaux fonctionnels de domaine et de <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>forêt» dans la bibliothèque TechNet à l’adresse.

    
    </div>

  - Un catalogue global est déployé dans chaque domaine sur lequel vous déployez des ordinateurs ou des utilisateurs Lync Server.

Lync Server 2013 prend en charge les groupes universels dans les systèmes d’exploitation Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003. Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également. La prise en charge des groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement de Lync Server. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux.

</div>

<span> </span>

</div>

</div>

</div>

