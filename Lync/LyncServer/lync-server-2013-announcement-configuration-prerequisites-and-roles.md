---
title: 'Lync Server 2013 : conditions préalables et rôles de configuration d’annonce'
description: 'Lync Server 2013 : conditions préalables et rôles de configuration d’annonce.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561890"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="673d5-103">Conditions préalables et rôles de configuration d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="673d5-103">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="673d5-104">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="673d5-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="673d5-105">Annonce est une fonctionnalité de gestion des appels voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="673d5-105">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="673d5-106">Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer une annonce et les attributions de rôles dont vous avez besoin pour effectuer des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="673d5-106">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="673d5-107">Cette section suppose que vous avez lu la documentation de planification relative à annonce (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="673d5-107">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="673d5-108">Conditions préalables de configuration d’annonce</span><span class="sxs-lookup"><span data-stu-id="673d5-108">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="673d5-109">L’application d’annonce requiert les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="673d5-109">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="673d5-110">Service d’application</span><span class="sxs-lookup"><span data-stu-id="673d5-110">Application service</span></span>

  - <span data-ttu-id="673d5-111">Application Response Group</span><span class="sxs-lookup"><span data-stu-id="673d5-111">Response Group application</span></span>

  - <span data-ttu-id="673d5-112">Magasin de fichiers, pour conserver les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="673d5-112">File Store, to hold audio files</span></span>

<span data-ttu-id="673d5-113">Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="673d5-113">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="673d5-114">Rôles de configuration d’annonce</span><span class="sxs-lookup"><span data-stu-id="673d5-114">Announcement Configuration Roles</span></span>

<span data-ttu-id="673d5-115">Vous pouvez utiliser les outils administratifs suivants pour configurer les annonces :</span><span class="sxs-lookup"><span data-stu-id="673d5-115">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="673d5-116">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="673d5-116">Lync Server Control Panel</span></span>

  - <span data-ttu-id="673d5-117">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="673d5-117">Lync Server Management Shell</span></span>

<span data-ttu-id="673d5-118">La configuration de l’application d’annonce nécessite l’un des rôles d’administrateur suivants :</span><span class="sxs-lookup"><span data-stu-id="673d5-118">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="673d5-119">**CsVoiceAdministrator**     Ce rôle d’administrateur peut créer, configurer et gérer toutes les stratégies et les paramètres vocaux, y compris les paramètres d’annonce.</span><span class="sxs-lookup"><span data-stu-id="673d5-119">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="673d5-120">**CsServerAdministrator**     Ce rôle d’administrateur permet de gérer, surveiller et dépanner les serveurs et les services, et de configurer tous les paramètres d’annonce.</span><span class="sxs-lookup"><span data-stu-id="673d5-120">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="673d5-121">**CsAdministrator**     Ce rôle d’administrateur peut effectuer toutes les tâches administratives et modifier tous les paramètres.</span><span class="sxs-lookup"><span data-stu-id="673d5-121">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="673d5-122">**CsViewOnlyAdministrator**     Ce rôle d’administrateur peut afficher le déploiement pour surveiller l’intégrité du déploiement.</span><span class="sxs-lookup"><span data-stu-id="673d5-122">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="673d5-123">Pour plus d’informations sur les droits d’administrateur, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="673d5-123">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="673d5-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="673d5-124">See Also</span></span>


[<span data-ttu-id="673d5-125">Déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="673d5-125">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="673d5-126">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="673d5-126">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

