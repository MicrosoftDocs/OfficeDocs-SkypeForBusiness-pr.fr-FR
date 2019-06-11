---
title: 'Lync Server 2013 : Conditions prérequises et rôles de configuration d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5f909170e1de2566e21e9305175211c306fee6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="02a5b-102">Conditions prérequises et rôles de configuration d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a5b-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02a5b-103">_**Dernière modification de la rubrique:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="02a5b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="02a5b-104">Annonce est une fonction de gestion des appels voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="02a5b-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="02a5b-105">Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer l’annonce et les affectations de rôles nécessaires à l’exécution de tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="02a5b-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="02a5b-106">Cette section suppose que vous avez lu la documentation de planification liée à l’annonce (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="02a5b-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="02a5b-107">Conditions préalables à la configuration de l’annonce</span><span class="sxs-lookup"><span data-stu-id="02a5b-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="02a5b-108">L’application d’annonce nécessite les composants suivants:</span><span class="sxs-lookup"><span data-stu-id="02a5b-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="02a5b-109">service d’application</span><span class="sxs-lookup"><span data-stu-id="02a5b-109">Application service</span></span>

  - <span data-ttu-id="02a5b-110">application Response Group</span><span class="sxs-lookup"><span data-stu-id="02a5b-110">Response Group application</span></span>

  - <span data-ttu-id="02a5b-111">Magasin de fichiers, pour contenir des fichiers audio</span><span class="sxs-lookup"><span data-stu-id="02a5b-111">File Store, to hold audio files</span></span>

<span data-ttu-id="02a5b-112">Tous ces composants sont installés par défaut lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="02a5b-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="02a5b-113">Rôles de configuration d’annonce</span><span class="sxs-lookup"><span data-stu-id="02a5b-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="02a5b-114">Pour configurer des annonces, vous pouvez utiliser les outils d’administration suivants:</span><span class="sxs-lookup"><span data-stu-id="02a5b-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="02a5b-115">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="02a5b-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="02a5b-116">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="02a5b-116">Lync Server Management Shell</span></span>

<span data-ttu-id="02a5b-117">La configuration de l’application d’annonce nécessite l’un des rôles d’administration suivants:</span><span class="sxs-lookup"><span data-stu-id="02a5b-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="02a5b-118">**CsVoiceAdministrator**   ce rôle d’administrateur peut créer, configurer et gérer toutes les stratégies et paramètres relatifs à la voix, y compris les paramètres d’annonce.</span><span class="sxs-lookup"><span data-stu-id="02a5b-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="02a5b-119">**CsServerAdministrator**   ce rôle d’administrateur peut gérer, surveiller et résoudre les problèmes liés aux serveurs et aux services, et configurer tous les paramètres d’annonce.</span><span class="sxs-lookup"><span data-stu-id="02a5b-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="02a5b-120">**CsAdministrator**   ce rôle d’administrateur peut effectuer toutes les tâches administratives et modifier tous les paramètres.</span><span class="sxs-lookup"><span data-stu-id="02a5b-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="02a5b-121">**CsViewOnlyAdministrator**   ce rôle d’administrateur peut voir le déploiement pour contrôler l’intégrité du déploiement.</span><span class="sxs-lookup"><span data-stu-id="02a5b-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02a5b-122">Pour plus d’informations sur les privilèges des utilisateurs d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="02a5b-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02a5b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02a5b-123">See Also</span></span>


[<span data-ttu-id="02a5b-124">Déploiement d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a5b-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="02a5b-125">Planifier les fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a5b-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

