---
title: 'Lync Server 2013 : test du déploiement du pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 552677dde2706265093879bc9b48ac803e1365fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="4192d-102">Test du déploiement du pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4192d-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4192d-103">_**Dernière modification de la rubrique :** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="4192d-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="4192d-104">La procédure suivante décrit comment tester le déploiement du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4192d-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="4192d-105">Pour tester le déploiement du pool</span><span class="sxs-lookup"><span data-stu-id="4192d-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="4192d-106">Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement de Lync Server 2013 (sur lequel le panneau de configuration Lync Server 2013 est installé) au groupe **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="4192d-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4192d-107">Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez un message d’erreur lors de l’ouverture du panneau de configuration Lync Server, qui indique que « l’accès est refusé en raison d’un échec d’autorisation de contrôle d’accès basé sur un rôle (RBAC) ».</span><span class="sxs-lookup"><span data-stu-id="4192d-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="4192d-108">Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="4192d-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4192d-109">Le compte d’utilisateur ne peut pas être l’administrateur local d’un serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4192d-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="4192d-110">Utilisez le compte d’administrateur pour vous connecter à l’ordinateur sur lequel le panneau de configuration Lync Server est installé.</span><span class="sxs-lookup"><span data-stu-id="4192d-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="4192d-111">Démarrez le panneau de configuration Lync Server, puis fournissez les informations d’identification, si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="4192d-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="4192d-112">Le panneau de configuration Lync Server affiche des informations sur le déploiement.</span><span class="sxs-lookup"><span data-stu-id="4192d-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="4192d-113">Dans la barre de navigation de gauche, cliquez sur **topologie**, puis confirmez que l’état du service indique un ordinateur avec une flèche verte et qu’une coche verte pour l’état de réplication est en regard de chaque rôle serveur Lync Server déployé et mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="4192d-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="4192d-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4192d-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="4192d-115">Sur la page **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4192d-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="4192d-p102">Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="4192d-p102">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="4192d-119">Dans le volet de résultats, sélectionnez tous les objets de cette session de recherche, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4192d-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="4192d-p103">Sur la page **Nouvel utilisateur Lync Server**, le ou les objets sélectionnés se trouvent dans l’affichage **Utilisateurs**. Dans la liste **Attribuer des utilisateurs à un pool**, sélectionnez le serveur qui devrait héberger les objets.</span><span class="sxs-lookup"><span data-stu-id="4192d-p103">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display. In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="4192d-122">Ce qui suit est une série d’options pour configurer les objets.</span><span class="sxs-lookup"><span data-stu-id="4192d-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="4192d-123">**Générer l’URI SIP de l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="4192d-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="4192d-124">**Téléphonie**</span><span class="sxs-lookup"><span data-stu-id="4192d-124">**Telephony**</span></span>
    
      - <span data-ttu-id="4192d-125">**URI de ligne**</span><span class="sxs-lookup"><span data-stu-id="4192d-125">**Line URI**</span></span>
    
      - <span data-ttu-id="4192d-126">**Stratégie de conférence**</span><span class="sxs-lookup"><span data-stu-id="4192d-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="4192d-127">**Stratégie de version du client**</span><span class="sxs-lookup"><span data-stu-id="4192d-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="4192d-128">**Stratégie de code confidentiel**</span><span class="sxs-lookup"><span data-stu-id="4192d-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="4192d-129">**Stratégie d’accès externe**</span><span class="sxs-lookup"><span data-stu-id="4192d-129">**External access policy**</span></span>
    
      - <span data-ttu-id="4192d-130">**Stratégie d’archivage**</span><span class="sxs-lookup"><span data-stu-id="4192d-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="4192d-131">**Stratégie d’emplacement**</span><span class="sxs-lookup"><span data-stu-id="4192d-131">**Location policy**</span></span>
    
      - <span data-ttu-id="4192d-132">**Stratégie du client**</span><span class="sxs-lookup"><span data-stu-id="4192d-132">**Client policy**</span></span>
    
    <span data-ttu-id="4192d-133">Pour tester les fonctionnalités de base, sélectionnez votre option préférée pour le paramètre **Générer l’URI SIP de l’utilisateur** (les autres options de la configuration utiliseront les paramètres par défaut), puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="4192d-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="4192d-p104">Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les objets sont désormais prêts à être utilisés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4192d-p104">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="4192d-136">Connectez un utilisateur sur un ordinateur qui est lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="4192d-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="4192d-137">Installez Lync 2013 sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Lync Server 2013 et peuvent envoyer des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="4192d-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4192d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4192d-138">See Also</span></span>


[<span data-ttu-id="4192d-139">Déploiement des clients et des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4192d-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

