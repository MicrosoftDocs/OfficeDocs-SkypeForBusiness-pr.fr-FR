---
title: 'Lync Server 2013 : New-CsClientPolicy pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a253fb46dfdfe63957efa97ffa68d97ead65ed87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508821"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2b1ec-102">New-CsClientPolicy pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1ec-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b1ec-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2b1ec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2b1ec-104">Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande New-CsClientPolicy : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2b1ec-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="2b1ec-105">Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="2b1ec-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="2b1ec-106">L’applet de commande New-CsClientPolicy définit un grand nombre de paramètres pour la mise en service des clients pour les fonctionnalités disponibles dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b1ec-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="2b1ec-107">Pour le service de carnet d’adresses, le paramètre AddressBookAvailability est intéressant.</span><span class="sxs-lookup"><span data-stu-id="2b1ec-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="2b1ec-108">Ce paramètre, qui influe directement sur les options disponibles pour les clients, comporte trois options possibles :</span><span class="sxs-lookup"><span data-stu-id="2b1ec-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="2b1ec-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="2b1ec-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="2b1ec-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="2b1ec-110">WebSearchOnly</span></span>

  - <span data-ttu-id="2b1ec-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="2b1ec-111">FileDownloadOnly</span></span>

<span data-ttu-id="2b1ec-112">Lorsqu’il est défini, il détermine comment les clients accèdent au carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="2b1ec-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="2b1ec-113">Si vous définissez ce paramètre, vous devez définir l’une des options.</span><span class="sxs-lookup"><span data-stu-id="2b1ec-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="2b1ec-114">Si vous ne modifiez pas ce paramètre, le WebSearchAndFileDownload par défaut reste en vigueur.</span><span class="sxs-lookup"><span data-stu-id="2b1ec-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="2b1ec-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2b1ec-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="2b1ec-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b1ec-116">See Also</span></span>


[<span data-ttu-id="2b1ec-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2b1ec-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

