---
title: Vérifier la topologie dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé: Découvrez comment vérifier que la topologie du serveur Skype entreprise et les serveurs Active Directory fonctionnent comme prévu. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245235"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="edf67-104">Vérifier la topologie dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="edf67-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="edf67-105">**Résumé:** Découvrez comment vérifier que la topologie de Skype entreprise Server et les serveurs Active Directory fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="edf67-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="edf67-106">Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="edf67-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="edf67-107">Après la publication de la topologie et des composants du système Skype entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="edf67-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="edf67-108">Pour cela, vous devez vérifier que la configuration a été propagée sur tous les serveurs Active Directory de sorte que l’intégralité du domaine sache que Skype entreprise est disponible dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="edf67-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="edf67-109">Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="edf67-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="edf67-110">Cependant, vous devez réaliser les étapes 6, 7 et 8 dans l’ordre stipulé, après les étapes 1 à 5, comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="edf67-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="edf67-111">La vérification de la topologie est la 8e des 8 étapes.</span><span class="sxs-lookup"><span data-stu-id="edf67-111">Verifying the topology is step 8 of 8.</span></span>
  
![Schéma de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="edf67-113">Test du déploiement de pool frontal</span><span class="sxs-lookup"><span data-stu-id="edf67-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="edf67-114">La dernière étape consiste à tester le pool frontal et à confirmer que les clients Skype entreprise peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="edf67-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="edf67-115">Ajout d’utilisateur et vérification de la connectivité entre les clients</span><span class="sxs-lookup"><span data-stu-id="edf67-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="edf67-116">Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle administrateur pour le déploiement de Skype entreprise Server (sur lequel est installé le panneau de configuration Skype entreprise Server) vers le groupe **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="edf67-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edf67-117">Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous recevez un message d’erreur lors de l’ouverture du panneau de configuration Skype entreprise Server qui lit «non autorisé: accès refusé en raison d’un échec de l’autorisation de contrôle d’accès basé sur un rôle (RBAC) ."</span><span class="sxs-lookup"><span data-stu-id="edf67-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="edf67-118">Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="edf67-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="edf67-119">Le compte d’utilisateur ne peut pas être l’administrateur local de tout serveur exécutant Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="edf67-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="edf67-120">Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel est installé le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="edf67-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="edf67-121">Démarrez le panneau de configuration Skype entreprise Server, puis fournissez les informations d’identification, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="edf67-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="edf67-122">Le panneau de configuration Skype entreprise Server affiche des informations de déploiement.</span><span class="sxs-lookup"><span data-stu-id="edf67-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="edf67-123">Dans la barre de navigation de gauche, cliquez sur **Topology**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication est située en regard de chaque rôle serveur Skype entreprise déployé et remis en ligne.</span><span class="sxs-lookup"><span data-stu-id="edf67-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="edf67-124">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="edf67-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="edf67-125">Dans la page de l' **utilisateur Skype entreprise Server** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="edf67-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="edf67-p105">Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="edf67-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="edf67-129">Dans le volet de résultats, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="edf67-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="edf67-130">Dans la page de l' **utilisateur de Skype entreprise Server** , les utilisateurs sélectionnés se trouvent dans l’affichage **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="edf67-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="edf67-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="edf67-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="edf67-132">Voici ci-après une liste des options pouvant être utilisées pour configurer les objets.</span><span class="sxs-lookup"><span data-stu-id="edf67-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="edf67-133">**Générer URI SIP de l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="edf67-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="edf67-134">**Téléphonie**</span><span class="sxs-lookup"><span data-stu-id="edf67-134">**Telephony**</span></span>
    
    - <span data-ttu-id="edf67-135">**URI de ligne**</span><span class="sxs-lookup"><span data-stu-id="edf67-135">**Line URI**</span></span>
    
    - <span data-ttu-id="edf67-136">**Stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="edf67-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="edf67-137">**Stratégie de version du client**</span><span class="sxs-lookup"><span data-stu-id="edf67-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="edf67-138">**Stratégie de code confidentiel**</span><span class="sxs-lookup"><span data-stu-id="edf67-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="edf67-139">**Stratégie d’accès externe**</span><span class="sxs-lookup"><span data-stu-id="edf67-139">**External access policy**</span></span>
    
    - <span data-ttu-id="edf67-140">**Stratégie d’archivage**</span><span class="sxs-lookup"><span data-stu-id="edf67-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="edf67-141">**Stratégie d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="edf67-141">**Location policy**</span></span>
    
    - <span data-ttu-id="edf67-142">**Stratégie du client**</span><span class="sxs-lookup"><span data-stu-id="edf67-142">**Client policy**</span></span>
    
    <span data-ttu-id="edf67-143">Pour tester la fonctionnalité de base, sélectionnez l’option de votre choix pour le paramètre **URI SIP de l’utilisateur générer** (les autres options dans la configuration utiliser les paramètres par défaut), puis cliquez sur **activer**, comme indiqué dans l’illustration.</span><span class="sxs-lookup"><span data-stu-id="edf67-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Activez des utilisateurs dans le Panneau de configuration.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="edf67-p107">Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les utilisateurs sont configurés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="edf67-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Utilisateurs ajoutés au Panneau de configuration de Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="edf67-148">Connectez un utilisateur sur un ordinateur lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="edf67-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="edf67-149">Installez le client Skype entreprise sur chacun des deux ordinateurs client, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype entreprise Server et pouvoir vous envoyer des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="edf67-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

