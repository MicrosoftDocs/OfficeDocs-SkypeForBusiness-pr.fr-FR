---
title: Conditions préalables et droits d’utilisateur pour la configuration des appels de groupe
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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="ac716-102">Configuration requise pour les appels de groupe et droits d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac716-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac716-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ac716-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ac716-104">La cueillette de groupe est une fonctionnalité de gestion des appels qui est installée par défaut lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ac716-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ac716-105">Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer la collecte d’appels de groupe et les droits d’utilisateur nécessaires à l’exécution des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="ac716-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="ac716-106">Cette section part du principe que vous avez lu la documentation de planification liée au regroupement d’appels de groupe (voir [planification d’appels de groupe dans Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="ac716-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="ac716-107">Configuration requise pour la configuration des appels de groupe</span><span class="sxs-lookup"><span data-stu-id="ac716-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="ac716-108">La collecte des appels de groupe nécessite les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="ac716-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="ac716-109">service d’application</span><span class="sxs-lookup"><span data-stu-id="ac716-109">Application service</span></span>

  - <span data-ttu-id="ac716-110">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="ac716-110">Call Park application</span></span>

<span data-ttu-id="ac716-111">Ces composants sont installés automatiquement lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ac716-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="ac716-112">Droits d’utilisateur de configuration des appels de groupe</span><span class="sxs-lookup"><span data-stu-id="ac716-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="ac716-113">Vous pouvez utiliser les outils d’administration suivants pour configurer la cueillette des appels de groupe :</span><span class="sxs-lookup"><span data-stu-id="ac716-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="ac716-114">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ac716-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="ac716-115">Outil du kit de ressources SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="ac716-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="ac716-116">Utilisez Lync Server Management Shell pour créer et gérer des groupes de captures d’appels dans la table de stationnement d’appel.</span><span class="sxs-lookup"><span data-stu-id="ac716-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="ac716-117">Utilisez l’outil de kit de ressources SEFAUtil pour attribuer un groupe de cueillette d’appel et activer le regroupement d’appels de groupe pour les utilisateurs ou pour désactiver la sélection d’appels de groupe pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac716-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="ac716-118">La configuration de la cueillette de groupe nécessite l’un des rôles d’administration suivants, en fonction de la tâche :</span><span class="sxs-lookup"><span data-stu-id="ac716-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="ac716-119">**CsVoiceAdministrator :** Ce rôle d’administrateur peut créer, configurer et gérer l’ensemble des stratégies et paramètres relatifs à la voix.</span><span class="sxs-lookup"><span data-stu-id="ac716-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="ac716-120">**CsUserAdministrator :** Ce rôle d’administrateur peut activer le prélèvement d’appels de groupe pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac716-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="ac716-121">Ce rôle d’administrateur dispose également d’un accès en lecture seule à toutes les configurations vocales.</span><span class="sxs-lookup"><span data-stu-id="ac716-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="ac716-122">**CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et résoudre les problèmes liés aux serveurs et services.</span><span class="sxs-lookup"><span data-stu-id="ac716-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="ac716-123">**CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ac716-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ac716-124">Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ac716-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac716-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac716-125">See Also</span></span>


[<span data-ttu-id="ac716-126">Déploiement d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac716-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="ac716-127">Planifier les fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac716-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

