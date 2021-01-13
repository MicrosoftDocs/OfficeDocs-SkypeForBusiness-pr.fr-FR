---
title: Activation ou désactivation de l’accès utilisateur anonyme
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 7e828745810bd49f9b8f3ea9e7bee1d023e4fc67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817444"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="2881d-102">Activer ou désactiver l’accès des utilisateurs anonymes dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2881d-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="2881d-103">Les utilisateurs anonymes sont des utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais peuvent être invités à participer à distance à une conférence sur site.</span><span class="sxs-lookup"><span data-stu-id="2881d-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="2881d-104">En permettant la participation anonyme aux réunions, vous autorisez les utilisateurs anonymes (c’est-à-dire, les utilisateurs dont l’identité est vérifiée uniquement par le biais de la clé de réunion ou de conférence) à participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="2881d-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="2881d-105">L’activation de la participation anonyme nécessite son activation pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2881d-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="2881d-106">Si vous souhaitez par la suite empêcher temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2881d-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="2881d-107">Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2881d-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="2881d-108">En activant l’accès des utilisateurs anonymes pour votre organisation, vous spécifiez uniquement que vos serveurs exécutant le service Edge d’accès permettent aux utilisateurs anonymes de prendre en charge l’accès.</span><span class="sxs-lookup"><span data-stu-id="2881d-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="2881d-109">Les utilisateurs anonymes ne peuvent participer à aucune réunion de votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’avez appliquée à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2881d-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="2881d-110">Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont ceux qui se voit attribuer une stratégie de conférence configurée pour prendre en charge les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="2881d-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="2881d-111">Pour plus d’informations sur la configuration des stratégies de conférence pour prendre en charge l’invitation d’utilisateurs anonymes, voir [Gérer les stratégies de conférence.](../../conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2881d-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="2881d-112">Pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="2881d-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="2881d-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2881d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2881d-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2881d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2881d-115">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="2881d-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="2881d-116">Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="2881d-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2881d-117">Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2881d-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="2881d-118">Pour activer l’accès des utilisateurs anonymes pour votre organisation, activez la case à cocher Activer les communications avec **les utilisateurs** anonymes.</span><span class="sxs-lookup"><span data-stu-id="2881d-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="2881d-119">Pour désactiver l’accès des utilisateurs anonymes pour votre organisation, **désactivez** la case à cocher Activer les communications avec les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="2881d-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="2881d-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2881d-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2881d-121">Activation ou désactivation de l’accès des utilisateurs anonymes à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="2881d-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2881d-122">Vous pouvez gérer l’accès des utilisateurs anonymes à l’Windows PowerShell et à l’aide de l’cmdlet **Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="2881d-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="2881d-123">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2881d-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="2881d-124">Pour activer l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="2881d-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="2881d-125">Pour activer l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="2881d-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="2881d-126">Pour désactiver l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="2881d-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="2881d-127">Pour désactiver l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="2881d-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="2881d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2881d-128">See Also</span></span>

[<span data-ttu-id="2881d-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2881d-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
