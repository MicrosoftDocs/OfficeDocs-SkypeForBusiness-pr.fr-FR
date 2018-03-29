---
title: Installation des outils d’administration dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Résumé : Apprenez à installer les outils d’administration requis pour une installation de Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a><span data-ttu-id="b7813-104">Installation des outils d’administration dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b7813-104">Install administrative tools in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b7813-105">**Résumé :** Apprenez à installer les outils d’administration requis pour une installation de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7813-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="b7813-106">Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="b7813-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b7813-107">Parmi les outils d’administration disponibles figurent Générateur de topologie et le Panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="b7813-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="b7813-108">Les outils d’administration doivent être installés sur au moins un serveur dans la topologie ou une station de travail de gestion 64 bits exécutant une version de système d’exploitation Windows est pris en charge par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7813-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="b7813-109">Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque.</span><span class="sxs-lookup"><span data-stu-id="b7813-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="b7813-110">Vous devez cependant réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué par le diagramme.</span><span class="sxs-lookup"><span data-stu-id="b7813-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="b7813-111">L’installation des outils d’administration constitue la 3e des 8 étapes.</span><span class="sxs-lookup"><span data-stu-id="b7813-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Schéma de vue d’ensemble](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a><span data-ttu-id="b7813-113">Installer Skype pour les outils d’administration de Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b7813-113">Install Skype for Business Server 2015 administrative tools</span></span>

<span data-ttu-id="b7813-114">Le support d’installation de Skype pour Business Server 2015 offre un environnement flexible.</span><span class="sxs-lookup"><span data-stu-id="b7813-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span></span> <span data-ttu-id="b7813-115">Lors de la première exécution de Setup.exe, les outils sont uniquement installés sont le Skype pour l’Assistant de déploiement de Business Server et le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7813-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b7813-116">À l’aide de ces deux outils, appelés composants principaux, vous pouvez poursuivre le processus d’installation, mais elles ne fournissent pas de fonctionnalité principale pour le Skype global pour l’environnement du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b7813-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="b7813-117">L’assistant Déploiement démarre automatiquement après l’installation des composants principaux.</span><span class="sxs-lookup"><span data-stu-id="b7813-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="b7813-118">La section de l’Assistant de déploiement intitulée **Installer les outils d’administration** installe Skype pour le Générateur de topologies de serveur Business et Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7813-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b7813-119">Chaque Skype pour environnement Business Server doit avoir au moins un serveur avec les outils d’administration est installés.</span><span class="sxs-lookup"><span data-stu-id="b7813-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="b7813-120">Visionnez les étapes présentées dans la vidéo pour l’**installation des outils d’administration** :</span><span class="sxs-lookup"><span data-stu-id="b7813-120">Watch the video steps for **Install administrative tools**:</span></span>
  
![Votre navigateur ne prend pas en charge la vidéo. Installez Microsoft Silverlight, Adobe Flash Player ou Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="b7813-123">Installer Skype pour Business Server 2015 des outils d’administration à partir de l’Assistant de déploiement</span><span class="sxs-lookup"><span data-stu-id="b7813-123">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="b7813-124">Insérez le Skype pour le support d’installation Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7813-124">Insert the Skype for Business Server 2015 installation media.</span></span> <span data-ttu-id="b7813-125">Si l’installation ne démarre pas automatiquement, double-cliquez sur **Installation (Setup)**.</span><span class="sxs-lookup"><span data-stu-id="b7813-125">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="b7813-p107">Le support d’installation nécessite Microsoft Visual C++ pour s’exécuter. Une boîte de dialogue apparaît pour demander si vous souhaitez l’installer. Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b7813-p107">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="b7813-129">En utilisant le programme d’installation active, une nouvelle fonctionnalité dans Skype pour 2015 de serveur d’entreprise, vous pouvez vous connecter à Internet pour vérifier les mises à jour pendant le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="b7813-129">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="b7813-130">Cela permet une meilleure expérience du fait de la recherche des mises à jour les plus récentes disponibles pour le produit.</span><span class="sxs-lookup"><span data-stu-id="b7813-130">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="b7813-131">Cliquez sur **Installer** pour lancer l’installation.</span><span class="sxs-lookup"><span data-stu-id="b7813-131">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="b7813-132">Passez en revue le Contrat de Licence Utilisateur Final et si vous êtes d’accord, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7813-132">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="b7813-133">Le Skype pour 2015 principaux composants Business Server sera installé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b7813-133">The Skype for Business Server 2015 Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="b7813-134">Les composants principaux sont les suivants, comme indiqué dans la figure.</span><span class="sxs-lookup"><span data-stu-id="b7813-134">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Composants centraux dans l’écran Apps.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="b7813-136">**Skype pour l’Assistant de déploiement 2015 Business Server** Un programme de déploiement qui fournit le lancement d’un boîtier de commande pour installer les différents composants de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7813-136">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span></span>
    
  - <span data-ttu-id="b7813-137">**Skype pour Business Server 2015 Management Shell** Un programme PowerShell préconfiguré qui permet l’administration de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7813-137">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span></span>
    
    <span data-ttu-id="b7813-138">Une fois l’installation des composants principaux est terminée, le Skype pour l’Assistant de déploiement 2015 Business Server démarre automatiquement, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="b7813-138">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Assistant Déploiement de Skype Entreprise Server 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="b7813-140">Outre les composants de base, vous devez également installer Skype pour le Générateur de topologies Business Server 2015 et Skype pour panneau de Business Server 2015 au moins un serveur dans l’environnement.</span><span class="sxs-lookup"><span data-stu-id="b7813-140">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="b7813-141">Cliquez sur **Installer les outils d’administration** dans l’assistant Déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7813-141">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="b7813-142">Cliquez sur **Suivant** pour commencer l’installation.</span><span class="sxs-lookup"><span data-stu-id="b7813-142">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="b7813-p110">Une fois l’installation terminée, cliquez sur **Terminer**. Les outils d’administration sont désormais ajoutés au serveur, comme indiqué dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="b7813-p110">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Outils d’administration du serveur Skype Entreprise 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="b7813-146">**Skype pour le Générateur de topologies 2015 Business Server** Un programme utilisé pour générer, déployer et gérer des topologies.</span><span class="sxs-lookup"><span data-stu-id="b7813-146">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="b7813-147">**Skype pour panneau Business Server 2015** Un programme permettant de gérer l’installation.</span><span class="sxs-lookup"><span data-stu-id="b7813-147">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span></span>
    

