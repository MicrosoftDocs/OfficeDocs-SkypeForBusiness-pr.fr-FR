---
title: 'Lync Server 2013 : New-CsClientPolicy pour la gestion du carnet d’adresses'
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
ms.openlocfilehash: 3f68f6cfa2fde4d1e5a2bc58a36478a60060dd5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0f80e-102">Nouveauté-CsClientPolicy pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f80e-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f80e-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0f80e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0f80e-104">Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande New-CsClientPolicy : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0f80e-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="0f80e-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="0f80e-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="0f80e-106">Le cmdlet New-CsClientPolicy définit un grand nombre de paramètres pour les clients de mise en service pour les fonctionnalités disponibles dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f80e-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="0f80e-107">Pour le service de carnet d’adresses, le paramètre AddressBookAvailability est intéressant.</span><span class="sxs-lookup"><span data-stu-id="0f80e-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="0f80e-108">Ce paramètre a un impact direct sur les options disponibles pour les clients et propose trois options possibles :</span><span class="sxs-lookup"><span data-stu-id="0f80e-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="0f80e-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="0f80e-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="0f80e-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="0f80e-110">WebSearchOnly</span></span>

  - <span data-ttu-id="0f80e-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="0f80e-111">FileDownloadOnly</span></span>

<span data-ttu-id="0f80e-112">Détermine la manière dont les clients peuvent accéder au carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0f80e-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="0f80e-113">Si vous définissez ce paramètre, vous devez définir une des options.</span><span class="sxs-lookup"><span data-stu-id="0f80e-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="0f80e-114">Si vous ne modifiez pas ce paramètre, le WebSearchAndFileDownload par défaut reste en vigueur.</span><span class="sxs-lookup"><span data-stu-id="0f80e-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="0f80e-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0f80e-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="0f80e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f80e-116">See Also</span></span>


[<span data-ttu-id="0f80e-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0f80e-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

