---
title: 'Lync Server 2013 : premières étapes préalables à la migration des utilisateurs de Lync Online vers Lync en local'
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
ms.openlocfilehash: 4165df6829818b90a22eff4f90ac8072876b4831
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="aec31-102">Premières étapes avant de commencer la migration des utilisateurs de Lync Online vers Lync sur site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aec31-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aec31-103">_**Dernière modification de la rubrique :** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="aec31-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="aec31-104">Avant de commencer à transférer des utilisateurs Lync Online vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="aec31-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="aec31-105">Votre environnement Lync Server local doit être entièrement déployé et validé.</span><span class="sxs-lookup"><span data-stu-id="aec31-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="aec31-106">Pour plus d’informations, consultez la rubrique [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="aec31-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="aec31-107">Votre client Lync Online doit être configuré pour l’accès à PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="aec31-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="aec31-108">Pour ce faire, commencez par installer le module Lync Online pour Windows PowerShell, que vous pouvez obtenir ici [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911):.</span><span class="sxs-lookup"><span data-stu-id="aec31-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="aec31-109">Après avoir installé le module, vous pouvez établir une session distante en tapant les applets de commande suivantes dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="aec31-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
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
    
    <span data-ttu-id="aec31-110">Pour plus d’informations sur la façon d’établir une session PowerShell distante avec Lync Online, consultez la rubrique [connexion à Lync Online à l’aide de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="aec31-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="aec31-111">Pour plus d’informations sur l’utilisation du module Lync Online PowerShell, voir [Using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="aec31-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="aec31-112">Votre Lync Online doit être configuré pour l’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="aec31-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="aec31-113">Pour ce faire, commencez par démarrer une session PowerShell distante avec Lync Online.</span><span class="sxs-lookup"><span data-stu-id="aec31-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="aec31-114">Exécutez ensuite l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="aec31-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="aec31-115">Une fois que vous avez terminé ces étapes, vous pouvez passer à la [migration des utilisateurs Lync Online vers Lync sur site dans Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="aec31-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

