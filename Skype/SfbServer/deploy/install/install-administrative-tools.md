---
title: Installer les outils d’administration dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Découvrez comment installer les outils d’administration requis pour une installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: cb5e1766ca4e0b7d6ad03db2004835e1a51d52cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891830"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="ae137-104">Installer les outils d’administration dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="ae137-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="ae137-105">**Résumé :** Découvrez comment installer les outils d’administration requis pour une installation de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae137-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="ae137-106">Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="ae137-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ae137-107">Parmi les outils d’administration disponibles figurent Générateur de topologie et le Panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="ae137-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="ae137-108">Les outils d’administration doivent être installés sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits qui exécute une version du système d’exploitation Windows pris en charge pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae137-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="ae137-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="ae137-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ae137-110">Vous devez cependant réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué par le diagramme.</span><span class="sxs-lookup"><span data-stu-id="ae137-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="ae137-111">L’installation des outils d’administration constitue la 3e des 8 étapes.</span><span class="sxs-lookup"><span data-stu-id="ae137-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Schéma de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="ae137-113">Installer Skype pour les outils d’administration Business Server</span><span class="sxs-lookup"><span data-stu-id="ae137-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="ae137-114">Le support d’installation pour Skype pour Business Server fournit une expérience flexible.</span><span class="sxs-lookup"><span data-stu-id="ae137-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="ae137-115">Lors de la première exécution de Setup.exe, installés les outils seulement sont le Skype pour l’Assistant de déploiement Business Server et le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ae137-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ae137-116">À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais ils ne fournissent pas de fonctionnalité principale pour le Skype globale pour l’environnement Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae137-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="ae137-117">L’assistant Déploiement démarre automatiquement après l’installation des composants principaux.</span><span class="sxs-lookup"><span data-stu-id="ae137-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="ae137-118">La section de l’Assistant Déploiement intitulée **Installer les outils d’administration** installe Skype pour le Générateur de topologie du serveur Business et Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ae137-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ae137-119">Chaque Skype pour un environnement Business Server doit avoir au moins un serveur doté des outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="ae137-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="ae137-120">Visionnez les étapes présentées dans la vidéo pour l’**installation des outils d’administration** :</span><span class="sxs-lookup"><span data-stu-id="ae137-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="ae137-121">Installer Skype pour les outils d’administration Business Server à partir de l’Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="ae137-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="ae137-122">Insérez le Skype pour le support d’installation Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae137-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="ae137-123">Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.</span><span class="sxs-lookup"><span data-stu-id="ae137-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="ae137-p106">Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous souhaitez l’installer. Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ae137-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="ae137-127">À l’aide de la configuration active, une nouvelle fonctionnalité de Skype pour Business Server, vous pouvez vous connecter à Internet pour vérifier les mises à jour au cours du processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="ae137-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="ae137-128">Cela permet une meilleure expérience du fait de la recherche des mises à jour les plus récentes disponibles pour le produit.</span><span class="sxs-lookup"><span data-stu-id="ae137-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="ae137-129">Cliquez sur **Installer** pour lancer l’installation.</span><span class="sxs-lookup"><span data-stu-id="ae137-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="ae137-130">Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae137-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="ae137-131">Le Skype pour les composants principaux d’entreprise Server sera installé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ae137-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="ae137-132">Les composants principaux sont les suivants, comme indiqué dans la figure.</span><span class="sxs-lookup"><span data-stu-id="ae137-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Composants centraux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="ae137-134">**Skype pour l’Assistant de déploiement Business Server** Un programme de déploiement qui fournit une zone de lancement pour installer les différents composants de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae137-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="ae137-135">**Skype pour Business Server Management Shell** Un programme PowerShell préconfiguré qui permet la gestion de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae137-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="ae137-136">Une fois l’installation des composants principaux est terminée, le Skype pour l’Assistant de déploiement Business Server lance automatiquement, comme le montre la figure.</span><span class="sxs-lookup"><span data-stu-id="ae137-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Assistant Déploiement de Skype Entreprise Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="ae137-138">Outre les composants principaux, vous devez également installer Skype pour le Générateur de topologie du serveur Business et Skype pour le panneau de configuration serveur Business au moins un serveur dans l’environnement.</span><span class="sxs-lookup"><span data-stu-id="ae137-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="ae137-139">Cliquez sur **Installer les outils d’administration** dans l’assistant Déploiement.</span><span class="sxs-lookup"><span data-stu-id="ae137-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="ae137-140">Cliquez sur **Suivant** pour commencer l’installation.</span><span class="sxs-lookup"><span data-stu-id="ae137-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="ae137-p109">Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont désormais ajoutés au serveur, comme indiqué dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="ae137-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype pour les outils d’administration serveur](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="ae137-144">**Skype pour le Générateur de topologie Business Server** Un programme utilisé pour générer, déployer et gérer les topologies.</span><span class="sxs-lookup"><span data-stu-id="ae137-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="ae137-145">**Skype pour le panneau de configuration serveur Business** Programme permettant de gérer l’installation.</span><span class="sxs-lookup"><span data-stu-id="ae137-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

