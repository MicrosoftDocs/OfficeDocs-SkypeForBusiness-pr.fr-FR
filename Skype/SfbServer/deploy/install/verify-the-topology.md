---
title: Vérifier la topologie dans Skype pour Business Server
ms.author: kenwith
author: kenwith
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
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé : Découvrez comment vérifier la Skype pour la topologie du serveur d’entreprise et serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: ed06860837805886f1d2287f23281edb90c470c1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881972"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="5155f-104">Vérifier la topologie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5155f-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="5155f-105">**Résumé :** Découvrez comment vérifier la Skype pour la topologie du serveur d’entreprise et serveurs Active Directory fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="5155f-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="5155f-106">Téléchargez une version d’évaluation gratuite de Skype pour Business Server à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="5155f-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="5155f-107">Une fois que la topologie publiée et la Skype pour les composants du système Business Server installé sur chacun des serveurs dans la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="5155f-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="5155f-108">Cela inclut de vérifier que la configuration est propagée à tous les serveurs Active Directory pour que la totalité du domaine sache que Skype pour les entreprises est disponible dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="5155f-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="5155f-109">Vous pouvez effectuer les étapes 1 à 5 dans un ordre quelconque.</span><span class="sxs-lookup"><span data-stu-id="5155f-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="5155f-110">Cependant, vous devez réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="5155f-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="5155f-111">La vérification de la topologie est la 8e des 8 étapes.</span><span class="sxs-lookup"><span data-stu-id="5155f-111">Verifying the topology is step 8 of 8.</span></span>
  
![Schéma de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="5155f-113">Test du déploiement de pool frontal</span><span class="sxs-lookup"><span data-stu-id="5155f-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="5155f-114">L’étape finale consiste à tester le pool frontal et confirmez que Skype pour les clients d’entreprise peut communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="5155f-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="5155f-115">Ajout d’utilisateur et vérification de la connectivité entre les clients</span><span class="sxs-lookup"><span data-stu-id="5155f-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="5155f-116">Utilisez les utilisateurs et ordinateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le Skype pour le déploiement de serveur d’entreprise (sur lequel est installé Skype pour le panneau de configuration serveur Business) au groupe **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="5155f-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5155f-117">Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez une erreur lorsque vous ouvrez Skype pour Business Server Control Panel qui lit, « non autorisé : accès refusé en raison d’un échec de l’autorisation d’accès basé sur un rôle RBAC (contrôle) ."</span><span class="sxs-lookup"><span data-stu-id="5155f-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="5155f-118">Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="5155f-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5155f-119">Le compte d’utilisateur ne peut pas être administrateur local de n’importe quel serveur exécutant Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="5155f-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="5155f-120">Utilisez le compte administratif pour ouvrir une session sur l’ordinateur où est installé Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="5155f-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="5155f-121">Démarrez Skype pour Business Server le panneau de configuration, puis fournissez les informations d’identification, si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="5155f-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="5155f-122">Skype pour Business Server Control Panel affiche les informations de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5155f-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="5155f-123">Dans la barre de navigation de gauche, cliquez sur **la topologie**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication est en regard de chaque Skype pour le rôle de serveur d’entreprise qui a été déployé et mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="5155f-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="5155f-124">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="5155f-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="5155f-125">Dans la page **Nouvelle Skype pour l’utilisateur Business Server** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5155f-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="5155f-p105">Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="5155f-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="5155f-129">Dans le volet de résultats, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5155f-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="5155f-130">Dans la page **Nouvelle Skype pour l’utilisateur Business Server** , les utilisateurs sélectionnés sont dans l’affichage des **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="5155f-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="5155f-131">Dans la liste **Attribuer des utilisateurs à un pool**, sélectionnez le serveur qui devrait héberger les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5155f-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="5155f-132">Voici ci-après une liste des options pouvant être utilisées pour configurer les objets.</span><span class="sxs-lookup"><span data-stu-id="5155f-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="5155f-133">**Générer l’URI SIP de l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="5155f-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="5155f-134">**Téléphonie**</span><span class="sxs-lookup"><span data-stu-id="5155f-134">**Telephony**</span></span>
    
    - <span data-ttu-id="5155f-135">**URI de ligne**</span><span class="sxs-lookup"><span data-stu-id="5155f-135">**Line URI**</span></span>
    
    - <span data-ttu-id="5155f-136">**Stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="5155f-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="5155f-137">**Stratégie de version du client**</span><span class="sxs-lookup"><span data-stu-id="5155f-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="5155f-138">**Stratégie de code confidentiel**</span><span class="sxs-lookup"><span data-stu-id="5155f-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="5155f-139">**Stratégie d’accès externe**</span><span class="sxs-lookup"><span data-stu-id="5155f-139">**External access policy**</span></span>
    
    - <span data-ttu-id="5155f-140">**Stratégie d’archivage**</span><span class="sxs-lookup"><span data-stu-id="5155f-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="5155f-141">**Stratégie d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="5155f-141">**Location policy**</span></span>
    
    - <span data-ttu-id="5155f-142">**Stratégie du client**</span><span class="sxs-lookup"><span data-stu-id="5155f-142">**Client policy**</span></span>
    
    <span data-ttu-id="5155f-143">Pour tester la fonctionnalité de base, sélectionnez l’option que vous préférez pour le paramètre **URI SIP de l’utilisateur de générer** (autres options Paramètres de configuration utilisés par défaut), puis cliquez sur **Activer**, comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="5155f-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Activez des utilisateurs dans le Panneau de configuration.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="5155f-p107">Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les utilisateurs sont configurés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5155f-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Utilisateurs ajoutés au Panneau de configuration de Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="5155f-148">Connectez un utilisateur sur un ordinateur lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="5155f-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="5155f-149">Installer Skype pour Business client sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype pour Business Server et peuvent envoyer des messages instantanés entre eux.</span><span class="sxs-lookup"><span data-stu-id="5155f-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

