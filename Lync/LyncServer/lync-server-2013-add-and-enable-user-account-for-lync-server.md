---
title: 'Lync Server 2013 : ajout et activation d’un compte d’utilisateur pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04a798a69279ebef6c4917938ead2fd88a49805
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="90b21-102">Ajouter et activer un compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90b21-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90b21-103">_**Dernière modification de la rubrique :** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="90b21-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="90b21-104">Après avoir activé un compte d’utilisateur dans utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le panneau de configuration de Lync Server pour créer et activer les nouveaux comptes d’utilisateurs Lync Server 2013 en ajoutant un utilisateur Active Directory à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90b21-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="90b21-105">Pour ajouter et activer un nouvel utilisateur Lync Server</span><span class="sxs-lookup"><span data-stu-id="90b21-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="90b21-106">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="90b21-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90b21-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90b21-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90b21-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90b21-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90b21-109">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="90b21-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="90b21-110">Cliquez sur **activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="90b21-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="90b21-111">Dans la boîte de dialogue **nouveau serveur Lync** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="90b21-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="90b21-112">Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom, le nom d’affichage, le prénom, le nom, le nom du compte Sam (Security Accounts Manager), l’adresse de messagerie, le nom d’utilisateur principal (UPN) ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="90b21-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="90b21-113">Dans le tableau, sélectionnez le compte que vous voulez ajouter à Lync Server, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="90b21-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="90b21-114">Affectez l’utilisateur à un pool, spécifiez des détails supplémentaires et attribuez les stratégies à l’utilisateur de votre choix, puis cliquez sur **activer**.</span><span class="sxs-lookup"><span data-stu-id="90b21-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90b21-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90b21-115">See Also</span></span>


[<span data-ttu-id="90b21-116">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90b21-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="90b21-117">Supprimer un compte d’utilisateur de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90b21-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="90b21-118">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90b21-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

