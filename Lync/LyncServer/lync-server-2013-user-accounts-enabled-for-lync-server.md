---
title: 'Lync Server 2013 : comptes d’utilisateur activés pour Lync Server'
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
ms.openlocfilehash: 6d51f72f586ab6d5b5094c61ae09d8ac316350b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="b072e-102">Comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b072e-103">_**Dernière modification de la rubrique :** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="b072e-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="b072e-104">Les rubriques de cette section comportent des procédures détaillées pour la configuration des paramètres utilisateur que vous pouvez effectuer à l’aide du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b072e-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b072e-105">Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour gérer les utilisateurs membres du groupe administrateurs du domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b072e-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="b072e-106">Pour les utilisateurs administrateurs du domaine, vous pouvez utiliser le panneau de configuration Lync Server uniquement pour effectuer des opérations de recherche en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="b072e-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="b072e-107">Pour effectuer des opérations d’écriture sur les utilisateurs des administrateurs du domaine (par exemple, activer ou désactiver le panneau de configuration de Lync Server, modifier les attributions de stratégie ou de pool, les paramètres de téléphonie, l’adresse SIP), vous devez utiliser les applets de commande Windows PowerShell lorsque vous êtes connecté en tant qu’utilisateur administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="b072e-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="b072e-108">Pour plus d’informations sur l’utilisation des applets de commande Windows PowerShell pour gérer les utilisateurs, voir <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span><span class="sxs-lookup"><span data-stu-id="b072e-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="b072e-109">Lorsque vous effectuez une tâche administrative Lync Server 2013 qui implique la recherche d’un utilisateur ou le filtrage des résultats de la recherche utilisateur, il existe des propriétés utilisateur qui existent en tant qu’attributs dans les services de domaine Active Directory, mais qui ne sont pas répliquées dans le catalogue global. tant que Microsoft Exchange Server n’est pas déployé.</span><span class="sxs-lookup"><span data-stu-id="b072e-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="b072e-110">Microsoft Exchange, et non Lync Server, marque les attributs suivants pour la réplication dans le catalogue global lors de l’installation :</span><span class="sxs-lookup"><span data-stu-id="b072e-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b072e-111">Informations utilisateur</span><span class="sxs-lookup"><span data-stu-id="b072e-111">User Information</span></span></th>
<th><span data-ttu-id="b072e-112">Adresse et numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="b072e-112">Address and Phone</span></span></th>
<th><span data-ttu-id="b072e-113">Organisation</span><span class="sxs-lookup"><span data-stu-id="b072e-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b072e-114">Initiales</span><span class="sxs-lookup"><span data-stu-id="b072e-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="b072e-115">Rue</span><span class="sxs-lookup"><span data-stu-id="b072e-115">Street address</span></span></p>
<p><span data-ttu-id="b072e-116">Pays/région</span><span class="sxs-lookup"><span data-stu-id="b072e-116">Country/region</span></span></p>
<p><span data-ttu-id="b072e-117">Alphanumérique</span><span class="sxs-lookup"><span data-stu-id="b072e-117">Pager</span></span></p>
<p><span data-ttu-id="b072e-118">Télécopie</span><span class="sxs-lookup"><span data-stu-id="b072e-118">Fax</span></span></p>
<p><span data-ttu-id="b072e-119">Mobile</span><span class="sxs-lookup"><span data-stu-id="b072e-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="b072e-120">Titre</span><span class="sxs-lookup"><span data-stu-id="b072e-120">Title</span></span></p>
<p><span data-ttu-id="b072e-121">Company</span><span class="sxs-lookup"><span data-stu-id="b072e-121">Company</span></span></p>
<p><span data-ttu-id="b072e-122">Service</span><span class="sxs-lookup"><span data-stu-id="b072e-122">Department</span></span></p>
<p><span data-ttu-id="b072e-123">Bureau</span><span class="sxs-lookup"><span data-stu-id="b072e-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="b072e-124">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b072e-124">In This Section</span></span>

  - [<span data-ttu-id="b072e-125">Affichage des informations sur les comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="b072e-126">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="b072e-127">Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="b072e-128">Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="b072e-129">Gérer la stratégie d’accès externe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="b072e-130">Affectation de stratégies par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b072e-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b072e-131">See Also</span></span>


[<span data-ttu-id="b072e-132">Applets de commande de gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="b072e-133">Gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b072e-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

