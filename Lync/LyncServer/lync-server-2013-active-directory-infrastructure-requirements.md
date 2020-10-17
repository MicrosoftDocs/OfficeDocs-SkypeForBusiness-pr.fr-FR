---
title: 'Lync Server 2013 : configuration requise pour l’infrastructure Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46435a3683465c1e31406e46181df8ffa069615e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529611"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Avant de commencer le processus de préparation des services de domaine Active Directory pour Lync Server 2013, assurez-vous que votre infrastructure Active Directory répond aux conditions préalables suivantes :

  - Tous les contrôleurs de domaine (qui incluent tous les serveurs de catalogue global) dans la forêt où vous déployez Lync Server exécutent l’un des systèmes d’exploitation suivants :
    
      - Système d’exploitation Windows Server 2012 R2
    
      - Système d’exploitation Windows Server 2012
    
      - système d’exploitation Windows Server 2008 R2
    
      - système d’exploitation Windows Server 2008
    
      - Windows Server 2008 Enterprise 32 bits
    
      - versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003 R2
    
      - versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003

  - Tous les domaines dans lesquels vous déployez Lync Server sont élevés à un niveau fonctionnel de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

  - La forêt dans laquelle vous déployez Lync Server est élevée à un niveau fonctionnel de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.
    
    <div>
    

    > [!NOTE]  
    > Pour modifier le niveau fonctionnel de votre domaine ou de votre forêt, voir « augmentation des niveaux fonctionnels des domaines et des forêts » dans la bibliothèque TechNet à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> .

    
    </div>

  - Un catalogue global est déployé dans chaque domaine où vous déployez des ordinateurs ou des utilisateurs Lync Server.

Lync Server 2013 prend en charge les groupes universels dans les systèmes d’exploitation Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003. Les membres des groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arborescence de domaine ou de la forêt et peuvent se voir attribuer des autorisations dans n’importe quel domaine de l’arborescence de domaine ou de la forêt. La prise en charge de groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement Lync Server. Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre pour permettre à un administrateur de gérer les deux.

</div>

<span> </span>

</div>

</div>

</div>

