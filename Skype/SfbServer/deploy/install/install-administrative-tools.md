---
title: Installer les outils d’administration dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Résumé : Découvrez comment installer les outils d’administration requis pour une installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018265"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="dd30a-104">Installer les outils d’administration dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dd30a-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="dd30a-105">**Résumé :** Découvrez comment installer les outils d’administration requis pour une installation de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dd30a-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="dd30a-106">Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft à l’adresse suivante :.</span><span class="sxs-lookup"><span data-stu-id="dd30a-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="dd30a-107">Les outils d’administration comprennent le générateur de topologie et le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="dd30a-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="dd30a-108">Les outils d’administration doivent être installés sur au moins un serveur de la topologie ou sur une station de travail de gestion 64 bits exécutant une version du système d’exploitation Windows prise en charge pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dd30a-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="dd30a-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="dd30a-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="dd30a-110">Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="dd30a-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="dd30a-111">L’installation des outils d’administration est l’étape 3 sur 8.</span><span class="sxs-lookup"><span data-stu-id="dd30a-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagramme de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="dd30a-113">Installer les outils d’administration de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dd30a-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="dd30a-114">Le support d’installation de Skype entreprise Server offre une expérience flexible.</span><span class="sxs-lookup"><span data-stu-id="dd30a-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="dd30a-115">Lorsque vous exécutez Setup. exe pour la première fois, les seuls outils installés sont l’Assistant Déploiement de Skype entreprise Server et Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dd30a-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="dd30a-116">À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalité principale pour l’environnement de Skype entreprise Server global.</span><span class="sxs-lookup"><span data-stu-id="dd30a-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="dd30a-117">L’Assistant déploiement est lancé automatiquement après l’installation des composants principaux.</span><span class="sxs-lookup"><span data-stu-id="dd30a-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="dd30a-118">La section de l’Assistant Déploiement intitulée **installer les outils d’administration** installe le générateur de topologie Skype entreprise Server et le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dd30a-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dd30a-119">Chaque environnement Skype entreprise Server doit disposer d’au moins un serveur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="dd30a-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="dd30a-120">Regardez les étapes vidéo pour **installer les outils d’administration**:</span><span class="sxs-lookup"><span data-stu-id="dd30a-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="dd30a-121">Installer les outils d’administration de Skype entreprise Server à partir de l’Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="dd30a-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="dd30a-122">Insérez le support d’installation de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dd30a-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="dd30a-123">Si le programme d’installation ne commence pas automatiquement, double-cliquez sur **configuration**.</span><span class="sxs-lookup"><span data-stu-id="dd30a-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="dd30a-124">Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="dd30a-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="dd30a-125">Une boîte de dialogue s’affiche et vous demande si vous souhaitez l’installer.</span><span class="sxs-lookup"><span data-stu-id="dd30a-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="dd30a-126">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="dd30a-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="dd30a-127">À l’aide de l’installation intelligente, une nouvelle fonctionnalité de Skype entreprise Server, vous pouvez vous connecter à Internet pour vérifier les mises à jour pendant le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="dd30a-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="dd30a-128">Cela permet une meilleure expérience en s’assurant que vous disposez des dernières mises à jour du produit lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="dd30a-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="dd30a-129">Cliquez sur **Installer** pour commencer l’installation.</span><span class="sxs-lookup"><span data-stu-id="dd30a-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="dd30a-130">Lisez attentivement le contrat de licence et, si vous l’acceptez, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd30a-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="dd30a-131">Les composants principaux de Skype entreprise Server seront installés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="dd30a-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="dd30a-132">Les composants principaux se composent des éléments suivants, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="dd30a-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Composants principaux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="dd30a-134">**Assistant Déploiement de Skype entreprise Server** Programme de déploiement qui fournit un pavé de lancement pour l’installation des différents composants de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dd30a-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="dd30a-135">**Skype entreprise Server Management Shell** Programme PowerShell préconfiguré qui permet l’administration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="dd30a-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="dd30a-136">Une fois l’installation des composants principaux terminée, l’Assistant Déploiement de Skype entreprise Server se lance automatiquement, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="dd30a-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Assistant Déploiement de Skype entreprise Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="dd30a-138">En plus des composants principaux, vous devrez également installer le générateur de topologie Skype entreprise Server et le panneau de configuration Skype entreprise Server sur au moins un serveur de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="dd30a-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="dd30a-139">Cliquez sur **installer les outils d’administration** dans l’Assistant déploiement.</span><span class="sxs-lookup"><span data-stu-id="dd30a-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="dd30a-140">Cliquez sur **Suivant** pour commencer l’installation.</span><span class="sxs-lookup"><span data-stu-id="dd30a-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="dd30a-141">Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="dd30a-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="dd30a-142">Les outils d’administration sont désormais ajoutés au serveur, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="dd30a-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Outils d’administration de Skype entreprise Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="dd30a-144">**Générateur de topologie Skype entreprise Server** Programme utilisé pour créer, déployer et gérer des topologies.</span><span class="sxs-lookup"><span data-stu-id="dd30a-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="dd30a-145">**Panneau de configuration de Skype entreprise Server** Programme utilisé pour administrer l’installation.</span><span class="sxs-lookup"><span data-stu-id="dd30a-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

