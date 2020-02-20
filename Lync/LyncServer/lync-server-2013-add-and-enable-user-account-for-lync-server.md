---
title: 'Lync Server 2013 : ajouter et activer un compte d’utilisateur pour Lync Server'
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
ms.openlocfilehash: bcbea7a081de0f5416f0df1cf6628e66c0998b92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="8d0b9-102">Ajouter et activer un compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d0b9-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d0b9-103">_**Dernière modification de la rubrique :** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="8d0b9-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="8d0b9-104">Après avoir activé un compte d’utilisateur dans utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le panneau de configuration Lync Server pour créer et activer de nouveaux comptes d’utilisateur Lync Server 2013 en ajoutant un utilisateur Active Directory à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="8d0b9-105">Pour ajouter et activer un nouvel utilisateur Lync Server</span><span class="sxs-lookup"><span data-stu-id="8d0b9-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="8d0b9-106">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8d0b9-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8d0b9-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8d0b9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8d0b9-109">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8d0b9-110">Cliquez sur **Activer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="8d0b9-111">Dans la boîte de dialogue **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="8d0b9-112">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom, du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse e-mail, du nom d’utilisateur principal ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="8d0b9-113">Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Lync Server, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="8d0b9-114">Affectez l’utilisateur à un pool, indiquez d’autres détails utiles et affectez les stratégies à l’utilisateur voulu, puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="8d0b9-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d0b9-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d0b9-115">See Also</span></span>


[<span data-ttu-id="8d0b9-116">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d0b9-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="8d0b9-117">Supprimer un compte d’utilisateur de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d0b9-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="8d0b9-118">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d0b9-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

