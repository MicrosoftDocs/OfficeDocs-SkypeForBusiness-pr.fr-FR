---
title: Activation ou désactivation de l’accès des utilisateurs anonymes
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280270"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="fb5f3-102">Activation ou désactivation de l’accès anonyme aux utilisateurs dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="fb5f3-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="fb5f3-103">Les utilisateurs anonymes sont des utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou qui sont invités à participer à distance dans une conférence locale.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="fb5f3-104">La participation anonyme aux réunions vous permet d’activer les utilisateurs anonymes (c’est-à-dire les utilisateurs dont l’identité est vérifiée uniquement via la réunion ou la clé de conférence) pour participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="fb5f3-105">L’activation de la participation anonyme exige de l’activer pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="fb5f3-106">Si vous souhaitez suspendre temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="fb5f3-107">Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation, suivez la procédure décrite dans cette section.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="fb5f3-108">L’activation de l’accès anonyme aux utilisateurs de votre organisation consiste uniquement à indiquer que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="fb5f3-109">Les utilisateurs anonymes ne peuvent pas participer à une réunion au sein de votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="fb5f3-110">Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est affectée et qui est configurée pour prendre en charge les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="fb5f3-111">Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge de l’invitation d’utilisateurs anonymes, voir [gérer les stratégies de conférence](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fb5f3-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="fb5f3-112">Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="fb5f3-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="fb5f3-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb5f3-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fb5f3-115">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis cliquez sur **configuration d’Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="fb5f3-116">Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fb5f3-117">Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="fb5f3-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="fb5f3-118">Pour activer l’accès anonyme aux utilisateurs de votre organisation, activez la case à cocher **activer les communications avec les utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="fb5f3-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="fb5f3-119">Pour désactiver l’accès anonyme aux utilisateurs de votre organisation, décochez la case **activer les communications avec les utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="fb5f3-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="fb5f3-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb5f3-121">Activation ou désactivation de l’accès utilisateur anonyme à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb5f3-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fb5f3-122">Vous pouvez gérer l’accès utilisateur anonyme à l’aide de Windows PowerShell et de l’applet **de connexion Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fb5f3-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="fb5f3-123">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb5f3-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="fb5f3-124">Pour autoriser l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="fb5f3-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="fb5f3-125">Pour autoriser l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true):</span><span class="sxs-lookup"><span data-stu-id="fb5f3-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="fb5f3-126">Pour désactiver l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="fb5f3-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="fb5f3-127">Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false):</span><span class="sxs-lookup"><span data-stu-id="fb5f3-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="fb5f3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb5f3-128">See Also</span></span>

[<span data-ttu-id="fb5f3-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="fb5f3-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
