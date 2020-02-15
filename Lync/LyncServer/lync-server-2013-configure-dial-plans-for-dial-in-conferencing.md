---
title: 'Lync Server 2013 : configuration des plans de numérotation pour les conférences rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28dd2ddb0633a45d19f1a7bb7638d86e042658b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="b787b-102">Configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b787b-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b787b-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="b787b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="b787b-p101">Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant. Veillez à ce qu’au moins une règle de normalisation dans chaque plan convertisse les numéros de poste en numéros de téléphone complets au format E.164. Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir des postes en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="b787b-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="b787b-108">Pour configurer des plans de numérotation pour la conférence rendez-vous, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b787b-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="b787b-109">Si vous déployez voix entreprise ou non, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et vous assurer qu’une règle de normalisation convertit correctement vos numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="b787b-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="b787b-110">Pour obtenir des instructions détaillées, consultez [la rubrique modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="b787b-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="b787b-111">Si vous n’avez pas déployé voix entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b787b-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="b787b-112">Veillez à inclure une région de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b787b-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="b787b-113">Pour obtenir des instructions détaillées, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="b787b-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="b787b-114">Si vous avez déployé voix entreprise, modifiez les plans de numérotation de voix entreprise selon vos besoins pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="b787b-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="b787b-115">Pour obtenir des instructions détaillées, consultez [la rubrique modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="b787b-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="b787b-116">Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="b787b-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="b787b-117">Pour obtenir des instructions détaillées, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="b787b-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="b787b-118">Pour plus d’informations sur la planification des régions, voir Configuration requise pour les conférences rendez [-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b787b-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b787b-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b787b-119">In This Section</span></span>

  - [<span data-ttu-id="b787b-120">Afficher les informations de plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b787b-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="b787b-121">Création d’un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b787b-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="b787b-122">Modifier un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b787b-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="b787b-123">Définition de règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b787b-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

