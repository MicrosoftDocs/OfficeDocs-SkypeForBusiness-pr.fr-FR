---
title: Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="69009-102">Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69009-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="69009-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="69009-p101">Les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter à la stratégie des enregistrements d’utilisation RTC, qui spécifient les droits accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation RTC, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs ne peuvent effectuer que des appels utilisant des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation RTC correspondants.</span><span class="sxs-lookup"><span data-stu-id="69009-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="69009-108">La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer par configurer une stratégie de voix qui comprend les enregistrements d’utilisation RTC appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="69009-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="69009-109">Vous pouvez également créer des stratégies de voix avec l’étendue d’<EM>utilisateur</EM> et les affecter à des utilisateurs ou à des groupes individuels.</span><span class="sxs-lookup"><span data-stu-id="69009-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="69009-110">Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, reportez-vous aux procédures de cette section.</span><span class="sxs-lookup"><span data-stu-id="69009-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69009-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="69009-111">In This Section</span></span>

  - [<span data-ttu-id="69009-112">Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="69009-113">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="69009-114">Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="69009-115">Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="69009-116">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="69009-117">Test du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69009-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

