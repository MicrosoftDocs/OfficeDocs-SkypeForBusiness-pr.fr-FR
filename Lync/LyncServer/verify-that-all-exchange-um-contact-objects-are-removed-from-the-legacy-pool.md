---
title: Vérifier que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="7edeb-102">Vérifier que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité</span><span class="sxs-lookup"><span data-stu-id="7edeb-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7edeb-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="7edeb-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="7edeb-104">Utilisez l’outil **OCSUmUtil** ou la cmdlet **Get-CsExumContact** pour vérifier que les objets contact de messagerie unifiée Exchange ont été supprimés du pool Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="7edeb-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="7edeb-105">**OCSUmUtil** se trouve dans le dossier suivant :</span><span class="sxs-lookup"><span data-stu-id="7edeb-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="7edeb-106">% Program Files%\\Common Files\\Lync Server 2013\\support\\OcsUMUtil. exe</span><span class="sxs-lookup"><span data-stu-id="7edeb-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="7edeb-107">**OCSUmUtil** doit être exécuté à partir d’un compte d’utilisateur qui remplit les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7edeb-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="7edeb-108">appartenance aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins (ce qui inclut les droits de lecture des paramètres de messagerie unifiée Exchange Server) ;</span><span class="sxs-lookup"><span data-stu-id="7edeb-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="7edeb-109">autorisations de domaine pour la création d’objets contact dans le conteneur d’unités d’organisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="7edeb-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="7edeb-110">Pour plus d’informations sur l’utilisation de la cmdlet **Get-CsExumContact** , voir [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7edeb-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

