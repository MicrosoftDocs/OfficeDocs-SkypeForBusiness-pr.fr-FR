---
title: 'Lync Server 2013 : affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes'
description: 'Lync Server 2013 : affectez des stratégies de conférence pour prendre en charge les utilisateurs anonymes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e94c3097e3e21f854e91fdee1ad0b33c3b9f53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566160"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="f2fa0-103">Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2fa0-103">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2fa0-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f2fa0-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f2fa0-105">Par défaut, aucun utilisateur ne peut inviter d’utilisateurs anonymes à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-105">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="f2fa0-106">Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-106">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="f2fa0-107">Pour plus d’informations sur la configuration des stratégies de conférence afin de prendre en charge les utilisateurs anonymes, voir [Create or Modify a Conferencing Policy in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f2fa0-107">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="f2fa0-108">Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence, que vous avez déjà créée, à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-108">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2fa0-109">Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez aussi activer la prise en charge des utilisateurs anonymes pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-109">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="f2fa0-110">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configure Policies to Control public user Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-110">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="f2fa0-111">Pour configurer une stratégie utilisateur en vue d’une participation anonyme aux réunions</span><span class="sxs-lookup"><span data-stu-id="f2fa0-111">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="f2fa0-112">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2fa0-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2fa0-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f2fa0-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2fa0-115">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2fa0-115">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="f2fa0-p104">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans le champ **Nom**, créez un nom unique indiquant ce qu’englobe la stratégie utilisateur (par exemple, **AutoriserAnonyme** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).</span><span class="sxs-lookup"><span data-stu-id="f2fa0-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="f2fa0-118">Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-118">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="f2fa0-119">Dans la boîte de dialogue **Stratégies de conférence**, activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-119">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="f2fa0-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-120">Click **Commit**.</span></span>

6.  <span data-ttu-id="f2fa0-121">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-121">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="f2fa0-122">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-122">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="f2fa0-123">Dans **Modifier l’utilisateur Lync Server**, sous **Stratégie de conférence**, sélectionnez la stratégie utilisateur spécifiant la configuration d’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-123">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2fa0-124">Les paramètres <STRONG> &lt; automatiques &gt; </STRONG> appliquent les paramètres d’installation du serveur par défaut et sont appliqués automatiquement par le serveur.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-124">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="f2fa0-125">Pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences, vous devez aussi activer la prise en charge des utilisateurs anonymes dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-125">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="f2fa0-126">Pour plus d’informations, voir [configure Policies to Control public user Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f2fa0-126">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

