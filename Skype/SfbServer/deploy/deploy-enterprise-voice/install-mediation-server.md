---
title: Installer les fichiers pour le serveur de médiation dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Résumé : Découvrez comment installer les fichiers pour le serveur de médiation dans Skype pour Business Server.'
ms.openlocfilehash: ab02655dc812815c79720d76c87bfefe91c90c73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223054"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="24496-103">Installer les fichiers pour le serveur de médiation dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="24496-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="24496-104">**Résumé :** Découvrez comment installer les fichiers pour le serveur de médiation dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="24496-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="24496-105">Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="24496-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="24496-106">Utilisez les étapes décrites dans cette rubrique pour exécuter les Skype pour l’Assistant de déploiement Business Server installer les fichiers pour le serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveur de médiation après avoir utilisé le Générateur de topologie pour définir et publier le pool.</span><span class="sxs-lookup"><span data-stu-id="24496-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="24496-107">Lorsque vous installez les fichiers serveur de médiation, vous également installez et affectez le certificat requis par chaque ordinateur dans un pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="24496-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24496-108">Cette rubrique suppose que vous avez déjà défini et publié un pool de serveur de médiation autonome dans votre topologie, comme décrit dans [déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="24496-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="24496-109">Pour installer les fichiers sur un pool de serveurs de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="24496-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="24496-110">À partir du support d’installation, avec le bouton droit _ \<support d’installation\> _ **\Setup\amd64\Setup.exe**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="24496-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="24496-111">Dans la page **Emplacement d’installation**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="24496-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="24496-p102">Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)</span><span class="sxs-lookup"><span data-stu-id="24496-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="24496-114">Dans la page **Skype pour l’Assistant de déploiement Business Server** , cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="24496-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="24496-115">Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="24496-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="24496-116">Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="24496-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="24496-117">Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="24496-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="24496-118">Regard **étape 2 : installer ou supprimer des Skype pour les composants du serveur Business**, cliquez sur **exécuter**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="24496-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="24496-119">Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="24496-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="24496-p103">Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.</span><span class="sxs-lookup"><span data-stu-id="24496-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="24496-123">Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="24496-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="24496-124">Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="24496-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="24496-125">Sur l’ordinateur sur lequel vous exécutez Skype pour Business Server le panneau de configuration, vérifiez sur la page **topologie** de Skype pour Business Server Control Panel l’état du service du serveur de médiation est affiché en tant qu’une coche verte.</span><span class="sxs-lookup"><span data-stu-id="24496-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="24496-126">Si une croix rouge est affichée, sélectionnez le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="24496-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="24496-127">Dans le menu **Action**, cliquez sur **Démarrer tous les services**.</span><span class="sxs-lookup"><span data-stu-id="24496-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="24496-128">Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, effectuez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="24496-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="24496-129">Si vous n’avez pas besoin installer les fichiers d’un serveur de médiation pour d’autres ordinateurs, puis suivez les procédures de [configuration de jonctions dans Skype pour Business Server](configure-trunks.md) pour configurer les paramètres pour la connexion de jonction entre ce pool de serveur de médiation (ou la médiation tous les Serveurs sur un site) et son homologue.</span><span class="sxs-lookup"><span data-stu-id="24496-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

