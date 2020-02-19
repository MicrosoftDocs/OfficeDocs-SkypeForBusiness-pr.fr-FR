---
title: 'Lync Server 2013 : conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39fd811a39a1221ec522c7ca3874d0de4f340b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="85e69-102">Conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85e69-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85e69-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="85e69-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="85e69-104">Le parcage d’appel est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="85e69-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="85e69-105">Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer le parcage d’appel et les droits d’utilisateur dont vous avez besoin pour effectuer des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="85e69-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85e69-106">Les fichiers de conservation de musique personnalisés pour l’application de parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence Lync Server 2013 et les fichiers sont perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="85e69-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="85e69-107">Conservez toujours une copie de sauvegarde distincte des fichiers de conservation musicaux personnalisés que vous avez téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="85e69-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="85e69-108">Cette section suppose que vous avez lu la documentation de planification relative au parcage d’appel (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="85e69-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="85e69-109">Conditions préalables à la configuration du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="85e69-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="85e69-110">Le parcage d’appel requiert les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="85e69-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="85e69-111">service d’application</span><span class="sxs-lookup"><span data-stu-id="85e69-111">Application service</span></span>

  - <span data-ttu-id="85e69-112">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="85e69-112">Call Park application</span></span>

<span data-ttu-id="85e69-113">Ces composants sont installés automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="85e69-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="85e69-114">Si vous voulez que les appelants entendent de la musique lors du parcage des appels, un fichier d’attente musicale est également requis.</span><span class="sxs-lookup"><span data-stu-id="85e69-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="85e69-115">Un fichier d’attente musicale par défaut est installé automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="85e69-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="85e69-116">Vous pouvez le remplacer par un fichier d’attente musicale de votre choix.</span><span class="sxs-lookup"><span data-stu-id="85e69-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="85e69-117">Le parcage d’appel utilise le magasin de fichiers pour stocker le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="85e69-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="85e69-118">Droits d’utilisateur pour la configuration du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="85e69-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="85e69-119">Vous pouvez utiliser les outils d’administration suivants pour configurer le parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="85e69-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="85e69-120">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="85e69-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="85e69-121">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="85e69-121">Lync Server Management Shell</span></span>

<span data-ttu-id="85e69-122">Ces outils vous permettent de configurer la table d’orbites de parcage d’appel et de configurer les autres paramètres utilisés par le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="85e69-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="85e69-123">La configuration du parcage d’appel nécessite l’un des rôles d’administrateur suivants, en fonction de la tâche :</span><span class="sxs-lookup"><span data-stu-id="85e69-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="85e69-124">**CsVoiceAdministrator :** Ce rôle d’administrateur permet de créer, de configurer et de gérer toutes les stratégies et les paramètres liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="85e69-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="85e69-125">**CsUserAdministrator :** Ce rôle d’administrateur peut activer le parcage d’appel dans la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="85e69-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="85e69-126">Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.</span><span class="sxs-lookup"><span data-stu-id="85e69-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="85e69-127">**CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et dépanner les serveurs et les services.</span><span class="sxs-lookup"><span data-stu-id="85e69-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="85e69-128">**CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="85e69-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85e69-129">Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="85e69-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85e69-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85e69-130">See Also</span></span>


[<span data-ttu-id="85e69-131">Déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85e69-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="85e69-132">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85e69-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

