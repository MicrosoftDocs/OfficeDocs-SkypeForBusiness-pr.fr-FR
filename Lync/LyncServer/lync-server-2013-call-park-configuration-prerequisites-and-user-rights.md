---
title: 'Lync Server 2013 : conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel'
description: 'Lync Server 2013 : conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel.'
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
ms.openlocfilehash: b01187ad32fa7338765c0fa5b409b4e185e8ad35
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563530"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="577cf-103">Conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="577cf-103">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="577cf-104">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="577cf-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="577cf-105">Le parcage d’appel est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="577cf-105">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="577cf-106">Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer le parcage d’appel et les droits d’utilisateur dont vous avez besoin pour effectuer des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="577cf-106">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="577cf-107">Les fichiers de conservation de musique personnalisés pour l’application de parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence Lync Server 2013 et les fichiers sont perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="577cf-107">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="577cf-108">Conservez toujours une copie de sauvegarde distincte des fichiers de conservation musicaux personnalisés que vous avez téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="577cf-108">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="577cf-109">Cette section suppose que vous avez lu la documentation de planification relative au parcage d’appel (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="577cf-109">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="577cf-110">Conditions préalables à la configuration du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="577cf-110">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="577cf-111">Le parcage d’appel requiert les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="577cf-111">Call Park requires the following components:</span></span>

  - <span data-ttu-id="577cf-112">service d’application</span><span class="sxs-lookup"><span data-stu-id="577cf-112">Application service</span></span>

  - <span data-ttu-id="577cf-113">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="577cf-113">Call Park application</span></span>

<span data-ttu-id="577cf-114">Ces composants sont installés automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="577cf-114">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="577cf-115">Si vous voulez que les appelants entendent de la musique lors du parcage des appels, un fichier d’attente musicale est également requis.</span><span class="sxs-lookup"><span data-stu-id="577cf-115">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="577cf-116">Un fichier d’attente musicale par défaut est installé automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="577cf-116">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="577cf-117">Vous pouvez le remplacer par un fichier d’attente musicale de votre choix.</span><span class="sxs-lookup"><span data-stu-id="577cf-117">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="577cf-118">Le parcage d’appel utilise le magasin de fichiers pour stocker le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="577cf-118">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="577cf-119">Droits d’utilisateur pour la configuration du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="577cf-119">Call Park Configuration User Rights</span></span>

<span data-ttu-id="577cf-120">Vous pouvez utiliser les outils d’administration suivants pour configurer le parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="577cf-120">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="577cf-121">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="577cf-121">Lync Server Control Panel</span></span>

  - <span data-ttu-id="577cf-122">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="577cf-122">Lync Server Management Shell</span></span>

<span data-ttu-id="577cf-123">Ces outils vous permettent de configurer la table d’orbites de parcage d’appel et de configurer les autres paramètres utilisés par le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="577cf-123">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="577cf-124">La configuration du parcage d’appel nécessite l’un des rôles d’administrateur suivants, en fonction de la tâche :</span><span class="sxs-lookup"><span data-stu-id="577cf-124">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="577cf-125">**CsVoiceAdministrator :** Ce rôle d’administrateur permet de créer, de configurer et de gérer toutes les stratégies et les paramètres liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="577cf-125">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="577cf-126">**CsUserAdministrator :** Ce rôle d’administrateur peut activer le parcage d’appel dans la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="577cf-126">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="577cf-127">Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.</span><span class="sxs-lookup"><span data-stu-id="577cf-127">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="577cf-128">**CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et dépanner les serveurs et les services.</span><span class="sxs-lookup"><span data-stu-id="577cf-128">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="577cf-129">**CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="577cf-129">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="577cf-130">Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="577cf-130">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="577cf-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="577cf-131">See Also</span></span>


[<span data-ttu-id="577cf-132">Déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="577cf-132">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="577cf-133">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="577cf-133">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

