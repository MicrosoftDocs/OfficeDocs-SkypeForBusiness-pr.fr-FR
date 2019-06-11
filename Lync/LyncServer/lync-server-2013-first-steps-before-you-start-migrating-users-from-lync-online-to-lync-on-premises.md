---
title: 'Lync Server 2013: premières étapes avant de commencer à migrer des utilisateurs de Lync Online vers Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e278fcb1e63c1db1334e625765d65d5d556e934
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="35ccb-102">Premiers pas avant de commencer à migrer des utilisateurs de Lync Online vers Lync local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ccb-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ccb-103">_**Dernière modification de la rubrique:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="35ccb-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="35ccb-104">Avant de commencer à déplacer des utilisateurs de Lync Online vers votre environnement local, assurez-vous que les conditions suivantes sont remplies:</span><span class="sxs-lookup"><span data-stu-id="35ccb-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="35ccb-105">Votre environnement Lync Server local doit être entièrement déployé et validé.</span><span class="sxs-lookup"><span data-stu-id="35ccb-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="35ccb-106">Pour plus d’informations, reportez-vous à [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="35ccb-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="35ccb-107">Votre client Lync Online doit être configuré pour l’accès PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="35ccb-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="35ccb-108">Pour ce faire, vous devez d’abord installer le module Lync Online pour Windows PowerShell que vous trouverez ici [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911):.</span><span class="sxs-lookup"><span data-stu-id="35ccb-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="35ccb-109">Après avoir installé le module, vous pouvez établir une session distante en tapant les applets de commande suivantes dans Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="35ccb-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```
        Import-Module LyncOnlineConnector
       ```  
    
       ```
        $cred = Get-Credential
       ``` 
    
       ```
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="35ccb-110">Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Lync Online, voir [connexion à Lync Online à l’aide de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="35ccb-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="35ccb-111">Pour plus d’informations sur l’utilisation du module Lync Online PowerShell, reportez-vous à la rubrique [utilisation de Windows PowerShell pour gérer Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="35ccb-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="35ccb-112">Votre Lync Online doit être configuré pour l’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="35ccb-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="35ccb-113">Pour ce faire, commencez par commencer une session PowerShell distante avec Lync Online.</span><span class="sxs-lookup"><span data-stu-id="35ccb-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="35ccb-114">Ensuite, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35ccb-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="35ccb-115">Une fois ces étapes terminées, vous pouvez passer à la [migration des utilisateurs Lync Online vers Lync local dans Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="35ccb-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

