---
title: Vérifier la topologie dans Skype Entreprise Server
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
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Résumé : Découvrez comment vérifier que la topologie Skype Entreprise Server et les serveurs Active Directory fonctionnent comme prévu. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833834"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="34193-104">Vérifier la topologie dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="34193-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="34193-105">**Résumé :** Découvrez comment vérifier que la topologie Skype Entreprise Server et les serveurs Active Directory fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="34193-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="34193-106">Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du [Centre d’évaluation Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="34193-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="34193-107">Une fois la topologie publiée et les composants du système Skype Entreprise Server installés sur chacun des serveurs de la topologie, vous êtes prêt à vérifier que la topologie fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="34193-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="34193-108">Cela inclut la vérification que la configuration s’est propagée à tous les serveurs Active Directory afin que l’ensemble du domaine sache que Skype Entreprise est disponible dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="34193-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="34193-109">Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="34193-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="34193-110">Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="34193-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="34193-111">La vérification de la topologie est l’étape 8 sur 8.</span><span class="sxs-lookup"><span data-stu-id="34193-111">Verifying the topology is step 8 of 8.</span></span>
  
![Diagramme de vue d’ensemble.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="34193-113">Tester le déploiement de pool frontal</span><span class="sxs-lookup"><span data-stu-id="34193-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="34193-114">La dernière étape consiste à tester le pool frontal et à vérifier que les clients Skype Entreprise peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="34193-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="34193-115">Ajouter des utilisateurs et vérifier la connectivité du client</span><span class="sxs-lookup"><span data-stu-id="34193-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="34193-116">Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement de Skype Entreprise Server (sur lequel le Panneau de contrôle Skype Entreprise Server est installé) au groupe **CSAdministrator.**</span><span class="sxs-lookup"><span data-stu-id="34193-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="34193-117">Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez une erreur lorsque vous ouvrirez le Panneau de contrôle Skype Entreprise Server, qui indique « Non autorisé : l’accès est refusé en raison d’un échec d’autorisation du contrôle d’accès basé sur un rôle (RBAC). »</span><span class="sxs-lookup"><span data-stu-id="34193-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="34193-118">Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="34193-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="34193-119">Le compte d’utilisateur ne peut pas être l’administrateur local d’un serveur exécutant Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34193-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="34193-120">Utilisez le compte d’administration pour vous connecter à l’ordinateur sur lequel le Panneau de contrôle Skype Entreprise Server est installé.</span><span class="sxs-lookup"><span data-stu-id="34193-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="34193-121">Démarrez le Panneau de contrôle Skype Entreprise Server, puis fournissez les informations d’identification, si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="34193-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="34193-122">Le Panneau de contrôle Skype Entreprise Server affiche les informations de déploiement.</span><span class="sxs-lookup"><span data-stu-id="34193-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="34193-123">Dans la barre de navigation de gauche, cliquez sur Topologie, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de la réplication est en regard de chaque rôle Skype Entreprise Server qui a été déployé et mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="34193-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="34193-124">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="34193-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="34193-125">Dans la page **Nouvel utilisateur Skype Entreprise Server,** cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="34193-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="34193-126">Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="34193-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="34193-127">Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés.</span><span class="sxs-lookup"><span data-stu-id="34193-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="34193-128">Une fois que vous avez choisi vos options de recherche, cliquez sur **Rechercher.**</span><span class="sxs-lookup"><span data-stu-id="34193-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="34193-129">Dans le volet Résultats de la recherche, sélectionnez les utilisateurs que vous souhaitez ajouter, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="34193-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="34193-130">Dans la page **Nouvel utilisateur Skype Entreprise Server,** les utilisateurs que vous avez sélectionnés sont affichés dans **l’affichage** Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="34193-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="34193-131">Dans la **liste Affecter des utilisateurs à un pool,** sélectionnez le serveur où les utilisateurs doivent résider.</span><span class="sxs-lookup"><span data-stu-id="34193-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="34193-132">Voici une liste d’options que vous pouvez utiliser pour configurer les objets.</span><span class="sxs-lookup"><span data-stu-id="34193-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="34193-133">**Générer l’URI SIP de l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="34193-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="34193-134">**Téléphonie**</span><span class="sxs-lookup"><span data-stu-id="34193-134">**Telephony**</span></span>
    
    - <span data-ttu-id="34193-135">**URI de ligne**</span><span class="sxs-lookup"><span data-stu-id="34193-135">**Line URI**</span></span>
    
    - <span data-ttu-id="34193-136">**Stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="34193-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="34193-137">**Stratégie de version du client**</span><span class="sxs-lookup"><span data-stu-id="34193-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="34193-138">**Stratégie de code confidentiel**</span><span class="sxs-lookup"><span data-stu-id="34193-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="34193-139">**Stratégie d’accès externe**</span><span class="sxs-lookup"><span data-stu-id="34193-139">**External access policy**</span></span>
    
    - <span data-ttu-id="34193-140">**Stratégie d’archivage**</span><span class="sxs-lookup"><span data-stu-id="34193-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="34193-141">**Stratégie d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="34193-141">**Location policy**</span></span>
    
    - <span data-ttu-id="34193-142">**Stratégie du client**</span><span class="sxs-lookup"><span data-stu-id="34193-142">**Client policy**</span></span>
    
    <span data-ttu-id="34193-143">Pour tester les fonctionnalités de base, sélectionnez l’option de votre choix pour le paramètre Générer **l’URI SIP de l’utilisateur** (les autres options de la configuration utilisent les paramètres par défaut), puis cliquez sur **Activer,** comme illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="34193-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Activez les utilisateurs dans le Panneau de contrôle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="34193-145">Une page récapitulatif s’affiche et affiche une coche dans la colonne **Enabled** pour indiquer que les utilisateurs sont en cours d’installation.</span><span class="sxs-lookup"><span data-stu-id="34193-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="34193-146">La **colonne d’adresse SIP** affiche l’adresse dont vous avez besoin pour la configuration de la connectez-vous de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="34193-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Utilisateurs ajoutés au Panneau de contrôle Skype Entreprise Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="34193-148">Connectez un utilisateur à un ordinateur qui est joint au domaine et un autre utilisateur sur un autre ordinateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="34193-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="34193-149">Installez le client Skype Entreprise sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Skype Entreprise Server et s’envoyer des messages instantanés entre eux.</span><span class="sxs-lookup"><span data-stu-id="34193-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

