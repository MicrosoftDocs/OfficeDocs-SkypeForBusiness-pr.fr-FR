---
title: 'Lync Server 2013 : octroi d’autorisations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 495b556254ab42270aa031861aea0c4390f17602
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="2fbd3-102">Octroi d’autorisations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fbd3-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fbd3-103">_**Dernière modification de la rubrique :** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="2fbd3-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="2fbd3-104">Pour le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, permettant ainsi aux membres du groupe RTCUniversalServerAdmins dans cette unité d’organisation d’installer Lync Server 2013 dans le domaine spécifié.</span><span class="sxs-lookup"><span data-stu-id="2fbd3-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="2fbd3-105">Quand vous octroyez des autorisations à une unité d’organisation, vous octroyez les autorisations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2fbd3-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="2fbd3-106">Lecture</span><span class="sxs-lookup"><span data-stu-id="2fbd3-106">Read</span></span>

  - <span data-ttu-id="2fbd3-107">Write</span><span class="sxs-lookup"><span data-stu-id="2fbd3-107">Write</span></span>

  - <span data-ttu-id="2fbd3-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="2fbd3-108">ReadSPN</span></span>

  - <span data-ttu-id="2fbd3-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="2fbd3-109">WriteSPN</span></span>

<span data-ttu-id="2fbd3-110">En ce qui concerne l’administration, vous pouvez ajouter des autorisations aux unités d’organisation spécifiées afin que les membres des groupes universels RTC créés pendant la préparation de la forêt puissent y accéder sans avoir besoin d’appartenir au groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="2fbd3-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="2fbd3-111">Les autorisations ajoutées à l’unité d’organisation spécifiée sont identiques à celles que la cmdlet **Enable-CsAdDomain** ajoute aux conteneurs d’unités d’organisation d’ordinateurs et d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2fbd3-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2fbd3-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2fbd3-112">In This Section</span></span>

  - [<span data-ttu-id="2fbd3-113">Octroi d’autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fbd3-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="2fbd3-114">Octroi d’autorisations d’unité d’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fbd3-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

