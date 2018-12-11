---
title: Activation ou désactivation de l’accès des utilisateurs anonymes
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 35104d7d7128e76f7691a4ddf1ad9693a427eb40
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222750"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="10f82-102">Activer ou désactiver l’accès utilisateur anonyme dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="10f82-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="10f82-103">Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’un compte d’utilisateur dans des Services votre organisation de domaine Active Directory ou dans un domaine fédéré pris en charge, mais peuvent être invités à participer à une conférence sur site à distance.</span><span class="sxs-lookup"><span data-stu-id="10f82-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="10f82-104">En autorisant la participation anonyme aux réunions, vous activez les utilisateurs anonymes (autrement dit, les utilisateurs dont l’identité est vérifiée au moyen de la clé de réunion ou une conférence uniquement) à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="10f82-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="10f82-105">Permettant la participation anonyme nécessite l’activation de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="10f82-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="10f82-106">Si vous souhaitez ultérieurement à titre temporaire ou permanent empêcher l’accès des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="10f82-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="10f82-107">Utilisez la procédure de cette section pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="10f82-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="10f82-108">En autorisant l’accès utilisateur anonyme pour votre organisation, vous pouvez uniquement définir que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="10f82-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="10f82-109">Les utilisateurs anonymes ne peuvent pas participer à des réunions dans votre organisation jusqu'à ce que vous également configurez au moins une stratégie de conférence et l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="10f82-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="10f82-110">Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes aux réunions sont des utilisateurs qui sont affectés à une stratégie de conférence qui est configurée pour prendre en charge les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="10f82-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="10f82-111">Pour plus d’informations sur la configuration des stratégies de conférence pour prendre en charge d’inviter des utilisateurs anonymes, voir [Gérer les stratégies de conférence](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="10f82-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="10f82-112">Pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="10f82-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="10f82-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="10f82-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10f82-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="10f82-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="10f82-115">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="10f82-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="10f82-116">Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="10f82-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="10f82-117">Dans **Modifier la Configuration Edge accès**, effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="10f82-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="10f82-118">Pour activer l’accès utilisateur anonyme pour votre organisation, activez la case à cocher **Activer les communications avec les utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="10f82-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="10f82-119">Pour désactiver l’accès utilisateur anonyme pour votre organisation, désactivez la case à cocher **Activer les communications avec les utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="10f82-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="10f82-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="10f82-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="10f82-121">Activation ou désactivation de l’accès utilisateur anonyme à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10f82-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="10f82-122">Vous pouvez gérer l’accès utilisateur anonyme à l’aide de Windows PowerShell et l’applet de commande **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="10f82-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="10f82-123">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10f82-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="10f82-124">Pour activer l’accès utilisateur anonyme</span><span class="sxs-lookup"><span data-stu-id="10f82-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="10f82-125">Pour activer l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="10f82-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="10f82-126">Pour désactiver l’accès utilisateur anonyme</span><span class="sxs-lookup"><span data-stu-id="10f82-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="10f82-127">Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="10f82-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="10f82-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10f82-128">See Also</span></span>

[<span data-ttu-id="10f82-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="10f82-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
