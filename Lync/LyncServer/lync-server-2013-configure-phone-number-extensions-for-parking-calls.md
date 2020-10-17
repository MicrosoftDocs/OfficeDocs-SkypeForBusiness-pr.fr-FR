---
title: 'Lync Server 2013 : configuration des extensions de numéros de téléphone pour les appels de parking'
description: 'Lync Server 2013 : configurez les extensions de numéros de téléphone pour les appels de parking.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548830"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="7d9aa-103">Configurer les extensions de numéros de téléphone pour les appels de parking dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d9aa-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d9aa-104">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="7d9aa-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="7d9aa-105">L’application de parcage d’appel utilise des numéros de poste dans la table des orbites de parcage d’appel pour Park Calls.</span><span class="sxs-lookup"><span data-stu-id="7d9aa-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="7d9aa-106">Vous devez configurer la table d’orbites de parcage d’appel avec les plages de numéros de poste que votre organisation réserve pour les appels parqués.</span><span class="sxs-lookup"><span data-stu-id="7d9aa-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="7d9aa-107">Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné).</span><span class="sxs-lookup"><span data-stu-id="7d9aa-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="7d9aa-108">Chaque pool Lync Server où une application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbites.</span><span class="sxs-lookup"><span data-stu-id="7d9aa-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="7d9aa-109">Les plages d’orbites doivent être uniques au niveau global dans le déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d9aa-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7d9aa-110">Vous devez activer la case à cocher <STRONG>activer le parcage d’appel</STRONG> dans votre stratégie de voix avant de pouvoir utiliser le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d9aa-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="7d9aa-111">Par défaut, cette option n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7d9aa-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d9aa-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7d9aa-112">In This Section</span></span>

  - [<span data-ttu-id="7d9aa-113">Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d9aa-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="7d9aa-114">Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d9aa-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

