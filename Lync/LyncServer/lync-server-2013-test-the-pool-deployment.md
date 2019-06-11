---
title: 'Lync Server 2013 : Test du déploiement du pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="72905-102">Test du déploiement du pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72905-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72905-103">_**Dernière modification de la rubrique:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="72905-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="72905-104">La procédure suivante vous explique comment tester le déploiement du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="72905-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="72905-105">Pour tester le déploiement du pool</span><span class="sxs-lookup"><span data-stu-id="72905-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="72905-106">Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle administrateur pour le déploiement de Lync Server 2013 (sur lequel est installé le panneau de configuration Lync Server 2013) vers le groupe **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="72905-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72905-107">Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous recevez un message d’erreur lors de l’ouverture du panneau de configuration de Lync Server, qui indique que l’accès à un contrôle de contrôle d’accès basé sur les rôles (RBAC) est refusé en raison d’un échec de l’autorisation de contrôle d’accès basé sur un rôle.»</span><span class="sxs-lookup"><span data-stu-id="72905-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="72905-108">Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="72905-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72905-109">Le compte d’utilisateur ne peut pas être l’administrateur local de tout serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72905-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="72905-110">Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel le panneau de configuration de Lync Server est installé.</span><span class="sxs-lookup"><span data-stu-id="72905-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="72905-111">Démarrez le panneau de configuration de Lync Server, puis fournissez les informations d’identification, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="72905-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="72905-112">Le panneau de configuration de Lync Server affiche des informations de déploiement.</span><span class="sxs-lookup"><span data-stu-id="72905-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="72905-113">Dans la barre de navigation de gauche, cliquez sur **Topology**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de réplication est située en regard de chaque rôle serveur Lync Server déployé et remis en ligne.</span><span class="sxs-lookup"><span data-stu-id="72905-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="72905-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="72905-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="72905-115">Dans la page **nouveau serveur Lync** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="72905-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="72905-116">Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="72905-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="72905-117">Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés.</span><span class="sxs-lookup"><span data-stu-id="72905-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="72905-118">Après avoir choisi les options de recherche, **sélectionnez Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="72905-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="72905-119">Dans le volet résultats de la recherche, sélectionnez tous les objets pour cette session de recherche, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="72905-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="72905-120">Dans la page **nouvel utilisateur de Lync Server** , le ou les objets que vous avez sélectionnés apparaissent dans l’affichage **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="72905-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="72905-121">Dans la liste **attribuer des utilisateurs à un pool** , sélectionnez le serveur sur lequel les objets doivent être hébergés.</span><span class="sxs-lookup"><span data-stu-id="72905-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="72905-122">Vous trouverez ci-dessous un certain nombre d’options de configuration des objets.</span><span class="sxs-lookup"><span data-stu-id="72905-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="72905-123">**Générer l’URL SIP de l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="72905-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="72905-124">**Téléphonie**</span><span class="sxs-lookup"><span data-stu-id="72905-124">**Telephony**</span></span>
    
      - <span data-ttu-id="72905-125">**URI de ligne**</span><span class="sxs-lookup"><span data-stu-id="72905-125">**Line URI**</span></span>
    
      - <span data-ttu-id="72905-126">**Stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="72905-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="72905-127">**Stratégie de version du client**</span><span class="sxs-lookup"><span data-stu-id="72905-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="72905-128">**Stratégie de code confidentiel**</span><span class="sxs-lookup"><span data-stu-id="72905-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="72905-129">**Stratégie d’accès externe**</span><span class="sxs-lookup"><span data-stu-id="72905-129">**External access policy**</span></span>
    
      - <span data-ttu-id="72905-130">**Stratégie d’archivage**</span><span class="sxs-lookup"><span data-stu-id="72905-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="72905-131">**Stratégie d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="72905-131">**Location policy**</span></span>
    
      - <span data-ttu-id="72905-132">**Stratégie du client**</span><span class="sxs-lookup"><span data-stu-id="72905-132">**Client policy**</span></span>
    
    <span data-ttu-id="72905-133">Pour tester la fonctionnalité de base, sélectionnez l’option de votre choix pour le paramètre **URI SIP de l’utilisateur générer** (les autres options dans la configuration utiliseront les paramètres par défaut), puis cliquez sur **activer**.</span><span class="sxs-lookup"><span data-stu-id="72905-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="72905-134">Une page de résumé s’ouvre et affiche une coche dans la colonne **activé** pour indiquer que les objets sont désormais prêts à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="72905-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="72905-135">La colonne **adresse SIP** affiche l’adresse dont vous avez besoin pour la configuration de connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="72905-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="72905-136">Connectez un utilisateur à un ordinateur joint au domaine et un autre utilisateur à un autre ordinateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="72905-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="72905-137">Installez Lync 2013 sur chacun des deux ordinateurs client, puis vérifiez que les deux utilisateurs peuvent se connecter à Lync Server 2013 et pouvoir vous envoyer des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="72905-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72905-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72905-138">See Also</span></span>


[<span data-ttu-id="72905-139">Déploiement de clients et d’appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72905-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

