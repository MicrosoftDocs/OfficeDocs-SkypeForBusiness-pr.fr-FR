---
title: 'Lync Server 2013: cmdlets du serveur du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 634e6ae86a68cece6472d04ba1870159dc9b866f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="489c3-102">Cmdlets du serveur du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="489c3-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="489c3-103">_**Dernière modification de la rubrique:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="489c3-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="489c3-104">Les serveurs de carnets d’adresses sont intermédiaires entre les services de domaine Active Directory et Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="489c3-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="489c3-105">Le serveur du carnet d’adresses vérifie que les informations utilisateur stockées dans Lync Server 2013 sont synchronisées avec les informations utilisateur stockées dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="489c3-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="489c3-106">Pour cela, la synchronisation périodique des fichiers du carnet d’adresses et des informations stockées dans la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="489c3-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="489c3-107">À son tour, Lync Server inclut plusieurs cmdlets pour la gestion des serveurs du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="489c3-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="489c3-108">Cmdlets du serveur du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="489c3-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="489c3-109">Vous ne pouvez pas configurer les paramètres de serveur du carnet d’adresses dans Lync Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="489c3-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="489c3-110">Windows PowerShell est l’outil principal de gestion de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="489c3-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="489c3-111">La liste suivante répertorie les applets de commande qui concernent directement la gestion du serveur du carnet d’adresses:</span><span class="sxs-lookup"><span data-stu-id="489c3-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="489c3-112">**Serveur de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="489c3-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="489c3-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="489c3-114">[Nouveau-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="489c3-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="489c3-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="489c3-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="489c3-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="489c3-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="489c3-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="489c3-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="489c3-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="489c3-121">See Also</span></span>


[<span data-ttu-id="489c3-122">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="489c3-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

