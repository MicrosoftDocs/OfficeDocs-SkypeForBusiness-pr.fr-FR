---
title: 'Lync Server 2013 : Délégation du contrôle administratif de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2acecec7a4b6543bb5dd22720af7a3f9aab62137
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="8011b-102">Délégation du contrôle administratif de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8011b-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8011b-103">_**Dernière modification de la rubrique:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8011b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8011b-104">Dans Lync Server 2013, les tâches d’administration sont déléguées aux utilisateurs à l’aide de la nouvelle fonctionnalité de contrôle d’accès basée sur les rôles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8011b-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="8011b-105">Lorsque vous installez Lync Server, un certain nombre de rôles RBAC sont créés pour vous.</span><span class="sxs-lookup"><span data-stu-id="8011b-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="8011b-106">Ces rôles correspondent aux groupes de sécurité universelles dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8011b-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="8011b-107">Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk figurant dans le conteneur utilisateurs dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="8011b-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="8011b-108">Par ailleurs, chaque rôle RBAC est associé à un ensemble de cmdlets Windows PowerShell Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8011b-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="8011b-109">Ces applets de contrôle représentent les tâches qui peuvent être effectuées par les utilisateurs auxquels le rôle RBAC donné a été attribué.</span><span class="sxs-lookup"><span data-stu-id="8011b-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="8011b-110">Par exemple, le rôle CsHelpDesk a été affecté aux cmdlets Lock-CsClientPin et UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="8011b-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="8011b-111">Cela signifie que les utilisateurs qui ont été attribués au rôle CsHelpDesk peuvent verrouiller ou déverrouiller des numéros de broche d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8011b-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="8011b-112">Toutefois, le rôle CsHelpDesk n’a pas été affecté à l’applet de nouvelle applet de nouveau CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="8011b-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="8011b-113">Cela signifie que les utilisateurs qui ont été affectés au rôle CsHelpDesk ne peuvent pas créer de nouvelles stratégies vocales.</span><span class="sxs-lookup"><span data-stu-id="8011b-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="8011b-114">Affichage d’informations sur les rôles RBAC</span><span class="sxs-lookup"><span data-stu-id="8011b-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="8011b-115">Vous pouvez récupérer des informations de base sur vos rôles RBAC en exécutant la commande suivante à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8011b-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="8011b-116">Gardez à l’esprit que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) est associée à un groupe de sécurité figurant dans le conteneur utilisateurs dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="8011b-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="8011b-117">Pour afficher une liste des applets de commande attribuées à un rôle, utilisez une commande semblable à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="8011b-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="8011b-118">Attribution d’un rôle RBAC à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="8011b-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="8011b-119">Pour attribuer un rôle RBAC à un utilisateur, vous devez l’ajouter au groupe de sécurité Active Directory approprié.</span><span class="sxs-lookup"><span data-stu-id="8011b-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="8011b-120">Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8011b-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="8011b-121">Pour cela, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="8011b-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="8011b-122">**Pour affecter un utilisateur à un groupe de sécurité**</span><span class="sxs-lookup"><span data-stu-id="8011b-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="8011b-123">À l’aide d’un compte qui dispose des autorisations nécessaires pour modifier l’appartenance à un groupe Active Directory, connectez-vous à un ordinateur sur lequel sont installés les utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8011b-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="8011b-124">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8011b-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="8011b-125">Dans utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine, puis cliquez sur le conteneur **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="8011b-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="8011b-126">Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8011b-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="8011b-127">Dans la boîte de dialogue **Propriétés** , sous l’onglet **membres** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8011b-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="8011b-128">Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes** , entrez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe (par exemple, **Ken Myer**) dans la zone **Entrez les noms des objets à sélectionner** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8011b-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="8011b-129">Dans la boîte de dialogue **Propriétés** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8011b-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="8011b-130">Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de contrôle [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , en transmettant l’applet de contrôle sAMAccountName (nom de connexion Active Directory) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8011b-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="8011b-131">Par exemple, exécutez la commande suivante à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8011b-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

