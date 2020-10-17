---
title: 'Lync Server 2013 : conditions préalables et rôles de configuration d’annonce'
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
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531691"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="1237e-102">Conditions préalables et rôles de configuration d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1237e-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1237e-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="1237e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="1237e-104">Annonce est une fonctionnalité de gestion des appels voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="1237e-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="1237e-105">Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer une annonce et les attributions de rôles dont vous avez besoin pour effectuer des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="1237e-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="1237e-106">Cette section suppose que vous avez lu la documentation de planification relative à annonce (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="1237e-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="1237e-107">Conditions préalables de configuration d’annonce</span><span class="sxs-lookup"><span data-stu-id="1237e-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="1237e-108">L’application d’annonce requiert les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="1237e-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="1237e-109">Service d’application</span><span class="sxs-lookup"><span data-stu-id="1237e-109">Application service</span></span>

  - <span data-ttu-id="1237e-110">Application Response Group</span><span class="sxs-lookup"><span data-stu-id="1237e-110">Response Group application</span></span>

  - <span data-ttu-id="1237e-111">Magasin de fichiers, pour conserver les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="1237e-111">File Store, to hold audio files</span></span>

<span data-ttu-id="1237e-112">Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1237e-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="1237e-113">Rôles de configuration d’annonce</span><span class="sxs-lookup"><span data-stu-id="1237e-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="1237e-114">Vous pouvez utiliser les outils administratifs suivants pour configurer les annonces :</span><span class="sxs-lookup"><span data-stu-id="1237e-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="1237e-115">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="1237e-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="1237e-116">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1237e-116">Lync Server Management Shell</span></span>

<span data-ttu-id="1237e-117">La configuration de l’application d’annonce nécessite l’un des rôles d’administrateur suivants :</span><span class="sxs-lookup"><span data-stu-id="1237e-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="1237e-118">**CsVoiceAdministrator**     Ce rôle d’administrateur peut créer, configurer et gérer toutes les stratégies et les paramètres vocaux, y compris les paramètres d’annonce.</span><span class="sxs-lookup"><span data-stu-id="1237e-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="1237e-119">**CsServerAdministrator**     Ce rôle d’administrateur permet de gérer, surveiller et dépanner les serveurs et les services, et de configurer tous les paramètres d’annonce.</span><span class="sxs-lookup"><span data-stu-id="1237e-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="1237e-120">**CsAdministrator**     Ce rôle d’administrateur peut effectuer toutes les tâches administratives et modifier tous les paramètres.</span><span class="sxs-lookup"><span data-stu-id="1237e-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="1237e-121">**CsViewOnlyAdministrator**     Ce rôle d’administrateur peut afficher le déploiement pour surveiller l’intégrité du déploiement.</span><span class="sxs-lookup"><span data-stu-id="1237e-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1237e-122">Pour plus d’informations sur les droits d’administrateur, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1237e-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1237e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1237e-123">See Also</span></span>


[<span data-ttu-id="1237e-124">Déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1237e-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="1237e-125">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1237e-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

