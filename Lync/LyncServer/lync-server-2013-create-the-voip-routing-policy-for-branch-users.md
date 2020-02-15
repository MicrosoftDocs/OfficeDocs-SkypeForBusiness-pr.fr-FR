---
title: 'Lync Server 2013 : création de la stratégie de routage VoIP pour les utilisateurs de succursale'
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
ms.openlocfilehash: 308c4ad3a7371c9a27f668b79623a512227623b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="28f23-102">Création de la stratégie de routage VoIP pour les utilisateurs de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28f23-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28f23-103">_**Dernière modification de la rubrique :** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="28f23-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="28f23-104">Nous vous recommandons de créer une stratégie de Voix sur IP (VoIP) distincte pour les utilisateurs sur des sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="28f23-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="28f23-105">Cette stratégie doit contenir des itinéraires vers une sortie à partir de la passerelle Survivable Branch Appliance ou de la passerelle externe du serveur Survivable Branch Server et des itinéraires de sauvegarde vers une sortie à partir d’une passerelle sur le site central.</span><span class="sxs-lookup"><span data-stu-id="28f23-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="28f23-106">Quel que soit l’emplacement d’enregistrement de l’utilisateur, soit sur le serveur d’inscriptions sur le Survivable Branch appliance, soit sur le serveur Survivable Branch Server, ou sur le cluster de serveurs d’inscriptions de sauvegarde du site central, la stratégie VoIP de l’utilisateur est toujours en vigueur.</span><span class="sxs-lookup"><span data-stu-id="28f23-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="28f23-107">Pour configurer la stratégie de routage VoIP pour les utilisateurs de sites de succursale</span><span class="sxs-lookup"><span data-stu-id="28f23-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="28f23-108">Créez un plan de numérotation utilisateur et affectez-le aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="28f23-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="28f23-109">(Voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) dans la documentation des opérations.)</span><span class="sxs-lookup"><span data-stu-id="28f23-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="28f23-110">Affectez les règles de normalisation correspondantes aux habitudes de numérotation des utilisateurs sur ce site.</span><span class="sxs-lookup"><span data-stu-id="28f23-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="28f23-111">Si l’utilisateur Survivable Branch Appliance ou le serveur Survivable Branch Server bascule vers le pool de serveurs d’inscriptions de sauvegarde sur le site central, le même plan de numérotation sera appliqué.</span><span class="sxs-lookup"><span data-stu-id="28f23-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="28f23-112">(Voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) dans la documentation des opérations.)</span><span class="sxs-lookup"><span data-stu-id="28f23-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="28f23-113">Configurez un itinéraire des communications vocales qui egresses à partir de la passerelle Survivable Branch Appliance ou de la passerelle externe du serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="28f23-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="28f23-114">(Voir [créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) dans la documentation des opérations.)</span><span class="sxs-lookup"><span data-stu-id="28f23-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="28f23-115">Définissez un itinéraire d’appel de sauvegarde sur le Survivable Branch Appliance ou le Survivable Branch Server Gateway de manière à pointer vers le pool de serveurs d’inscriptions de sauvegarde (colocalisé avec le serveur de médiation) sur le site central.</span><span class="sxs-lookup"><span data-stu-id="28f23-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="28f23-116">(Consultez votre Survivable Branch Appliance ou la documentation du fournisseur Survivable Branch Server.)</span><span class="sxs-lookup"><span data-stu-id="28f23-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28f23-117">Cette configuration de l’acheminement des appels permet de s’assurer que les appels entrants vers l’utilisateur de succursale fonctionnent lorsque le Survivable Branch Appliance ou le serveur Survivable Branch Server n’est pas disponible (par exemple, s’il est arrêté pour maintenance).</span><span class="sxs-lookup"><span data-stu-id="28f23-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="28f23-118">Si le serveur d’inscriptions et de médiation sur le Survivable Branch Appliance ou le serveur Survivable Branch Server ne sont pas disponibles et que l’utilisateur est inscrit auprès du pool de serveurs d’inscriptions de sauvegarde sur le site central, les appels entrants peuvent toujours être acheminés vers l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28f23-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="28f23-119">**Étape suivante**: [configurer les paramètres de réacheminement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28f23-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

