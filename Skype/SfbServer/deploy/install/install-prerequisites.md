---
title: Installer les éléments prérequis pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Résumé : En savoir plus sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 11a4d4240415dc11ce42ceb8f9643b52c91c9e2c
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297633"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="c63de-104">Installer les éléments prérequis pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c63de-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="c63de-105">**Résumé :** Obtenir des informations sur les serveurs et les rôles de serveur que vous devez configurer avant d’installer Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="c63de-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="c63de-106">Téléchargez une version d’évaluation gratuite de Skype pour Business Server à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="c63de-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="c63de-107">L’installation des conditions préalables consiste à mettre en place Windows Server en installant les fonctionnalités et rôles requis pour chaque serveur de la topologie.</span><span class="sxs-lookup"><span data-stu-id="c63de-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="c63de-108">Les conditions sont basées sur le rôle que le serveur va jouer dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="c63de-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="c63de-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="c63de-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="c63de-110">Cependant, vous devez suivre les étapes 6, 7, et 8 dans l’ordre et après avoir effectué les étapes 1 à 5, comme expliqué sur le diagramme.</span><span class="sxs-lookup"><span data-stu-id="c63de-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="c63de-111">L’installation des conditions préalables est présentée dans l’étape 1 sur 8.</span><span class="sxs-lookup"><span data-stu-id="c63de-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Schéma de vue d’ensemble - Composants prérequis pour l’installation.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="c63de-113">Mise en place de Windows Server</span><span class="sxs-lookup"><span data-stu-id="c63de-113">Setup Windows Server</span></span>

<span data-ttu-id="c63de-114">Skype pour Business Server requiert le système d’exploitation Windows Server et un certain nombre de conditions préalables avant de pouvoir installer.</span><span class="sxs-lookup"><span data-stu-id="c63de-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="c63de-115">Pour plus d’informations sur la planification des conditions préalables, voir [configuration du serveur pour Skype pour Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c63de-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="c63de-116">Cette procédure se base sur Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="c63de-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="c63de-117">Si vous utilisez une version différente de Windows Server, la procédure peut être légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="c63de-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c63de-118">Avant de commencer, assurez-vous que Windows Server est mise à jour à l’aide de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c63de-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server à jour.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="c63de-120">Regardez la vidéo des étapes pour **installer les composants requis** :</span><span class="sxs-lookup"><span data-stu-id="c63de-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="c63de-121">Installez les fonctionnalités et rôles requis pour les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="c63de-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="c63de-122">Vous pouvez installer les rôles requis et les fonctionnalités à l’aide du Gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="c63de-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="c63de-123">Installer les fonctionnalités de logiciels répertoriées dans la [configuration serveur requise pour Skype pour Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c63de-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="c63de-124">Les logiciels requis doivent se trouver sur le serveur qui exécutera Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="c63de-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="c63de-125">Windows Server 2012 R2 n’installe pas tous les fichiers source pour les fonctionnalités requises par défaut.</span><span class="sxs-lookup"><span data-stu-id="c63de-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="c63de-126">Si le serveur n’est pas connecté à internet, vous devrez installer le média Windows Server 2012 R2 et sélectionner **Spécifier un autre chemin d’accès source** afin d’installer les fonctionnalités requises.</span><span class="sxs-lookup"><span data-stu-id="c63de-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="c63de-127">Les fichiers source se trouvent dans le répertoire sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="c63de-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="c63de-128">Par exemple, si le média Windows Server 2012 R2 se trouve dans le lecteur D, sélectionnez le chemin d’accès vers `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="c63de-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="c63de-129">Il est important que vous ayez les dernières mises à jour de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c63de-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="c63de-130">Si vous n’êtes pas connecté à internet, vous devrez installer manuellement toutes les mises à jour appropriées et toutes les conditions préalables pour les mises à jour requises.</span><span class="sxs-lookup"><span data-stu-id="c63de-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="c63de-131">Lorsque la boîte de dialogue indiquera que l’installation a bien été effectuée, vous devrez redémarrer le serveur pour terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="c63de-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="c63de-132">Réexécutez **Windows Update** pour vérifier les mises à jour pour les rôles et services qui ont été installés.</span><span class="sxs-lookup"><span data-stu-id="c63de-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="c63de-133">Si vous utilisez Skype pour le panneau de configuration serveur Business sur ce serveur vous devez également installer Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c63de-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="c63de-134">Pour installer Silverlight, reportez-vous à [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="c63de-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c63de-135">Les conditions préalables pour les serveurs ayant d’autres rôles que celui de serveur frontal (notamment les rôles de directeur, de conversation permanente, ou Edge) ont leurs propres conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="c63de-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="c63de-136">Pour plus d’informations sur la configuration exacte requise par chaque type de serveur, voir [configuration du serveur pour Skype pour Business Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c63de-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

