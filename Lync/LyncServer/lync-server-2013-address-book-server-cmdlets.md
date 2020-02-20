---
title: 'Lync Server 2013 : cmdlets du serveur de carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe9a7462edb8df2741a8c783cff17e62bfe848eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="dd5ed-102">Cmdlets de serveur de carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd5ed-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd5ed-103">_**Dernière modification de la rubrique :** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="dd5ed-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="dd5ed-104">Les serveurs de carnet d’adresses sont des intermédiaires entre les services de domaine Active Directory et Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd5ed-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="dd5ed-105">Le serveur de carnet d’adresses garantit que les informations utilisateur stockées dans Lync Server 2013 sont synchronisées avec les informations utilisateur stockées dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dd5ed-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="dd5ed-106">Pour ce faire, les fichiers de carnet d’adresses sont régulièrement synchronisés avec les informations contenues dans la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd5ed-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="dd5ed-107">En retour, Lync Server inclut un certain nombre d’applets de commande pour la gestion des serveurs de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="dd5ed-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="dd5ed-108">Applets de commande pour le serveur de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="dd5ed-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="dd5ed-109">Vous ne pouvez pas configurer les paramètres du serveur de carnet d’adresses dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd5ed-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="dd5ed-110">Windows PowerShell est l’outil principal pour la gestion de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="dd5ed-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="dd5ed-111">La liste suivante indique les applets de commande directement associées à la gestion des serveurs de carnet d’adresses :</span><span class="sxs-lookup"><span data-stu-id="dd5ed-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="dd5ed-112">**Serveur de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="dd5ed-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="dd5ed-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="dd5ed-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="dd5ed-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="dd5ed-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="dd5ed-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="dd5ed-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="dd5ed-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="dd5ed-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dd5ed-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd5ed-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd5ed-121">See Also</span></span>


[<span data-ttu-id="dd5ed-122">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd5ed-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

