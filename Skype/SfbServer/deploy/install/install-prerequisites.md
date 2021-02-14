---
title: Installer les conditions préalables pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : Découvrez les serveurs et les rôles serveur que vous devez configurer avant d’installer Skype Entreprise Server. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801714"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="092ac-104">Installer les conditions préalables pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="092ac-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="092ac-105">**Résumé :** Découvrez les serveurs et les rôles serveur que vous devez configurer avant d’installer Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="092ac-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="092ac-106">Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du [Centre d’évaluation Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="092ac-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="092ac-107">L’installation des éléments prérequis consiste à installer Windows Server en installant les rôles et fonctionnalités requis sur chacun des serveurs de la topologie.</span><span class="sxs-lookup"><span data-stu-id="092ac-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="092ac-108">Les exigences sont basées sur le rôle que le serveur remplira dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="092ac-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="092ac-109">Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="092ac-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="092ac-110">Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="092ac-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="092ac-111">L’installation des prérequis est l’étape 1 sur 8.</span><span class="sxs-lookup"><span data-stu-id="092ac-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagramme de vue d’ensemble : conditions préalables à l’installation.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="092ac-113">Configurer Windows Server</span><span class="sxs-lookup"><span data-stu-id="092ac-113">Setup Windows Server</span></span>

<span data-ttu-id="092ac-114">Skype Entreprise Server nécessite le système d’exploitation Windows Server et un certain nombre de conditions préalables avant de pouvoir être installé.</span><span class="sxs-lookup"><span data-stu-id="092ac-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="092ac-115">Pour plus d’informations sur la planification des conditions préalables, consultez la liste des conditions requises pour [le serveur pour Skype Entreprise Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="092ac-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="092ac-116">Cette procédure utilise Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="092ac-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="092ac-117">Si vous utilisez une version différente de Windows Server, la procédure peut être légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="092ac-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="092ac-118">Avant de commencer, assurez-vous que Windows Server est à jour à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="092ac-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="092ac-120">Regardez les étapes de la vidéo pour **les conditions préalables à l’installation**:</span><span class="sxs-lookup"><span data-stu-id="092ac-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="092ac-121">Installer les rôles et fonctionnalités requis pour les serveurs frontux</span><span class="sxs-lookup"><span data-stu-id="092ac-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="092ac-122">Vous pouvez installer les rôles et fonctionnalités requis à l’aide du Gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="092ac-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="092ac-123">Installez les fonctionnalités logicielles prérequises répertoriées dans la liste des conditions [requises pour le serveur pour Skype Entreprise Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="092ac-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="092ac-124">Le logiciel requis doit se trouver sur le serveur qui exécutera Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="092ac-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="092ac-125">Windows Server 2012 R2 n’installe pas tous les fichiers sources pour les fonctionnalités requises par défaut.</span><span class="sxs-lookup"><span data-stu-id="092ac-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="092ac-126">Si le serveur n’est pas connecté à Internet, vous devez insérer le support Windows Server 2012 R2 et sélectionner Spécifier un autre chemin **d’accès source** pour installer les fonctionnalités requises.</span><span class="sxs-lookup"><span data-stu-id="092ac-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="092ac-127">Les fichiers sources se trouvent dans le répertoire sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="092ac-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="092ac-128">Par exemple, si le support Windows Server 2012 R2 se trouve dans le lecteur D, vous devez définir le chemin d’accès sur `d:\sources\sxs` .</span><span class="sxs-lookup"><span data-stu-id="092ac-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="092ac-129">Il est important que vous avez les dernières mises à jour de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="092ac-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="092ac-130">Si vous n’êtes pas connecté à Internet, vous devrez installer manuellement toutes les mises à jour pertinentes, ainsi que les conditions préalables aux mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="092ac-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="092ac-131">Lorsque la boîte de dialogue indique que l’installation est terminée, vous devez redémarrer le serveur pour terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="092ac-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="092ac-132">Exécutez **à nouveau Windows Update** pour vérifier s’il existe des mises à jour des rôles et services qui ont été installés.</span><span class="sxs-lookup"><span data-stu-id="092ac-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="092ac-133">Si vous utilisez le Panneau de contrôle Skype Entreprise Server sur ce serveur, vous devez également installer Silverlight.</span><span class="sxs-lookup"><span data-stu-id="092ac-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="092ac-134">Pour installer Silverlight, voir [Microsoft Silverlight.](https://www.microsoft.com/silverlight/)</span><span class="sxs-lookup"><span data-stu-id="092ac-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="092ac-135">Les conditions préalables pour les serveurs qui jouent des rôles autres que les serveurs frontaux, tels que le rôle de directeur, de conversation permanente ou de serveur Edge, ont leurs propres conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="092ac-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="092ac-136">Pour plus d’informations sur les conditions préalables exactes requises par chaque type de serveur, voir [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="092ac-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

