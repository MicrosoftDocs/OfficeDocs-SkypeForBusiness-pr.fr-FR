---
title: Gérer les stratégies de PIN pour les conférences rendez-vous dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Résumé : Découvrez comment gérer les stratégies de code confidentiel pour les conférences rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: f5ffef4af17a4337fe600b2059aab1ea106235ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992291"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="1b0f2-103">Gérer les stratégies de PIN pour les conférences rendez-vous dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b0f2-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="1b0f2-104">**Résumé :** Apprenez à gérer les stratégies de code confidentiel pour la Conférence rendez-vous dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="1b0f2-105">Les utilisateurs de Skype entreprise Server qui disposent des informations d’identification AD DS (Active Directory Domain Services) de votre organisation peuvent participer à des conférences rendez-vous en utilisant un code confidentiel (PIN) pour les utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="1b0f2-106">La stratégie de code confidentiel définit le fonctionnement des codes confidentiels d’accès aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="1b0f2-p102">Si vous voulez utiliser la même stratégie de code confidentiel au sein de toute votre organisation, vous pouvez utiliser la stratégie de code confidentiel globale et la modifier, au besoin. La stratégie d’authentification par code confidentiel globale définit les règles des codes confidentiels pour les conférences rendez-vous au niveau forêt. Vous pouvez modifier la stratégie de code confidentiel globale, mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="1b0f2-110">Vous pouvez en créer une si vous voulez qu’une stratégie spécifique s’applique à un site ou à un groupe d’utilisateurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="1b0f2-111">Les stratégies de code confidentiel s’appliquent aux utilisateurs, de l’étendue la plus petite à l’étendue la plus grande.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="1b0f2-112">Si vous affectez une stratégie de code confidentiel au niveau utilisateur, ces paramètres prévalent.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="1b0f2-113">Si vous n’affectez pas de stratégie au niveau utilisateur, la stratégie de code confidentiel de niveau site s’applique, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="1b0f2-114">En l’absence de stratégie de niveau utilisateur ou site, les paramètres par défaut de la stratégie de code confidentiel globale sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="1b0f2-115">Affichage des informations sur vos stratégies de code confidentiel</span><span class="sxs-lookup"><span data-stu-id="1b0f2-115">View information about PIN policies</span></span>

<span data-ttu-id="1b0f2-116">Vous pouvez afficher des informations sur les stratégies de code confidentiel en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1b0f2-117">Afficher des informations sur les stratégies de code confidentiel en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b0f2-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1b0f2-118">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="1b0f2-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1b0f2-119">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1b0f2-120">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1b0f2-121">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à afficher, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1b0f2-122">Afficher des informations sur les stratégies de code confidentiel à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b0f2-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1b0f2-123">Pour afficher des informations sur les stratégies de code confidentiel, utilisez l’applet de commande **Get-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="1b0f2-124">Par exemple, la commande suivante retourne les informations relatives à une seule stratégie de code confidentiel dont l’identité est site:Redmond:.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="1b0f2-125">Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b0f2-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="1b0f2-126">Modification de la stratégie de code confidentiel globale</span><span class="sxs-lookup"><span data-stu-id="1b0f2-126">Modify the global PIN policy</span></span>

<span data-ttu-id="1b0f2-127">Vous pouvez modifier la stratégie de code confidentiel global à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1b0f2-128">Modification de la stratégie de code confidentiel de conférence rendez-vous globale à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b0f2-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1b0f2-129">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="1b0f2-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1b0f2-130">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1b0f2-131">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1b0f2-132">Dans la page **Stratégie de code confidentiel**, cliquez sur la stratégie **Globale**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1b0f2-p105">Dans **Modifier la stratégie de code confidentiel**, dans **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel à autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="1b0f2-p106">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est déterminé automatiquement en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est déterminé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="1b0f2-138">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion à autoriser.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="1b0f2-p107">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="1b0f2-142">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="1b0f2-p108">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant de pouvoir réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="1b0f2-p109">Pour autoriser les modèles courants de codes confidentiels, comme les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b0f2-148">Pour des raisons de sécurité, Microsoft vous recommande de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="1b0f2-149">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1b0f2-150">Modification de la stratégie de code confidentiel de conférence rendez-vous globale à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b0f2-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1b0f2-151">Pour modifier la stratégie globale de code confidentiel de conférence rendez-vous, utilisez l’applet de commande **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1b0f2-p110">La commande suivante retourne la valeur de MinPasswordLength de toutes les stratégies de code confidentiel configurées pour être utilisées dans l’organisation. Pour y parvenir, la commande appelle d’abord l’applet de commande **Get-CsPinPolicy**, sans aucun paramètre, afin de récupérer une collection de toutes les stratégies de code confidentiel existantes. Cette collection est ensuite redirigée vers l’applet de commande **Set-CsPinPolicy** qui modifie la valeur de la propriété MinPasswordLength pour chaque stratégie de la collection.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="1b0f2-155">Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b0f2-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="1b0f2-156">Création d’une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="1b0f2-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="1b0f2-157">Vous pouvez créer une stratégie d’utilisateur ou de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1b0f2-158">Création d’une stratégie d’utilisateur ou de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b0f2-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1b0f2-159">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="1b0f2-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1b0f2-160">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1b0f2-161">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1b0f2-162">Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b0f2-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="1b0f2-p111">Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="1b0f2-p112">Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="1b0f2-168">Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="1b0f2-p113">Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="1b0f2-p114">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est déterminé automatiquement en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est déterminé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="1b0f2-174">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion à autoriser.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="1b0f2-p115">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="1b0f2-178">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="1b0f2-p116">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant de pouvoir réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="1b0f2-p117">Pour autoriser les modèles courants de codes confidentiels, comme les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b0f2-184">Pour des raisons de sécurité, Microsoft vous recommande de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="1b0f2-185">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1b0f2-186">Création d’une stratégie d’utilisateur ou de code confidentiel de site à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b0f2-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1b0f2-187">Pour créer une stratégie de code confidentiel au niveau utilisateur ou site, utilisez l’applet de commande **New-CsPinPolicy**</span><span class="sxs-lookup"><span data-stu-id="1b0f2-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1b0f2-p118">La commande ci-dessous crée une stratégie de code confidentiel dont l’identité est site:Redmond. Cette commande inclut un seul paramètre facultatif, MinPasswordLength, qui permet de définir la propriété MinPasswordLength sur 7. Toutes les propriétés de stratégie restantes seront configurées au moyen des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="1b0f2-191">Pour plus d’informations, y compris une description de syntaxe complète et une liste de paramètres, voir [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b0f2-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="1b0f2-192">Modification d’une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="1b0f2-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="1b0f2-193">Vous pouvez modifier une stratégie d’un utilisateur ou d’un site Web à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1b0f2-194">Modification d’une stratégie de code confidentiel d’utilisateur ou de site à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b0f2-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1b0f2-195">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="1b0f2-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1b0f2-196">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1b0f2-197">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1b0f2-198">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1b0f2-199">Dans **Modifier la stratégie de code confidentiel**, modifiez tous les paramètres de la stratégie (à l’exception de son nom qui ne peut être modifié).</span><span class="sxs-lookup"><span data-stu-id="1b0f2-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="1b0f2-200">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1b0f2-201">Modifier une stratégie d’un utilisateur ou d’un code confidentiel de site à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b0f2-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1b0f2-202">Pour modifier la stratégie de code confidentiel de conférence rendez-vous, utilisez l’applet de commande **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1b0f2-p119">La commande ci-dessous modifie la stratégie de code confidentiel affectée au site de Redmond. Dans ce cas, la commande modifie la valeur de la propriété MinPasswordLength sur 10, ce qui signifie que les nouveaux codes confidentiels devront contenir au moins 10 chiffres.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="1b0f2-205">Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b0f2-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="1b0f2-206">Suppression d’une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="1b0f2-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="1b0f2-207">Vous pouvez supprimer une stratégie d’utilisateur ou de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1b0f2-208">Supprimer un utilisateur ou une stratégie de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b0f2-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1b0f2-209">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="1b0f2-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1b0f2-210">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1b0f2-211">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1b0f2-212">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1b0f2-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1b0f2-213">Supprimer un utilisateur ou une stratégie de code confidentiel de site à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b0f2-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1b0f2-214">Pour supprimer une stratégie de code confidentiel au niveau utilisateur ou site, utilisez l’applet de commande **New-CsPinPolicy**</span><span class="sxs-lookup"><span data-stu-id="1b0f2-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1b0f2-p120">La commande ci-dessous supprime toutes les stratégies de code confidentiel configurées dans l’étendue de site. Pour ce faire, utilisez l’applet de commande **Get-CsPinPolicy** avec le paramètre Filter pour renvoyer une collection de toutes les stratégies ayant une identité qui commence par les caractères « site: ». Cette collection est ensuite redirigée vers l’applet de commande **Remove-CsPinPolicy** qui supprime chaque stratégie de la collection :</span><span class="sxs-lookup"><span data-stu-id="1b0f2-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="1b0f2-218">Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b0f2-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

