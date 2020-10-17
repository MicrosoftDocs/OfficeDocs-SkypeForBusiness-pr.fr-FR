---
title: 'Lync Server 2013 : délégation du contrôle administratif de Lync Server'
description: 'Lync Server 2013 : délégation du contrôle administratif de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567490"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="a7f54-103">Délégation du contrôle administratif de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7f54-103">Delegating administrative control of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7f54-104">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a7f54-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a7f54-105">Dans Lync Server 2013, les tâches d’administration sont déléguées aux utilisateurs à l’aide de la nouvelle fonctionnalité de contrôle d’accès basé sur un rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="a7f54-105">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="a7f54-106">Lorsque vous installez Lync Server, un certain nombre de rôles RBAC sont créés pour vous.</span><span class="sxs-lookup"><span data-stu-id="a7f54-106">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="a7f54-107">Ces rôles correspondent à des groupes de sécurité universels dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7f54-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="a7f54-108">Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk figurant dans le conteneur utilisateurs dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7f54-108">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="a7f54-109">En outre, chaque rôle RBAC est associé à un ensemble d’applets de commande Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7f54-109">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a7f54-110">Ces applets de commande représentent les tâches qui peuvent être effectuées par les utilisateurs auxquels le rôle RBAC donné a été attribué.</span><span class="sxs-lookup"><span data-stu-id="a7f54-110">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="a7f54-111">Par exemple, les applets de commande Lock-CsClientPin et UnlockCsClientPin ont été affectées au rôle CsHelpDesk.</span><span class="sxs-lookup"><span data-stu-id="a7f54-111">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="a7f54-112">Cela signifie que les utilisateurs auxquels le rôle CsHelpDesk a été attribué peuvent verrouiller et déverrouiller les numéros de code confidentiel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7f54-112">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="a7f54-113">Cependant, l’applet de commande New-CsVoicePolicy n’a pas été affectée au rôle CsHelpDesk.</span><span class="sxs-lookup"><span data-stu-id="a7f54-113">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="a7f54-114">Par conséquent, les utilisateurs auxquels le rôle CsHelpDesk a été affecté ne peuvent pas créer de nouvelles stratégies de voix.</span><span class="sxs-lookup"><span data-stu-id="a7f54-114">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="a7f54-115">Affichage des informations sur les rôles RBAC</span><span class="sxs-lookup"><span data-stu-id="a7f54-115">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="a7f54-116">Vous pouvez récupérer des informations de base sur vos rôles RBAC en exécutant la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a7f54-116">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="a7f54-117">N’oubliez pas que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) a un mappage direct à un groupe de sécurité se trouvant dans le conteneur utilisateurs des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7f54-117">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="a7f54-118">Pour obtenir une liste des applets de commande qui sont affectées à un rôle, utilisez une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="a7f54-118">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="a7f54-119">Attribution d’un rôle RBAC à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a7f54-119">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="a7f54-120">Pour attribuer un rôle RBAC à un utilisateur, vous devez ajouter cet utilisateur au groupe de sécurité Active Directory approprié.</span><span class="sxs-lookup"><span data-stu-id="a7f54-120">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="a7f54-121">Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a7f54-121">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="a7f54-122">Pour cela, effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="a7f54-122">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="a7f54-123">**Pour affecter un utilisateur à un groupe de sécurité**</span><span class="sxs-lookup"><span data-stu-id="a7f54-123">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="a7f54-124">En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.</span><span class="sxs-lookup"><span data-stu-id="a7f54-124">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="a7f54-125">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a7f54-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="a7f54-126">Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a7f54-126">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="a7f54-127">Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a7f54-127">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="a7f54-128">Dans la boîte de dialogue **Propriétés**, sous l’onglet **Membres**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a7f54-128">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="a7f54-129">Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes**, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe (par exemple, **Ken Myer**) dans la zone **Entrer les noms des objets à sélectionner**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7f54-129">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="a7f54-130">Dans la boîte de dialogue **Propriétés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7f54-130">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="a7f54-131">Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de commande [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment), en indiquant le nom SamAccountName (nom de connexion Active Directory) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7f54-131">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="a7f54-132">Par exemple, exécutez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a7f54-132">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

