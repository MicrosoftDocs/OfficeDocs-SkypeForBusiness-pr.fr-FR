---
title: 'Lync Server 2013 : affecter une stratégie de plan de numérotation par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134440"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="1d311-102">Affectation d’une stratégie de plan de numérotation par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d311-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1d311-p101">Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation au niveau du site si vous n’assignez pas de manière explicite un plan de numérotation utilisateur existant. Si vous voulez utiliser le plan de numérotation global ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="1d311-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="1d311-106">Pour affecter un plan de numérotation à l’aide du panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d311-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="1d311-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1d311-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d311-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d311-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d311-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1d311-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d311-110">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="1d311-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1d311-111">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="1d311-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="1d311-112">Dans le tableau, cliquez sur le compte d’utilisateur auquel vous voulez assigner un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="1d311-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="1d311-113">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1d311-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="1d311-114">Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1d311-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="1d311-115">Cliquez sur **Stratégie de plan de numérotation**, puis choisissez le plan de numérotation souhaité.</span><span class="sxs-lookup"><span data-stu-id="1d311-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="1d311-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1d311-116">Click **Commit**.</span></span>

<span data-ttu-id="1d311-117">Pour plus d’informations sur la configuration des plans de numérotation, voir la rubrique relative à la [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="1d311-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1d311-118">Affecter un plan de numérotation par utilisateur à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d311-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1d311-119">Vous pouvez attribuer des plans de numérotation par utilisateur avec Windows PowerShell et l’applet de commande **Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="1d311-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="1d311-120">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d311-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1d311-121">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1d311-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="1d311-122">Pour affecter un plan de numérotation par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="1d311-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="1d311-123">La commande suivante assigne le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="1d311-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="1d311-124">Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1d311-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="1d311-125">Cette commande assigne le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="1d311-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="1d311-126">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="1d311-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="1d311-127">Pour annuler l’affectation d’un plan de numérotation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="1d311-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="1d311-p105">La commande suivante annule l’assignation d’un plan de numérotation par utilisateur précédemment assigné à Ken Myer. Une fois l’assignation du plan de numérotation par utilisateur annulée, Ken Myer sera géré automatiquement à l’aide du plan de numérotation global, de son plan de numérotation de site local (s’il en existe un) ou du plan de numérotation à l’échelle du service assigné à son serveur d’inscriptions ou à sa passerelle PSTN. Un plan de numérotation à l’échelle du service est prioritaire par rapport à tout plan de numérotation de site et un plan de numérotation de site est prioritaire par rapport au plan de numérotation global.</span><span class="sxs-lookup"><span data-stu-id="1d311-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="1d311-131">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="1d311-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d311-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d311-132">See Also</span></span>


[<span data-ttu-id="1d311-133">Configuration des plans de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d311-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="1d311-134">Comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d311-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

