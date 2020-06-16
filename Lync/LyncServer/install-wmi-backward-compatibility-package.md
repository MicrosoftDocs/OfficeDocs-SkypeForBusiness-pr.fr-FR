---
title: Installer le package de compatibilité descendante WMI
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35be17aa08cf26f93a9d4002b23dacdfb35c5143
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Installer le package de compatibilité descendante WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Si vous essayez d’exécuter l’Assistant Fusion du Générateur de topologie sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :

![Message d’erreur WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Message d’erreur WMI")

Si vous essayez d’exécuter l’applet de commande **Merge-CsLegacytopology** sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :

![Erreur du fournisseur WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erreur du fournisseur WMI Windows PowerShell")

Pour installer le package de compatibilité descendante WMI

1.  À partir de votre support d’installation, naviguez jusqu’à \\ Setup \\ AMD64 \\ Setup \\OCSWMIBC.MSI.

2.  Installez OCSWMIBC.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi peut être installé sur tout ordinateur du domaine sur lequel les composants principaux de Lync Server 2013 et Lync Server 2013 Management Shell sont installés, et ayant accès à la topologie Office Communications Server 2007 R2 (fournisseur WMI aux services de domaine Active Directory (AD DS) et SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

