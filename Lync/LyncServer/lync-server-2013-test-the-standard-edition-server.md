---
title: 'Lync Server 2013 : Test du serveur Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00918643fcc59efc33d12dc3f8f77c7d3ac69815
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f307c-102">Test du serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f307c-102">Test the Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f307c-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f307c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f307c-104">La procédure suivante vous explique comment tester le déploiement d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f307c-104">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="f307c-105">Pour tester le déploiement d’un serveur Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="f307c-105">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="f307c-106">Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement de Lync Server 2013 (sur lequel est installé le panneau de configuration Lync Server) vers le groupe **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="f307c-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="f307c-107">Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.</span><span class="sxs-lookup"><span data-stu-id="f307c-107">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f307c-108">Le compte d’utilisateur ne peut pas être l’administrateur local du serveur exécutant Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f307c-108">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="f307c-109">Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous recevez un message d’erreur lors de l’ouverture du panneau de configuration de Lync Server 2013, qui indique que l’accès non autorisé est refusé en raison d’un échec d’autorisation de contrôle d’accès basé sur un rôle (RBAC).»</span><span class="sxs-lookup"><span data-stu-id="f307c-109">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="f307c-110">Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel le panneau de configuration de Lync Server est installé.</span><span class="sxs-lookup"><span data-stu-id="f307c-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="f307c-111">Démarrez le panneau de configuration de Lync Server et fournissez les informations d’identification, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="f307c-111">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="f307c-112">Le panneau de configuration de Lync Server 2013 affiche des informations de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f307c-112">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="f307c-113">Dans la barre de navigation de gauche, cliquez sur **Topology**, puis vérifiez que l’état du service est une icône d’ordinateur avec une flèche verte et qu’une coche verte apparaît à côté de chaque rôle serveur Lync Server déployé et remis en ligne.</span><span class="sxs-lookup"><span data-stu-id="f307c-113">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="f307c-114">Dans la barre de navigation de gauche, cliquez sur **utilisateurs**, puis activez les deux utilisateurs pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f307c-114">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="f307c-115">Connectez un utilisateur à un ordinateur joint au domaine et à l’autre utilisateur sur un autre ordinateur du domaine.</span><span class="sxs-lookup"><span data-stu-id="f307c-115">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="f307c-116">Installez Lync Server 2013 sur chacun des deux ordinateurs client, puis vérifiez que les deux utilisateurs peuvent se connecter à Lync Server 2013 et pouvoir vous envoyer des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="f307c-116">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f307c-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f307c-117">See Also</span></span>


[<span data-ttu-id="f307c-118">Déploiement de clients et d’appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f307c-118">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

