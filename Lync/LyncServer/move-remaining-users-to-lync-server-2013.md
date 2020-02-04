---
title: Déplacement des autres utilisateurs vers Lync Server 2013
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
ms.openlocfilehash: 4d60b3ba622e88978a8bbf555972c95979e8f8c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="80922-102">Déplacement des autres utilisateurs vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80922-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80922-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="80922-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="80922-104">Vous pouvez déplacer des utilisateurs vers le nouveau déploiement de Lync Server 2013 à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="80922-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="80922-105">Vous devez respecter certaines exigences pour garantir une transition fluide vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80922-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="80922-106">Pour plus d’informations sur les conditions préalables à l’exécution des procédures décrites dans cette rubrique, voir [configurer des clients pour la migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="80922-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="80922-107">Pour plus d’informations sur le déplacement des utilisateurs, voir [phase 4 : déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="80922-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80922-108">Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration de Lync Server 2010 pour déplacer des utilisateurs de votre environnement hérité vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80922-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="80922-109">Lorsque vous déplacez un utilisateur vers un pool Lync Server 2013, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="80922-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80922-110">Cela inclut les réunions actives créées par l’ancien utilisateur.</span><span class="sxs-lookup"><span data-stu-id="80922-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="80922-111">Par exemple, si un utilisateur hérité a configuré une conférence <STRONG>ma réunion</STRONG> , celle-ci restera disponible dans le nouveau pool Lync Server 2013 après que l’utilisateur a été déplacé.</span><span class="sxs-lookup"><span data-stu-id="80922-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="80922-112">Les détails permettant d’accéder à cette réunion seront toujours les mêmes <STRONG>URL et ID de conférence</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="80922-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="80922-113">La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool Lync Server 2013 sans le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="80922-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="80922-114">L’hébergement d’utilisateurs sur Lync Server 2013 ne nécessite pas le déploiement simultané de clients mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="80922-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="80922-115">Les nouvelles fonctionnalités ne seront accessibles qu’aux utilisateurs qui ont procédé à la mise à niveau vers le nouveau logiciel client.</span><span class="sxs-lookup"><span data-stu-id="80922-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="80922-116">Tâche après migration</span><span class="sxs-lookup"><span data-stu-id="80922-116">Post Migration Task</span></span>

1.  <span data-ttu-id="80922-117">Après le déplacement des utilisateurs, vérifiez la stratégie de conférence qui leur est affectée.</span><span class="sxs-lookup"><span data-stu-id="80922-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="80922-118">Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Lync Server 2013 fonctionnent en toute transparence avec les utilisateurs fédérés qui sont hébergés sur Lync Server 2010, la stratégie de conférence affectée aux utilisateurs migrés devrait permettre aux participants anonymes.</span><span class="sxs-lookup"><span data-stu-id="80922-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="80922-119">Les stratégies de conférence autorisant les participants anonymes ont la **possibilité d’inviter les utilisateurs anonymes** sélectionnés dans lync Server 2013 panneau de configuration et de définir **AllowAnonymousParticipantsInMeetings** sur **true** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="80922-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="80922-120">Pour plus d’informations sur la configuration d’une stratégie de conférence à l’aide de Lync Server Management Shell, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="80922-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

