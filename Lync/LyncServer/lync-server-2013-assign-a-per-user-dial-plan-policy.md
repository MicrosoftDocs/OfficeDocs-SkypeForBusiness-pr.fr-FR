---
title: 'Lync Server 2013: affecter une stratégie de plan de numérotation par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f9bca09515daba6db7e072625d5b4a217d37cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846938"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="19a7d-102">Affecter une stratégie de plan de numérotation par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19a7d-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="19a7d-103">Pour achever la configuration de compte d’utilisateur pour les utilisateurs d’Enterprise Voice ou les utilisateurs de conférences rendez-vous, l’utilisateur doit être affecté d’un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="19a7d-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="19a7d-104">Les comptes d’utilisateurs utiliseront automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation de niveau de site lorsque vous n’affectez pas explicitement un plan de numérotation par utilisateur existant.</span><span class="sxs-lookup"><span data-stu-id="19a7d-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="19a7d-105">Si vous souhaitez utiliser le plan de numérotation global ou de numérotation de site pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="19a7d-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="19a7d-106">Pour affecter un plan de numérotation à l’aide du panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19a7d-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="19a7d-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="19a7d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="19a7d-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19a7d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19a7d-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="19a7d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="19a7d-110">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="19a7d-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="19a7d-111">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="19a7d-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="19a7d-112">Dans la table, cliquez sur le compte d’utilisateur auquel vous voulez attribuer un plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="19a7d-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="19a7d-113">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="19a7d-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="19a7d-114">Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur **voix entreprise**.</span><span class="sxs-lookup"><span data-stu-id="19a7d-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="19a7d-115">Cliquez sur **stratégie de plan**de numérotation, puis sélectionnez le plan de numérotation de votre choix.</span><span class="sxs-lookup"><span data-stu-id="19a7d-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="19a7d-116">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="19a7d-116">Click **Commit**.</span></span>

<span data-ttu-id="19a7d-117">Pour plus d’informations sur la configuration des plans de numérotation, reportez-vous à la rubrique [configuration de plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="19a7d-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="19a7d-118">Affectation d’un plan de numérotation par utilisateur à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19a7d-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="19a7d-119">Vous pouvez affecter des plans de numérotation par utilisateur avec Windows PowerShell et l’applet **de connexion Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="19a7d-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="19a7d-120">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19a7d-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="19a7d-121">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="19a7d-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="19a7d-122">Pour affecter un plan de numérotation par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="19a7d-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="19a7d-123">La commande suivante attribue le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="19a7d-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="19a7d-124">Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="19a7d-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="19a7d-125">Cette commande affecte le plan de numérotation RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="19a7d-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="19a7d-126">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="19a7d-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="19a7d-127">Pour annuler l’affectation d’un plan de numérotation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="19a7d-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="19a7d-128">La commande suivante réattribue un plan de numérotation par utilisateur précédemment attribué à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="19a7d-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="19a7d-129">Lorsque le plan de numérotation par utilisateur n’est pas affecté, Ken Myer sera automatiquement géré à l’aide du plan de numérotation globale, de son plan de numérotation de site local (s’il en existe une) ou du plan de numérotation d’étendue de service affecté à son bureau d’enregistrement ou à ma passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="19a7d-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="19a7d-130">Le plan de numérotation de l’étendue du service est prioritaire sur n’importe quel plan de numérotation de site, et un plan de numérotation est prioritaire sur le plan de numérotation global.</span><span class="sxs-lookup"><span data-stu-id="19a7d-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="19a7d-131">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="19a7d-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="19a7d-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19a7d-132">See Also</span></span>


[<span data-ttu-id="19a7d-133">Configuration des plans de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19a7d-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="19a7d-134">Comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19a7d-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

