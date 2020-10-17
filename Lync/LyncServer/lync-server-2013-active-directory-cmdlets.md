---
title: 'Lync Server 2013 : applets de commande Active Directory'
description: 'Lync Server 2013 : applets de commande Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5e87cda24d5517b9c4501523fd06804ea20020
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571080"
---
# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="345db-103">Applets de commande Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="345db-103">Active Directory cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="345db-104">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="345db-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="345db-105">Les applets de commande Active Directory sont généralement utilisées par le programme d’installation et sont rarement directement appelées par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="345db-105">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="345db-106">Toutefois, les administrateurs peuvent utiliser ces cmdlets pour préparer (ou désinstaller) un domaine ou une forêt pour Microsoft Lync Server 2013, et pour installer les fichiers de schéma Active Directory requis.</span><span class="sxs-lookup"><span data-stu-id="345db-106">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="345db-107">Applets de commande Active Directory</span><span class="sxs-lookup"><span data-stu-id="345db-107">Active Directory Cmdlets</span></span>

<span data-ttu-id="345db-108">La liste suivante répertorie les applets de commande qui sont directement liées à la gestion des paramètres Active Directory de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="345db-108">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="345db-109">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="345db-109">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="345db-110">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-110">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="345db-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="345db-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="345db-113">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-113">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="345db-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="345db-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="345db-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="345db-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="345db-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="345db-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="345db-118">See Also</span></span>


[<span data-ttu-id="345db-119">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="345db-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

