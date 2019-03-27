---
title: Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Déterminer qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et appliquer cette stratégie de conférence à des utilisateurs spécifiques.
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881126"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="0eb65-103">Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="0eb65-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="0eb65-104">Par défaut, tous les utilisateurs ne peuvent pas d’inviter des utilisateurs anonymes à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="0eb65-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="0eb65-105">Déterminer qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et appliquer cette stratégie de conférence à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0eb65-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="0eb65-106">Pour plus d’informations sur la façon de configurer un stratégies de conférence pour prendre en charge les utilisateurs anonymes, voir [créer des stratégies de conférence de Skype pour Business Server](../../conferencing/create-policies.md) et [Managing fédération et accès externe aux Skype pour Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="0eb65-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="0eb65-107">Utilisez la procédure de cette section pour appliquer une stratégie de conférence que vous avez déjà créée à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0eb65-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="0eb65-108">Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez également activer la prise en charge pour les utilisateurs anonymes pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0eb65-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="0eb65-109">Pour plus d’informations, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0eb65-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="0eb65-110">Pour configurer une stratégie d’utilisateur pour la participation anonyme aux réunions</span><span class="sxs-lookup"><span data-stu-id="0eb65-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="0eb65-111">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0eb65-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0eb65-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="0eb65-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0eb65-113">Dans la barre de navigation de gauche, cliquez sur **conférence**, puis effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0eb65-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="0eb65-114">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis cliquez sur **stratégie de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0eb65-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="0eb65-115">Créez un nom unique dans le champ **nom** qui indique quel traite de la stratégie utilisateur (par exemple, **EnableAnonymous** pour une stratégie d’utilisateur qui permet les communications avec les utilisateurs anonymes).</span><span class="sxs-lookup"><span data-stu-id="0eb65-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="0eb65-116">Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0eb65-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="0eb65-117">Dans la boîte de dialogue **Stratégies de conférence** , activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="0eb65-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="0eb65-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0eb65-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="0eb65-119">Dans la barre de navigation de gauche, cliquez sur **utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="0eb65-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="0eb65-120">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0eb65-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="0eb65-121">Dans **Modifier les Skype pour l’utilisateur Business Server** sous **stratégie de conférence**, sélectionnez la stratégie d’utilisateur avec la configuration de l’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0eb65-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="0eb65-122">Le <STRONG> &lt;automatique&gt; </STRONG> paramètres s’appliquent les paramètres d’installation de serveur par défaut et sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="0eb65-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="0eb65-123">Pour permettre aux utilisateurs d’inviter des utilisateurs anonymes à des conférences, vous devez également activer la prise en charge pour les utilisateurs anonymes dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0eb65-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="0eb65-124">Pour plus d’informations, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0eb65-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

