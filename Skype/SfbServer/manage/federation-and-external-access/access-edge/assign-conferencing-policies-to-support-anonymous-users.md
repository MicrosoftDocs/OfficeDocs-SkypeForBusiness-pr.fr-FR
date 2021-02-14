---
title: Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817454"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="8476a-103">Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8476a-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="8476a-104">Par défaut, aucun utilisateur ne peut inviter d’utilisateurs anonymes à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="8476a-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="8476a-105">Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8476a-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="8476a-106">Pour plus d’informations sur la configuration d’une stratégie de conférence pour prendre en charge les utilisateurs anonymes, voir Créer des stratégies de conférence dans Skype Entreprise [Server](../../conferencing/create-policies.md) et Gestion de la fédération et de l’accès externe à [Skype Entreprise Server.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="8476a-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="8476a-107">Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence, que vous avez déjà créée, à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8476a-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="8476a-108">Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez aussi activer la prise en charge des utilisateurs anonymes pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8476a-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="8476a-109">Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des](../external-access-policies/configure-policies-to-control-public-user-access.md)utilisateurs publics dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8476a-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="8476a-110">Pour configurer une stratégie utilisateur en vue d’une participation anonyme aux réunions</span><span class="sxs-lookup"><span data-stu-id="8476a-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="8476a-111">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8476a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8476a-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8476a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8476a-113">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8476a-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="8476a-p103">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans le champ **Nom**, créez un nom unique indiquant ce qu’englobe la stratégie utilisateur (par exemple, **AutoriserAnonyme** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).</span><span class="sxs-lookup"><span data-stu-id="8476a-p103">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="8476a-116">Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8476a-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="8476a-117">Dans la boîte de dialogue **Stratégies de conférence**, activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**.</span><span class="sxs-lookup"><span data-stu-id="8476a-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="8476a-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8476a-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="8476a-119">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="8476a-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="8476a-120">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8476a-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="8476a-121">Dans **Modifier l’utilisateur Skype** Entreprise Server sous Stratégie de conférence, sélectionnez la stratégie utilisateur avec la configuration d’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur. </span><span class="sxs-lookup"><span data-stu-id="8476a-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="8476a-122">Les <STRONG> &lt; paramètres &gt; </STRONG> automatiques appliquent les paramètres d’installation du serveur par défaut et sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="8476a-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="8476a-123">Pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences, vous devez aussi activer la prise en charge des utilisateurs anonymes dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8476a-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="8476a-124">Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des](../external-access-policies/configure-policies-to-control-public-user-access.md)utilisateurs publics dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8476a-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

