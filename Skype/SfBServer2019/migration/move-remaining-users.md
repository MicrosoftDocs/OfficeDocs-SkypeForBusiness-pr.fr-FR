---
title: Déplacer les utilisateurs restants
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Vous pouvez déplacer des utilisateurs vers le nouveau déploiement de Skype entreprise Server 2019 à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell. Vous devez respecter certaines exigences pour garantir une transition fluide vers Skype entreprise Server 2019. Pour plus d’informations sur les conditions préalables à l’exécution des procédures décrites dans cette rubrique, voir Configurer des clients pour la migration. Pour plus d’informations sur le déplacement des utilisateurs, voir phase 4: déplacer les utilisateurs de test vers le pool de pilotes.'
ms.openlocfilehash: 67bc2d3b239e65b5b1c83e2dcda81a1610d5a31c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273958"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="0caa2-106">Déplacer les utilisateurs restants vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="0caa2-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="0caa2-107">Vous pouvez déplacer des utilisateurs vers le nouveau déploiement de Skype entreprise Server 2019 à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0caa2-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0caa2-108">Vous devez respecter certaines exigences pour garantir une transition fluide vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0caa2-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="0caa2-109">Pour plus d’informations sur les conditions préalables à l’exécution des procédures décrites dans cette rubrique, voir [configurer des clients pour la migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="0caa2-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="0caa2-110">Pour plus d’informations sur le déplacement des utilisateurs, voir [phase 4: déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="0caa2-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0caa2-111">Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration hérités pour déplacer des utilisateurs de votre environnement hérité vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0caa2-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="0caa2-112">Lorsque vous déplacez un utilisateur vers un pool Skype entreprise Server 2019, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="0caa2-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0caa2-113">Cela inclut les réunions actives créées par l’ancien utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0caa2-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="0caa2-114">Par exemple, si un utilisateur hérité a configuré une conférence **ma réunion** , celle-ci sera toujours disponible dans le nouveau pool Skype entreprise Server 2019 après que l’utilisateur a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="0caa2-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="0caa2-115">Les détails permettant d’accéder à cette réunion seront toujours les mêmes **URL et ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="0caa2-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="0caa2-116">La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool 2019 de Skype entreprise Server et non dans le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="0caa2-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0caa2-117">L’hébergement d’utilisateurs sur Skype entreprise Server 2019 ne nécessite pas le déploiement simultané de clients mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="0caa2-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="0caa2-118">Les nouvelles fonctionnalités ne seront accessibles qu’aux utilisateurs qui ont procédé à la mise à niveau vers le nouveau logiciel client.</span><span class="sxs-lookup"><span data-stu-id="0caa2-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="0caa2-119">Tâche après migration</span><span class="sxs-lookup"><span data-stu-id="0caa2-119">Post migration task</span></span>

1. <span data-ttu-id="0caa2-120">Après le déplacement des utilisateurs, vérifiez la stratégie de conférence qui leur est affectée.</span><span class="sxs-lookup"><span data-stu-id="0caa2-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="0caa2-121">Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Skype entreprise Server 2019 fonctionnent en toute transparence avec les utilisateurs fédérés qui sont hébergés sur une installation héritée, la stratégie de conférence affectée aux utilisateurs migrés devrait permettre aux participants anonymes.</span><span class="sxs-lookup"><span data-stu-id="0caa2-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="0caa2-122">Les stratégies de conférence autorisant les participants anonymes ont autorisé les participants à inviter les utilisateurs anonymes sélectionnés dans Skype entreprise 2019 Server AllowAnonymousParticipantsInMeetings panneau de configuration et ont configuré sur true dans la sortie de l’applet de passe **Get-CsConferencingPolicy** dans Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0caa2-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

