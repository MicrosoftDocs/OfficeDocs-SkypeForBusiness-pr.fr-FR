---
title: Déplacer les utilisateurs restants vers Lync Server 2013
description: Déplacez les utilisateurs restants vers Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291b58d6644f9ac8f10c63f6585ba865602580df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571310"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="3fb7e-103">Déplacer les utilisateurs restants vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fb7e-103">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fb7e-104">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3fb7e-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3fb7e-105">Vous pouvez déplacer des utilisateurs vers le nouveau déploiement Lync Server 2013 à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-105">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="3fb7e-106">Vous devez respecter certaines exigences pour garantir une transition sans complication vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-106">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="3fb7e-107">Pour plus d’informations sur les conditions préalables à la réalisation des procédures de cette rubrique, voir [configure clients for Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="3fb7e-107">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="3fb7e-108">Pour obtenir la procédure détaillée sur le déplacement des utilisateurs, reportez-vous [à la section phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="3fb7e-108">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3fb7e-109">Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration Lync Server 2010 pour déplacer des utilisateurs de votre environnement hérité vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-109">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="3fb7e-110">Lorsque vous déplacez un utilisateur vers un pool Lync Server 2013, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-110">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3fb7e-111">Cela comprend des réunions actives créées par l’utilisateur hérité.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-111">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="3fb7e-112">Par exemple, si un utilisateur hérité a configuré une conférence <STRONG>mon réunion</STRONG> , cette conférence sera toujours disponible dans le nouveau pool Lync Server 2013 une fois que l’utilisateur a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-112">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="3fb7e-113">Les détails permettant d’accéder à cette réunion seront encore les mêmes <STRONG>URL de conférence et ID de conférence</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-113">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="3fb7e-114">La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool Lync Server 2013, et non dans le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-114">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3fb7e-115">Le fait d’héberger des utilisateurs sur Lync Server 2013 n’exige pas que vous déployiez des clients mis à niveau en même temps.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-115">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="3fb7e-116">Les nouvelles fonctionnalités sont disponibles pour les utilisateurs uniquement lorsqu’ils ont effectué la mise à niveau vers le nouveau logiciel client.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-116">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="3fb7e-117">Tâche post-migration</span><span class="sxs-lookup"><span data-stu-id="3fb7e-117">Post Migration Task</span></span>

1.  <span data-ttu-id="3fb7e-118">Une fois que vous avez déplacé des utilisateurs, vérifiez la stratégie de conférence qui leur est attribuée.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-118">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="3fb7e-119">Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Lync Server 2013 fonctionnent de manière transparente avec les utilisateurs fédérés qui sont hébergés sur Lync Server 2010, la stratégie de conférence affectée aux utilisateurs migrés doit autoriser les participants anonymes.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-119">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="3fb7e-120">Les stratégies de conférence qui permettent aux participants anonymes ont **autorisé les participants à inviter des utilisateurs anonymes** sélectionnés dans le panneau de configuration lync Server 2013 et ont **Allowanonymousparticipantsinmeetings ayant** défini sur **true** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-120">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="3fb7e-121">Pour plus d’informations sur la configuration de la stratégie de conférence à l’aide de Lync Server Management Shell, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3fb7e-121">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

