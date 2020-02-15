---
title: Affecter une stratégie d’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez configurer la Fédération SIP, l’accès des utilisateurs distants et la connectivité PIC dans le panneau de configuration de Skype entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043676"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="a2e68-103">Affecter une stratégie d’accès des utilisateurs externes à un utilisateur prenant en charge Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a2e68-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="a2e68-104">Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez configurer la Fédération SIP, l’accès des utilisateurs distants et la connectivité PIC dans le panneau de configuration de Skype entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a2e68-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="a2e68-105">Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant de pouvoir se connecter à Skype entreprise Server à partir d’un emplacement distant et collaborer avec les utilisateurs internes à partir de l’emplacement distant.</span><span class="sxs-lookup"><span data-stu-id="a2e68-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="a2e68-106">Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès d’utilisateur externe à prendre en charge, puis configurer les stratégies appropriées et d’autres options afin de contrôler son utilisation.</span><span class="sxs-lookup"><span data-stu-id="a2e68-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="a2e68-107">Pour plus d’informations, reportez-vous à la rubrique gestion de la [Fédération et de l’accès externe à Skype entreprise Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="a2e68-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="a2e68-108">La procédure de cette rubrique vous permet d’appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a2e68-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="a2e68-109">Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a2e68-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="a2e68-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a2e68-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a2e68-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a2e68-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a2e68-112">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="a2e68-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="a2e68-113">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a2e68-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a2e68-114">Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie d’accès externe**, sélectionnez la stratégie utilisateur que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="a2e68-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="a2e68-115">Les paramètres de \*\* \<>automatique\*\* appliquent les paramètres de stratégie globale ou de serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="a2e68-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a2e68-116">Affectation de stratégies d’accès externe par utilisateur à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2e68-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a2e68-117">Les stratégies d’accès externe par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet de commande Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="a2e68-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="a2e68-118">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2e68-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="a2e68-119">Pour affecter une stratégie d’accès externe par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="a2e68-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="a2e68-120">Cette commande permet d’affecter la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="a2e68-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="a2e68-121">Pour affecter une stratégie d’accès externe par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a2e68-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="a2e68-122">Cette commande permet d’affecter la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui possèdent des comptes dans l’unité d’organisation (OU) UnitedStates dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a2e68-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="a2e68-123">Pour plus d’informations sur le paramètre OU utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="a2e68-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="a2e68-124">Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur</span><span class="sxs-lookup"><span data-stu-id="a2e68-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="a2e68-p105">Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="a2e68-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="a2e68-128">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="a2e68-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


