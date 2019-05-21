---
title: Installer les fichiers du serveur de médiation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Résumé: Découvrez comment installer les fichiers du serveur de médiation dans Skype entreprise Server.'
ms.openlocfilehash: 8ecd5b20f7f3dfac625851c94f313a50fa71af29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299442"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="73031-103">Installer les fichiers du serveur de médiation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="73031-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="73031-104">**Résumé:** Découvrez comment installer les fichiers du serveur de médiation dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="73031-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="73031-105">Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="73031-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="73031-106">Suivez les étapes décrites dans cette rubrique pour exécuter l’Assistant Déploiement de Skype entreprise Server et installer les fichiers de médiation Server sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation après avoir utilisé le générateur de topologie pour définir et publier le pool.</span><span class="sxs-lookup"><span data-stu-id="73031-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="73031-107">Lors de l’installation de files Mediation Server, vous installez et attribuez également le certificat requis par chaque ordinateur d’un pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="73031-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="73031-108">Cette rubrique part du principe que vous avez déjà défini et publié un pool de serveurs de médiation autonome dans votre topologie, comme décrit dans la rubrique [déploiement d’un serveur de médiation dans le générateur de topologie de Skype entreprise Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="73031-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="73031-109">Pour installer les fichiers sur un pool de serveurs de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="73031-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="73031-110">Sur le support d’installation, cliquez avec le bouton droit sur _ \<installation Media\> _ **\Setup\amd64\Setup.exe**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="73031-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="73031-111">Dans la page **Emplacement d’installation**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="73031-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="73031-p102">Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)</span><span class="sxs-lookup"><span data-stu-id="73031-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="73031-114">Dans la page **Assistant Déploiement de Skype entreprise Server** , cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="73031-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="73031-115">Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="73031-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="73031-116">Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="73031-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="73031-117">Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="73031-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="73031-118">À côté de l' **étape 2: configurer ou supprimer les composants serveur Skype entreprise**, cliquez sur **exécuter**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="73031-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="73031-119">Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="73031-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="73031-p103">Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.</span><span class="sxs-lookup"><span data-stu-id="73031-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="73031-123">Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="73031-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="73031-124">Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="73031-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="73031-125">Sur l’ordinateur sur lequel vous exécutez le panneau de configuration Skype entreprise Server, vérifiez sur la page **Topology** du panneau de configuration de Skype entreprise Server que l’état du service du serveur de médiation est représenté par une coche verte.</span><span class="sxs-lookup"><span data-stu-id="73031-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="73031-126">Si une croix rouge est affichée, sélectionnez le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="73031-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="73031-127">Dans le menu **Action**, cliquez sur **Démarrer tous les services**.</span><span class="sxs-lookup"><span data-stu-id="73031-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="73031-128">Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, suivez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="73031-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="73031-129">Si vous n’avez pas besoin d’installer des fichiers pour un serveur de médiation pour d’autres ordinateurs, suivez les procédures décrites dans la section [configurer des Trunks dans Skype entreprise Server](configure-trunks.md) afin de configurer les paramètres de la connexion de Trunking entre ce pool de serveurs de médiation (ou toute la médiation). Serveurs sur un site) et son homologue.</span><span class="sxs-lookup"><span data-stu-id="73031-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

