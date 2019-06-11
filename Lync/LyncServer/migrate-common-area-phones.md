---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-29_

Les téléphones portables courants sont les téléphones IP qui se trouvent le plus souvent dans un espace de travail partagé ou une zone commune (par exemple, salle d’attente, cuisine ou étage d’usine). Il n’est pas nécessaire de connecter des téléphones communs à un ordinateur pour fournir une fonctionnalité de communications unifiées Lync Server. Après avoir migré un déploiement de Lync Server 2010 vers Lync Server 2013, vous devez également migrer les objets de contact associés au téléphone de zone commune hérité. À l’aide de Lync Server Management Shell, vous devez d’abord récupérer tous les objets de contact associés aux téléphones de zone commune de Lync Server 2010, puis déplacer ces objets vers le pool Lync Server 2013.

**Migration des téléphones de partie commune**

1.  À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  À partir de la ligne de commande, tapez ce qui suit:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Pour vérifier que tous les objets de contact ont été déplacés vers le pool Lync Server 2013, à partir de Lync Server Management Shell, tapez ce qui suit:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Vérifiez que tous les objets de contact sont désormais associés au pool Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

