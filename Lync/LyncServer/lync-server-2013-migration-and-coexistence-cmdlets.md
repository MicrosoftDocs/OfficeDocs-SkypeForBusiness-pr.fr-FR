---
title: 'Lync Server 2013 : applets de commande de migration et de coexistence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence cmdlets
ms:assetid: ff1a56e0-e883-473d-92fe-ca77ea4eb63b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415682(v=OCS.15)
ms:contentKeyID: 48185968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20e2931dc24e96243b2e80eb0abd0cf3b50599ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="41692-102">Applets de commande de migration et de coexistence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41692-102">Migration and coexistence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41692-103">_**Dernière modification de la rubrique :** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="41692-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="41692-104">L’applet de commande [Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15)) vous permet de déplacer des comptes d’utilisateur à partir d’Office Communications Server 2007 ou Microsoft lync Server 2010 vers Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41692-104">The [Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15)) cmdlet provides a way for you to move user accounts from Office Communications Server 2007 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="41692-105">Si vous devez déplacer un compte d’utilisateur vers l’arrière (par exemple, à partir de Microsoft Lync Server 2013 vers Microsoft Lync Server 2010), utilisez la cmdlet [Move-Csuser](https://technet.microsoft.com/library/Gg398528(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="41692-105">If you need to move a user account "backward" (for example, from Microsoft Lync Server 2013 to Microsoft Lync Server 2010) use the [Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15)) cmdlet.</span></span>

  - <span></span>  
    <span data-ttu-id="41692-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="41692-107">[Import-applet cslegacyconfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-107">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="41692-108">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-108">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="41692-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="41692-110">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-110">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="41692-111">[Convert-applet csuserdata](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-111">[Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="41692-112">[Export-applet csuserdata](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-112">[Export-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="41692-113">[Import-applet csuserdata](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-113">[Import-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="41692-114">[Update-applet csuserdata](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="41692-114">[Update-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="41692-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41692-115">See Also</span></span>


[<span data-ttu-id="41692-116">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="41692-116">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

