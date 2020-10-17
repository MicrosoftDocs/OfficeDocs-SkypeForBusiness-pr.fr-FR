---
title: Conditions préalables à la configuration de la prise d’appel de groupe et droits de l’utilisateur
description: Conditions préalables à la configuration de la prise d’appel de groupe et droits de l’utilisateur.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554450"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="bd73d-103">Conditions préalables à la configuration de la prise d’appel de groupe et droits de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd73d-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd73d-104">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="bd73d-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="bd73d-105">La prise d’appel de groupe est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="bd73d-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bd73d-106">Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer la prise d’appel de groupe et les droits d’utilisateur dont vous avez besoin pour effectuer des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="bd73d-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="bd73d-107">Cette section suppose que vous avez lu la documentation de planification relative à la prise d’appel de groupe (voir [planification de la prise d’appel de groupe dans Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="bd73d-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="bd73d-108">Conditions préalables à la configuration de la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="bd73d-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="bd73d-109">La prise d’appel de groupe requiert les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="bd73d-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="bd73d-110">service d’application</span><span class="sxs-lookup"><span data-stu-id="bd73d-110">Application service</span></span>

  - <span data-ttu-id="bd73d-111">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="bd73d-111">Call Park application</span></span>

<span data-ttu-id="bd73d-112">Ces composants sont installés automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="bd73d-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="bd73d-113">Droits d’utilisateur de configuration de prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="bd73d-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="bd73d-114">Vous utilisez les outils d’administration suivants pour configurer la prise d’appel de groupe :</span><span class="sxs-lookup"><span data-stu-id="bd73d-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="bd73d-115">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="bd73d-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="bd73d-116">Outil de kit de ressources SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="bd73d-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="bd73d-117">Utilisez Lync Server Management Shell pour créer et gérer des groupes de prise d’appel dans la table des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="bd73d-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="bd73d-118">Utilisez l’outil Kit de ressources SEFAUtil pour affecter un groupe de prise d’appel et activer la prise d’appel de groupe pour les utilisateurs ou pour désactiver la prise d’appel de groupe pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bd73d-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="bd73d-119">La configuration de la prise d’appel de groupe nécessite l’un des rôles d’administrateur suivants, en fonction de la tâche :</span><span class="sxs-lookup"><span data-stu-id="bd73d-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="bd73d-120">**CsVoiceAdministrator :** Ce rôle d’administrateur permet de créer, de configurer et de gérer toutes les stratégies et les paramètres liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="bd73d-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="bd73d-121">**CsUserAdministrator :** Ce rôle d’administrateur peut activer la prise d’appel de groupe pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bd73d-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="bd73d-122">Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.</span><span class="sxs-lookup"><span data-stu-id="bd73d-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="bd73d-123">**CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et dépanner les serveurs et les services.</span><span class="sxs-lookup"><span data-stu-id="bd73d-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="bd73d-124">**CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bd73d-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bd73d-125">Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="bd73d-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd73d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd73d-126">See Also</span></span>


[<span data-ttu-id="bd73d-127">Déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd73d-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="bd73d-128">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd73d-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

