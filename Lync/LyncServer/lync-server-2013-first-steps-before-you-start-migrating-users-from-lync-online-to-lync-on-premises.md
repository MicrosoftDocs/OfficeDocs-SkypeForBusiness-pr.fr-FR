---
title: 'Lync Server 2013 : premières étapes avant de commencer à migrer des utilisateurs de Lync Online vers Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59ca20a994934a199504a4fb6a7dd5eec206c960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Premiers pas avant de commencer à migrer des utilisateurs de Lync Online vers Lync local dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-08_

Avant de commencer à déplacer des utilisateurs de Lync Online vers votre environnement local, assurez-vous que les conditions suivantes sont remplies :

  - Votre environnement Lync Server local doit être entièrement déployé et validé. Pour plus d’informations, reportez-vous à [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Votre client Lync Online doit être configuré pour l’accès PowerShell à distance.
    
    Pour ce faire, vous devez d’abord installer le module Lync Online pour Windows PowerShell que vous trouverez ici [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911):.
    
    Après avoir installé le module, vous pouvez établir une session distante en tapant les applets de commande suivantes dans Lync Server Management Shell :
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Lync Online, voir [connexion à Lync Online à l’aide de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Pour plus d’informations sur l’utilisation du module Lync Online PowerShell, reportez-vous à la rubrique [utilisation de Windows PowerShell pour gérer Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Votre Lync Online doit être configuré pour l’espace d’adressage SIP partagé. Pour ce faire, commencez par commencer une session PowerShell distante avec Lync Online. Ensuite, exécutez l’applet de commande suivante :
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Une fois ces étapes terminées, vous pouvez passer à la [migration des utilisateurs Lync Online vers Lync local dans Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

