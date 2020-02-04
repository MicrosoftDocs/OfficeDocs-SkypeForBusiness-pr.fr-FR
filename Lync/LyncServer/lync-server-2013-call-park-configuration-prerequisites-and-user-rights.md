---
title: 'Lync Server 2013 : Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur'
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
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="bbdad-102">Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbdad-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbdad-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="bbdad-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="bbdad-104">Le parc d’appels est une fonctionnalité de gestion des appels qui est installée par défaut lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bbdad-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bbdad-105">Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer le parc d’appels et les droits d’utilisateur nécessaires à l’exécution des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="bbdad-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bbdad-106">Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels ne sont pas sauvegardés dans le cadre du processus de reprise après sinistre de Lync Server 2013 et les fichiers sont perdus si les fichiers téléchargés sur le pool sont endommagés, endommagés ou supprimés.</span><span class="sxs-lookup"><span data-stu-id="bbdad-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="bbdad-107">Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="bbdad-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="bbdad-108">Cette section part du principe que vous avez lu la documentation de planification liée au parc d’appels (pour plus d’informations, reportez-vous à la [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="bbdad-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="bbdad-109">Conditions préalables à la configuration du parc d’appels</span><span class="sxs-lookup"><span data-stu-id="bbdad-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="bbdad-110">Le parc d’appels nécessite les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="bbdad-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="bbdad-111">service d’application</span><span class="sxs-lookup"><span data-stu-id="bbdad-111">Application service</span></span>

  - <span data-ttu-id="bbdad-112">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="bbdad-112">Call Park application</span></span>

<span data-ttu-id="bbdad-113">Ces composants sont installés automatiquement lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bbdad-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="bbdad-114">Si vous voulez que les appelants entendent de la musique pendant le stationnement de l’appel, un fichier en attente de musique est également requis.</span><span class="sxs-lookup"><span data-stu-id="bbdad-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="bbdad-115">Un fichier de Music-Holding par défaut est installé automatiquement lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bbdad-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bbdad-116">Vous pouvez remplacer le fichier par défaut par votre propre fichier audio.</span><span class="sxs-lookup"><span data-stu-id="bbdad-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="bbdad-117">Le parc d’appels utilise le magasin de fichiers pour contenir le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="bbdad-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="bbdad-118">Configuration du parc d’appels-droits d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="bbdad-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="bbdad-119">Pour configurer le parc d’appels, vous pouvez utiliser les outils d’administration suivants :</span><span class="sxs-lookup"><span data-stu-id="bbdad-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="bbdad-120">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="bbdad-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="bbdad-121">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="bbdad-121">Lync Server Management Shell</span></span>

<span data-ttu-id="bbdad-122">Ces outils vous permettent de configurer la table de stationnement d’appel et de configurer d’autres paramètres utilisés par le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="bbdad-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="bbdad-123">La configuration du parc d’appels nécessite l’un des rôles d’administration suivants, en fonction de la tâche :</span><span class="sxs-lookup"><span data-stu-id="bbdad-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="bbdad-124">**CsVoiceAdministrator :** Ce rôle d’administrateur peut créer, configurer et gérer l’ensemble des stratégies et paramètres relatifs à la voix.</span><span class="sxs-lookup"><span data-stu-id="bbdad-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="bbdad-125">**CsUserAdministrator :** Ce rôle d’administrateur peut activer le parc d’appels dans la politique vocale.</span><span class="sxs-lookup"><span data-stu-id="bbdad-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="bbdad-126">Ce rôle d’administrateur dispose également d’un accès en lecture seule à toutes les configurations vocales.</span><span class="sxs-lookup"><span data-stu-id="bbdad-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="bbdad-127">**CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et résoudre les problèmes liés aux serveurs et services.</span><span class="sxs-lookup"><span data-stu-id="bbdad-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="bbdad-128">**CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bbdad-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bbdad-129">Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="bbdad-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bbdad-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbdad-130">See Also</span></span>


[<span data-ttu-id="bbdad-131">Déploiement d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbdad-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="bbdad-132">Planifier les fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbdad-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

