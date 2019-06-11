---
title: 'Lync Server 2013 : Octroi d’autorisations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="d552a-102">Octroi d’autorisations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d552a-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d552a-103">_**Dernière modification de la rubrique:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d552a-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d552a-104">Dans le cas de l’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (UO), ce qui permet aux membres du groupe RTCUniversalServerAdmins dans cette UO d’installer Lync Server 2013 dans le domaine spécifié.</span><span class="sxs-lookup"><span data-stu-id="d552a-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="d552a-105">Lorsque vous accordez des autorisations sur une unité d’organisation, les autorisations suivantes sont octroyées:</span><span class="sxs-lookup"><span data-stu-id="d552a-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="d552a-106">Suit</span><span class="sxs-lookup"><span data-stu-id="d552a-106">Read</span></span>

  - <span data-ttu-id="d552a-107">Écrits</span><span class="sxs-lookup"><span data-stu-id="d552a-107">Write</span></span>

  - <span data-ttu-id="d552a-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="d552a-108">ReadSPN</span></span>

  - <span data-ttu-id="d552a-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="d552a-109">WriteSPN</span></span>

<span data-ttu-id="d552a-110">Dans le cas d’une administration, vous pouvez ajouter des autorisations à des UO spécifiques de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux UO sans avoir besoin d’être membres du groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="d552a-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="d552a-111">Les autorisations ajoutées à l’unité d’organisation spécifiée sont les mêmes que celles apportées par l’applet de passe **Enable-CsAdDomain** aux ordinateurs et aux conteneurs d’UO des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d552a-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d552a-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d552a-112">In This Section</span></span>

  - [<span data-ttu-id="d552a-113">Octroi d’autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d552a-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="d552a-114">Octroi d’autorisations d’unité organisationnelle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d552a-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

