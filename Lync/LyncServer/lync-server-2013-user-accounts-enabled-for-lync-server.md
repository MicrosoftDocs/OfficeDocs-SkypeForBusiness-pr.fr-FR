---
title: 'Lync Server 2013 : comptes d’utilisateurs activés pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="d50f4-102">Comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d50f4-103">_**Dernière modification de la rubrique :** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="d50f4-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="d50f4-104">Les rubriques de cette section fournissent des procédures pas à pas permettant de configurer les paramètres utilisateur que vous pouvez effectuer à l’aide du panneau de configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d50f4-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d50f4-105">Vous ne pouvez pas utiliser le panneau de configuration de Lync Server pour gérer les utilisateurs membres du groupe administrateurs de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d50f4-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="d50f4-106">Pour les utilisateurs de Domain Admins, vous pouvez utiliser le panneau de configuration de Lync Server uniquement pour effectuer des opérations de recherche en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="d50f4-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="d50f4-107">Pour effectuer des opérations d’écriture sur des utilisateurs de Domain Admins (par exemple, activer ou désactiver pour le panneau de configuration de Lync Server, modifier les affectations de la liste ou des stratégies, paramètres de téléphonie, adresse SIP), vous devez utiliser les applets de commande Windows PowerShell lorsque vous êtes connecté en tant qu’utilisateur administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="d50f4-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="d50f4-108">Pour plus d’informations sur l’utilisation des cmdlets Windows PowerShell pour gérer les utilisateurs, voir <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="d50f4-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="d50f4-109">Lors de l’exécution d’une tâche administrative Lync Server 2013 qui implique de rechercher un utilisateur ou de filtrer les résultats de la recherche utilisateur, il existe des propriétés utilisateur qui existent en tant qu’attributs dans les services de domaine Active Directory (AD FS), mais qui ne sont pas répliquées dans le catalogue global. tant que Microsoft Exchange Server n’est pas déployé.</span><span class="sxs-lookup"><span data-stu-id="d50f4-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="d50f4-110">Microsoft Exchange, et non Lync Server, marque les attributs suivants pour la réplication dans le catalogue global lors de son installation :</span><span class="sxs-lookup"><span data-stu-id="d50f4-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d50f4-111">Informations utilisateur</span><span class="sxs-lookup"><span data-stu-id="d50f4-111">User Information</span></span></th>
<th><span data-ttu-id="d50f4-112">Adresse et téléphone</span><span class="sxs-lookup"><span data-stu-id="d50f4-112">Address and Phone</span></span></th>
<th><span data-ttu-id="d50f4-113">Organisation</span><span class="sxs-lookup"><span data-stu-id="d50f4-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d50f4-114">Initiales</span><span class="sxs-lookup"><span data-stu-id="d50f4-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="d50f4-115">Adresse postale</span><span class="sxs-lookup"><span data-stu-id="d50f4-115">Street address</span></span></p>
<p><span data-ttu-id="d50f4-116">Pays/région</span><span class="sxs-lookup"><span data-stu-id="d50f4-116">Country/region</span></span></p>
<p><span data-ttu-id="d50f4-117">Radiomessagerie</span><span class="sxs-lookup"><span data-stu-id="d50f4-117">Pager</span></span></p>
<p><span data-ttu-id="d50f4-118">DelrinaFax</span><span class="sxs-lookup"><span data-stu-id="d50f4-118">Fax</span></span></p>
<p><span data-ttu-id="d50f4-119">Mobile</span><span class="sxs-lookup"><span data-stu-id="d50f4-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="d50f4-120">Titre</span><span class="sxs-lookup"><span data-stu-id="d50f4-120">Title</span></span></p>
<p><span data-ttu-id="d50f4-121">Elle</span><span class="sxs-lookup"><span data-stu-id="d50f4-121">Company</span></span></p>
<p><span data-ttu-id="d50f4-122">Service</span><span class="sxs-lookup"><span data-stu-id="d50f4-122">Department</span></span></p>
<p><span data-ttu-id="d50f4-123">Office</span><span class="sxs-lookup"><span data-stu-id="d50f4-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="d50f4-124">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d50f4-124">In This Section</span></span>

  - [<span data-ttu-id="d50f4-125">Affichage d’informations sur les comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="d50f4-126">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="d50f4-127">Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="d50f4-128">Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="d50f4-129">Gestion de la stratégie d’accès externe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="d50f4-130">Attribution de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d50f4-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d50f4-131">See Also</span></span>


[<span data-ttu-id="d50f4-132">Cmdlets de gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="d50f4-133">Gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d50f4-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

