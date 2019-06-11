---
title: Installer le package de compatibilité descendante WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b61d34ce8809f06156f4d4dca61c39cc4aff0f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Installer le package de compatibilité descendante WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Si vous essayez d’exécuter l’Assistant Fusion du générateur de topologie sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche:

![Message d’erreur WMI] (images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Message d’erreur WMI")

Si vous essayez d’exécuter l’applet **de commande Merge-CsLegacytopology** sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche:

![Erreur du fournisseur WMI Windows PowerShell] (images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erreur du fournisseur WMI Windows PowerShell")

Pour installer le package de compatibilité descendante WMI

1.  À partir de votre support d’installation \\,\\accédez\\à\\configuration de configuration de OCSWMIBC. Portion.

2.  Installez OCSWMIBC. Portion.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi doit être installé sur l’ordinateur sur lequel s’exécute l’Assistant Fusion du générateur de topologie. Toutefois, nous vous recommandons d’installer OCSWMIBC. msi sur tous les serveurs frontaux de votre topologie.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi peut être installé sur n’importe quel ordinateur du domaine sur lequel sont installés les composants principaux de Lync Server 2013 et Lync Server 2013 Management Shell et ayant accès à la topologie Office Communications Server 2007 R2 (fournisseur WMI sur le domaine Active Directory) Services (AD DS) et SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

