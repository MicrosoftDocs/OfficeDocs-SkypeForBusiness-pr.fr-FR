---
title: 'Lync Server 2013 : premières étapes préalables à la migration des utilisateurs de Lync Online vers Lync en local'
description: 'Lync Server 2013 : premières étapes avant de commencer à migrer des utilisateurs de Lync Online vers Lync en local.'
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
ms.openlocfilehash: 408820e461c0a9f7c0beaaaae3a502802048d3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564200"
---
# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Premières étapes avant de commencer la migration des utilisateurs de Lync Online vers Lync sur site dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-08_

Avant de commencer à transférer des utilisateurs Lync Online vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :

  - Votre environnement Lync Server local doit être entièrement déployé et validé. Pour plus d’informations, consultez la rubrique [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Votre client Lync Online doit être configuré pour l’accès à PowerShell à distance.
    
    Pour ce faire, commencez par installer le module Lync Online pour Windows PowerShell, que vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .
    
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
    
    Pour plus d’informations sur la façon d’établir une session PowerShell distante avec Lync Online, consultez la rubrique [connexion à Lync Online à l’aide de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Pour plus d’informations sur l’utilisation du module Lync Online PowerShell, voir [Using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Votre Lync Online doit être configuré pour l’espace d’adressage SIP partagé. Pour ce faire, commencez par démarrer une session PowerShell distante avec Lync Online. Exécutez ensuite l’applet de commande suivante :
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Une fois que vous avez terminé ces étapes, vous pouvez passer à la [migration des utilisateurs Lync Online vers Lync sur site dans Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

