---
title: Gérer les stratégies de code confidentiel pour les conférences rendez-vous dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Résumé : Découvrez comment gérer les stratégies de code confidentiel pour les conférences rendez-vous dans Skype pour Business Server.'
ms.openlocfilehash: 0fd6d8a3ebfaeee0c6b4b3757a7b58b8d3882d71
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013413"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="5a4c1-103">Gérer les stratégies de code confidentiel pour les conférences rendez-vous dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5a4c1-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="5a4c1-104">**Résumé :** Découvrez comment gérer les stratégies de code confidentiel pour les conférences rendez-vous dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="5a4c1-105">Skype pour les utilisateurs Business Server qui disposent d’informations d’identification des Services de domaine Active Directory (AD DS) dans votre organisation permettre participer à des conférences rendez-vous en tant qu’utilisateurs authentifiés à l’aide d’un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="5a4c1-106">La stratégie de code confidentiel définit le fonctionnement des codes confidentiels d’accès aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="5a4c1-p102">Si vous voulez utiliser la même stratégie de code confidentiel au sein de toute votre organisation, vous pouvez utiliser la stratégie de code confidentiel globale et la modifier, au besoin. La stratégie d’authentification par code confidentiel globale définit les règles des codes confidentiels pour les conférences rendez-vous au niveau forêt. Vous pouvez modifier la stratégie de code confidentiel globale, mais vous ne pouvez pas la supprimer.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="5a4c1-110">Vous pouvez en créer une si vous voulez qu’une stratégie spécifique s’applique à un site ou à un groupe d’utilisateurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="5a4c1-p103">Les stratégies de code confidentiel s’appliquent aux utilisateurs, de l’étendue la plus petite à l’étendue la plus grande. Si vous affectez une stratégie de code confidentiel au niveau utilisateur, ces paramètres prévalent. Si vous n’affectez pas de stratégie au niveau utilisateur, la stratégie de code confidentiel de niveau site s’applique, le cas échéant. En l’absence de stratégie de niveau utilisateur ou site, les paramètres par défaut de la stratégie de code confidentiel globale sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p103">PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="5a4c1-115">Affichage des informations sur vos stratégies de code confidentiel</span><span class="sxs-lookup"><span data-stu-id="5a4c1-115">View information about PIN policies</span></span>

<span data-ttu-id="5a4c1-116">Vous pouvez afficher des informations sur les stratégies de code confidentiel à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5a4c1-117">Afficher des informations sur les stratégies de code confidentiel à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="5a4c1-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5a4c1-118">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="5a4c1-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="5a4c1-119">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5a4c1-120">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5a4c1-121">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à afficher, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5a4c1-122">Afficher des informations sur les stratégies de code confidentiel à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5a4c1-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5a4c1-123">Pour afficher des informations sur les stratégies de code confidentiel, utilisez l’applet de commande **Get-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="5a4c1-124">Par exemple, la commande suivante retourne les informations relatives à une seule stratégie de code confidentiel dont l’identité est site:Redmond:.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="5a4c1-125">Pour plus d’informations, y compris une description de la syntaxe complète et une liste des paramètres, voir [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="5a4c1-126">Modification de la stratégie de code confidentiel globale</span><span class="sxs-lookup"><span data-stu-id="5a4c1-126">Modify the global PIN policy</span></span>

<span data-ttu-id="5a4c1-127">Vous pouvez modifier la stratégie de code confidentiel globale à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5a4c1-128">Modifier la rendez-vous conférence globale stratégie de code confidentiel à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="5a4c1-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5a4c1-129">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="5a4c1-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="5a4c1-130">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5a4c1-131">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5a4c1-132">Dans la page **Stratégie de code confidentiel**, cliquez sur la stratégie **Globale**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5a4c1-p105">Dans **Modifier la stratégie de code confidentiel**, dans **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel à autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="5a4c1-p106">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est déterminé automatiquement en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est déterminé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="5a4c1-138">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion à autoriser.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="5a4c1-p107">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="5a4c1-142">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="5a4c1-p108">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant de pouvoir réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="5a4c1-p109">Pour autoriser les modèles courants de codes confidentiels, comme les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a4c1-148">Pour des raisons de sécurité, Microsoft vous recommande de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="5a4c1-149">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5a4c1-150">Modifier la rendez-vous conférence globale stratégie de code confidentiel à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5a4c1-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5a4c1-151">Pour modifier la stratégie globale de code confidentiel de conférence rendez-vous, utilisez l’applet de commande **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5a4c1-p110">La commande suivante retourne la valeur de MinPasswordLength de toutes les stratégies de code confidentiel configurées pour être utilisées dans l’organisation. Pour y parvenir, la commande appelle d’abord l’applet de commande **Get-CsPinPolicy**, sans aucun paramètre, afin de récupérer une collection de toutes les stratégies de code confidentiel existantes. Cette collection est ensuite redirigée vers l’applet de commande **Set-CsPinPolicy** qui modifie la valeur de la propriété MinPasswordLength pour chaque stratégie de la collection.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="5a4c1-155">Pour plus d’informations, y compris une description de la syntaxe complète et une liste des paramètres, voir [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="5a4c1-156">Création d’une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="5a4c1-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="5a4c1-157">Vous pouvez créer un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5a4c1-158">Créer un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="5a4c1-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5a4c1-159">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="5a4c1-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="5a4c1-160">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5a4c1-161">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5a4c1-162">Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a4c1-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="5a4c1-p111">Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="5a4c1-p112">Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5a4c1-168">Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="5a4c1-p113">Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="5a4c1-p114">Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est déterminé automatiquement en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est déterminé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="5a4c1-174">Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion à autoriser.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="5a4c1-p115">Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="5a4c1-178">Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="5a4c1-p116">Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant de pouvoir réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="5a4c1-p117">Pour autoriser les modèles courants de codes confidentiels, comme les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a4c1-184">Pour des raisons de sécurité, Microsoft vous recommande de ne pas autoriser les modèles courants.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="5a4c1-185">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5a4c1-186">Créer un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5a4c1-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5a4c1-187">Pour créer une stratégie de code confidentiel au niveau utilisateur ou site, utilisez l’applet de commande **New-CsPinPolicy**</span><span class="sxs-lookup"><span data-stu-id="5a4c1-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5a4c1-p118">La commande ci-dessous crée une stratégie de code confidentiel dont l’identité est site:Redmond. Cette commande inclut un seul paramètre facultatif, MinPasswordLength, qui permet de définir la propriété MinPasswordLength sur 7. Toutes les propriétés de stratégie restantes seront configurées au moyen des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="5a4c1-191">Pour plus d’informations, y compris une description de la syntaxe complète et une liste des paramètres, voir [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="5a4c1-192">Modification d’une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="5a4c1-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="5a4c1-193">Vous pouvez modifier un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5a4c1-194">Modifier un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="5a4c1-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5a4c1-195">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="5a4c1-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="5a4c1-196">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5a4c1-197">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5a4c1-198">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5a4c1-199">Dans **Modifier la stratégie de code confidentiel**, modifiez tous les paramètres de la stratégie (à l’exception de son nom qui ne peut être modifié).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="5a4c1-200">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5a4c1-201">Modifier un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5a4c1-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5a4c1-202">Pour modifier la stratégie de code confidentiel de conférence rendez-vous, utilisez l’applet de commande **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5a4c1-p119">La commande ci-dessous modifie la stratégie de code confidentiel affectée au site de Redmond. Dans ce cas, la commande modifie la valeur de la propriété MinPasswordLength sur 10, ce qui signifie que les nouveaux codes confidentiels devront contenir au moins 10 chiffres.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="5a4c1-205">Pour plus d’informations, y compris une description de la syntaxe complète et une liste des paramètres, voir [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="5a4c1-206">Suppression d’une stratégie de code confidentiel au niveau utilisateur ou site</span><span class="sxs-lookup"><span data-stu-id="5a4c1-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="5a4c1-207">Vous pouvez supprimer un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5a4c1-208">Supprimer un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="5a4c1-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5a4c1-209">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="5a4c1-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="5a4c1-210">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5a4c1-211">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5a4c1-212">Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5a4c1-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5a4c1-213">Supprimer un utilisateur ou un site stratégie de code confidentiel à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5a4c1-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5a4c1-214">Pour supprimer une stratégie de code confidentiel au niveau utilisateur ou site, utilisez l’applet de commande **New-CsPinPolicy**</span><span class="sxs-lookup"><span data-stu-id="5a4c1-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5a4c1-p120">La commande ci-dessous supprime toutes les stratégies de code confidentiel configurées dans l’étendue de site. Pour ce faire, utilisez l’applet de commande **Get-CsPinPolicy** avec le paramètre Filter pour renvoyer une collection de toutes les stratégies ayant une identité qui commence par les caractères « site: ». Cette collection est ensuite redirigée vers l’applet de commande **Remove-CsPinPolicy** qui supprime chaque stratégie de la collection :</span><span class="sxs-lookup"><span data-stu-id="5a4c1-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="5a4c1-218">Pour plus d’informations, y compris une description de la syntaxe complète et une liste des paramètres, voir [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a4c1-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

