---
title: Installer le package de compatibilité descendante WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59e3ea03b3b6f4085f8acf461b1da3f32e21fa9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199397"
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

1.  À partir de votre support d’installation \\,\\naviguez jusqu’à Setup amd64\\Setup\\OCSWMIBC. MSP.

2.  Installez OCSWMIBC.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi doit être installé sur l’ordinateur sur lequel l’Assistant Fusion du Générateur de topologie s’exécute. Toutefois, nous recommandons d’installer OCSWMIBC.msi sur tous les serveurs frontaux de votre topologie.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi peut être installé sur tout ordinateur du domaine sur lequel les composants principaux Lync Server 2013 et Lync Server 2013 Management Shell sont installés, et ayant accès à la topologie Office Communications Server 2007 R2 (fournisseur WMI dans le domaine Active Directory Services (AD DS) et SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

