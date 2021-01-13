---
title: Installer les outils d’administration dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Découvrez comment installer les outils d’administration requis pour une installation de Skype Entreprise Server. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812104"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="ccb59-104">Installer les outils d’administration dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ccb59-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="ccb59-105">**Résumé :** Découvrez comment installer les outils d’administration requis pour une installation de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ccb59-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="ccb59-106">Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="ccb59-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ccb59-107">Les outils d’administration incluent le Générateur de topologie et le Panneau de contrôle.</span><span class="sxs-lookup"><span data-stu-id="ccb59-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="ccb59-108">Les outils d’administration doivent être installés sur au moins un serveur de la topologie ou sur une station de travail de gestion 64 bits exécutant une version du système d’exploitation Windows prise en charge pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ccb59-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="ccb59-109">Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="ccb59-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ccb59-110">Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="ccb59-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="ccb59-111">L’installation des outils d’administration est l’étape 3 sur 8.</span><span class="sxs-lookup"><span data-stu-id="ccb59-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagramme de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="ccb59-113">Installer les outils d’administration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ccb59-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="ccb59-114">Le support d’installation de Skype Entreprise Server offre une expérience flexible.</span><span class="sxs-lookup"><span data-stu-id="ccb59-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="ccb59-115">Lorsque vous exécutez Setup.exe, les seuls outils installés sont l’Assistant Déploiement de Skype Entreprise Server et Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ccb59-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ccb59-116">À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalités principales pour l’environnement Skype Entreprise Server global.</span><span class="sxs-lookup"><span data-stu-id="ccb59-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="ccb59-117">L’Assistant Déploiement se lance automatiquement après l’installation des composants principaux.</span><span class="sxs-lookup"><span data-stu-id="ccb59-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="ccb59-118">La section de l’Assistant Déploiement intitulée **Installer** les outils d’administration installe le Générateur de topologie Skype Entreprise Server et le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ccb59-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ccb59-119">Chaque environnement Skype Entreprise Server doit avoir au moins un serveur avec les outils d’administration installés.</span><span class="sxs-lookup"><span data-stu-id="ccb59-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="ccb59-120">Regardez les étapes vidéo pour **installer les outils d’administration**:</span><span class="sxs-lookup"><span data-stu-id="ccb59-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="ccb59-121">Installer les outils d’administration Skype Entreprise Server à partir de l’Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="ccb59-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="ccb59-122">Insérez le support d’installation de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ccb59-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="ccb59-123">Si le programme d’installation ne démarre pas automatiquement, double-cliquez sur **Installation.**</span><span class="sxs-lookup"><span data-stu-id="ccb59-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="ccb59-124">Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="ccb59-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="ccb59-125">Une boîte de dialogue apparaît pour vous demander si vous souhaitez l’installer.</span><span class="sxs-lookup"><span data-stu-id="ccb59-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="ccb59-126">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ccb59-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="ccb59-127">À l’aide de Smart Setup, une nouvelle fonctionnalité de Skype Entreprise Server, vous pouvez vous connecter à Internet pour vérifier les mises à jour au cours du processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="ccb59-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="ccb59-128">Cela permet d’améliorer l’expérience en vous assurez que vous disposez des mises à jour les plus récentes du produit lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="ccb59-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="ccb59-129">Cliquez sur **Installer** pour commencer l’installation.</span><span class="sxs-lookup"><span data-stu-id="ccb59-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="ccb59-130">Examinez attentivement le contrat de licence et, si vous acceptez, sélectionnez **J’accepte** les termes du contrat de licence, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccb59-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="ccb59-131">Les composants principaux de Skype Entreprise Server seront installés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ccb59-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="ccb59-132">Les composants principaux sont constitués des éléments suivants, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="ccb59-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Écran Composants principaux dans les applications.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="ccb59-134">**Assistant Déploiement de Skype Entreprise Server** Programme de déploiement qui fournit un pavé de lancement pour l’installation des différents composants de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ccb59-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="ccb59-135">**Skype Entreprise Server Management Shell** Programme PowerShell préconfiguré qui permet l’administration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ccb59-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="ccb59-136">Une fois l’installation des composants principaux terminée, l’Assistant Déploiement de Skype Entreprise Server se lance automatiquement, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="ccb59-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Assistant Déploiement de Skype Entreprise Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="ccb59-138">Outre les composants principaux, vous devez également installer le Générateur de topologie Skype Entreprise Server et le Panneau de contrôle Skype Entreprise Server sur au moins un serveur de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="ccb59-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="ccb59-139">Cliquez **sur Installer les outils d’administration** dans l’Assistant Déploiement.</span><span class="sxs-lookup"><span data-stu-id="ccb59-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="ccb59-140">Cliquez sur **Suivant** pour commencer l’installation.</span><span class="sxs-lookup"><span data-stu-id="ccb59-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="ccb59-141">Une fois l’installation terminée, cliquez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="ccb59-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="ccb59-142">Les outils d’administration sont désormais ajoutés au serveur, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="ccb59-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Outils d’administration Skype Entreprise Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="ccb59-144">**Générateur de topologie Skype** Entreprise Server Programme utilisé pour créer, déployer et gérer des topologies.</span><span class="sxs-lookup"><span data-stu-id="ccb59-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="ccb59-145">**Panneau de contrôle Skype Entreprise Server** Programme utilisé pour administrer l’installation.</span><span class="sxs-lookup"><span data-stu-id="ccb59-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

