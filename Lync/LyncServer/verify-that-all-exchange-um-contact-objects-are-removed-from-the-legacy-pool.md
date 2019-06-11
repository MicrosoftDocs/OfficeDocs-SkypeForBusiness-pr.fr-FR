---
title: Vérifier que tous les objets de contact Exchange UM sont supprimés du pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="5b60b-102">Vérifier que tous les objets de contact Exchange UM sont supprimés du pool hérité</span><span class="sxs-lookup"><span data-stu-id="5b60b-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b60b-103">_**Dernière modification de la rubrique:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="5b60b-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="5b60b-104">Utilisez l’outil **OCSUmUtil** ou l’applet de contrôle **Get-CsExumContact** pour vérifier que les objets de contact de messagerie unifiée Exchange ont été supprimés du pool Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="5b60b-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="5b60b-105">**OCSUmUtil** se trouve dans le dossier suivant:</span><span class="sxs-lookup"><span data-stu-id="5b60b-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="5b60b-106">% Program Files%\\Common Files\\Lync Server 2013\\support\\OcsUMUtil. exe</span><span class="sxs-lookup"><span data-stu-id="5b60b-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="5b60b-107">**OCSUmUtil** doit être exécuté à partir d’un compte d’utilisateur disposant des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="5b60b-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="5b60b-108">Appartenance au groupe RTCUniversalServerAdmins et RTCUniversalUserAdmins (y compris les droits pour lire les paramètres de messagerie unifiée Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="5b60b-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="5b60b-109">Droits de domaine pour créer des objets de contact dans le conteneur d’unité d’organisation (UO) spécifié</span><span class="sxs-lookup"><span data-stu-id="5b60b-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="5b60b-110">Pour plus d’informations sur l’utilisation de l’applet de connexion **Get-CsExumContact** , voir [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5b60b-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

