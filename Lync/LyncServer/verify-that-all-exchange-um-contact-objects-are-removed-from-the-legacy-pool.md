---
title: Vérifier que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité
description: Vérifiez que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555510"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="65cf4-103">Vérifier que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité</span><span class="sxs-lookup"><span data-stu-id="65cf4-103">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65cf4-104">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="65cf4-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="65cf4-105">Utilisez l’outil **OCSUmUtil** ou la cmdlet **Get-CsExumContact** pour vérifier que les objets contact de messagerie unifiée Exchange ont été supprimés du pool Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="65cf4-105">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="65cf4-106">**OCSUmUtil** se trouve dans le dossier suivant :</span><span class="sxs-lookup"><span data-stu-id="65cf4-106">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="65cf4-107">% Program Files% \\ fichiers communs de \\ \\ prise en charge de Lync Server 2013 \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="65cf4-107">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="65cf4-108">**OCSUmUtil** doit être exécuté à partir d’un compte d’utilisateur qui remplit les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="65cf4-108">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="65cf4-109">appartenance aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins (ce qui inclut les droits de lecture des paramètres de messagerie unifiée Exchange Server) ;</span><span class="sxs-lookup"><span data-stu-id="65cf4-109">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="65cf4-110">autorisations de domaine pour la création d’objets contact dans le conteneur d’unités d’organisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="65cf4-110">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="65cf4-111">Pour plus d’informations sur l’utilisation de la cmdlet **Get-CsExumContact** , voir [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="65cf4-111">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

