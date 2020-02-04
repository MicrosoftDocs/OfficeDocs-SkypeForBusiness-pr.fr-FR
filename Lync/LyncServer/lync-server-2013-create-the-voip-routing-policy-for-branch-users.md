---
title: 'Lync Server 2013 : Création de la stratégie de routage VoIP pour les utilisateurs de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="cb69e-102">Création de la stratégie de routage VoIP pour les utilisateurs de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb69e-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb69e-103">_**Dernière modification de la rubrique :** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="cb69e-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="cb69e-104">Nous vous recommandons de créer une stratégie VoIP (Voice over IP) distincte pour les utilisateurs des sites de succursales.</span><span class="sxs-lookup"><span data-stu-id="cb69e-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="cb69e-105">Cette stratégie doit contenir des itinéraires vers la sortie à partir de la passerelle de l’appareil de branchement survivant ou de la passerelle externe du serveur de succursales survivant et des itinéraires de sauvegarde vers la sortie à partir d’une passerelle sur le site central.</span><span class="sxs-lookup"><span data-stu-id="cb69e-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="cb69e-106">Quel que soit l’endroit où l’utilisateur est inscrit, soit dans le Bureau d’enregistrement sur l’appareil de succursale survivant ou sur le serveur de succursales survivant, soit dans le groupe d’inscriptions de secours sur le site central, la stratégie VoIP de l’utilisateur est toujours en vigueur.</span><span class="sxs-lookup"><span data-stu-id="cb69e-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="cb69e-107">Pour configurer la stratégie de routage VoIP pour les utilisateurs de succursales</span><span class="sxs-lookup"><span data-stu-id="cb69e-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="cb69e-108">Créer un plan de numérotation utilisateur et l’affecter aux utilisateurs de succursales.</span><span class="sxs-lookup"><span data-stu-id="cb69e-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="cb69e-109">(Pour plus d’informations, reportez-vous à la rubrique [création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) .)</span><span class="sxs-lookup"><span data-stu-id="cb69e-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="cb69e-110">Affectez des règles de normalisation correspondant aux habitudes de numérotation des utilisateurs sur ce site.</span><span class="sxs-lookup"><span data-stu-id="cb69e-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="cb69e-111">Dans le cas où l’utilisateur de l’unité de branchement survivant ou du serveur de succursale Survivable bascule vers le pool d’inscriptions de secours sur le site central, le même plan de numérotation sera appliqué.</span><span class="sxs-lookup"><span data-stu-id="cb69e-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="cb69e-112">(Pour plus d’informations, reportez-vous à la rubrique [création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) .)</span><span class="sxs-lookup"><span data-stu-id="cb69e-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="cb69e-113">Configurez un itinéraire vocal qui egresses à partir de la passerelle de l’appareil de succursale survivant ou de la passerelle externe du serveur de succursales survivant.</span><span class="sxs-lookup"><span data-stu-id="cb69e-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="cb69e-114">(Pour plus d’informations, reportez-vous à la rubrique [création d’un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) .)</span><span class="sxs-lookup"><span data-stu-id="cb69e-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="cb69e-115">Définissez un itinéraire de sauvegarde sur l’appareil de branchement survivant ou la passerelle du serveur de succursales survivant pour qu’il pointe vers le pool de bureau d’enregistrement de sauvegarde (colocalisé avec le serveur de médiation) sur le site central.</span><span class="sxs-lookup"><span data-stu-id="cb69e-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="cb69e-116">(Voir votre appareil de succursale survivant ou la documentation du fournisseur de votre serveur de succursales survivant.)</span><span class="sxs-lookup"><span data-stu-id="cb69e-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb69e-117">Cette opération de sauvegarde de l’itinéraire permet de garantir que les appels entrants de l’utilisateur de la succursale fonctionneront lorsque l’unité de branchement ou le serveur de succursale Survivable ne sera pas disponible (par exemple, s’il est arrêté pour maintenance).</span><span class="sxs-lookup"><span data-stu-id="cb69e-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="cb69e-118">Si le serveur d’inscriptions et de médiation sur l’appareil de branchement survivant ou la succursale Survivable ne sont pas disponibles, et si l’utilisateur est inscrit auprès du pool d’inscriptions de sauvegarde au niveau du site central, les appels entrants peuvent toujours être routés vers l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb69e-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="cb69e-119">**Étape suivante**: [configurer les paramètres de reroutage de la messagerie vocale dans Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cb69e-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

