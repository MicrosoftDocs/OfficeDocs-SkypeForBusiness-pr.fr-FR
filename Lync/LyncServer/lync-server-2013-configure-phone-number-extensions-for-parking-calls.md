---
title: 'Lync Server 2013 : configurer les extensions de numéro de téléphone pour les appels en stationnement'
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
ms.openlocfilehash: ba64f4f622a6f9ae9e134b2447abe21bc99ec62c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="86170-102">Configurer les extensions de numéro de téléphone pour les appels de parking dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86170-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86170-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="86170-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="86170-104">L’application de parc d’appels utilise des numéros d’extension dans la table de parc d’appels pour les appels de parc.</span><span class="sxs-lookup"><span data-stu-id="86170-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="86170-105">Vous devez configurer la table d’orbite du parc d’appels avec les plages de numéros d’extension que votre organisation réserve pour les appels en stationnement.</span><span class="sxs-lookup"><span data-stu-id="86170-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="86170-106">Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté).</span><span class="sxs-lookup"><span data-stu-id="86170-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="86170-107">Chaque pool de serveurs Lync dans lequel une application de parc d’appels est déployée et configurée peut avoir une ou plusieurs plages d’orbite.</span><span class="sxs-lookup"><span data-stu-id="86170-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="86170-108">Les plages orbites doivent être globalement uniques dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86170-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86170-109">Vous devez activer la case à cocher <STRONG>activer le parc d’appels</STRONG> dans votre politique vocale pour pouvoir utiliser le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="86170-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="86170-110">Par défaut, cette option n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="86170-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86170-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="86170-111">In This Section</span></span>

  - [<span data-ttu-id="86170-112">Créer ou modifier une gamme de parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86170-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="86170-113">Supprimer une gamme de stationnement d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86170-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

