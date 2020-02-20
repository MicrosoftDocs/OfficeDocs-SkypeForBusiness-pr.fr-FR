---
title: 'Lync Server 2013 : configuration des stratégies de contrôle de l’accès des utilisateurs distants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429d1751f9b9628df98c05112838715de2b249d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="32dc1-102">Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32dc1-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32dc1-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="32dc1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="32dc1-104">Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32dc1-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="32dc1-105">Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau global, du site et de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32dc1-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="32dc1-106">Les stratégies de site remplacent la stratégie globale, et les stratégies utilisateur remplacent les stratégies de site et globale.</span><span class="sxs-lookup"><span data-stu-id="32dc1-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="32dc1-107">Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir gestion de la [Fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="32dc1-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="32dc1-108">Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="32dc1-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="32dc1-109">La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="32dc1-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="32dc1-110">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="32dc1-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32dc1-111">Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs distants, même si vous n’avez pas activé l’accès des utilisateurs distants pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="32dc1-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="32dc1-112">Toutefois, les stratégies que vous configurez sont effectives uniquement quand vous activez l’accès des utilisateurs distants pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="32dc1-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="32dc1-113">Pour plus d’informations sur l’activation de l’accès des utilisateurs distants, consultez la rubrique <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="32dc1-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="32dc1-114">En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs distants, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="32dc1-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="32dc1-115">Pour plus d’informations sur la spécification des utilisateurs qui peuvent se connecter à Lync Server à partir d’emplacements distants, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès des utilisateurs externes à un utilisateur à extension Lync dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="32dc1-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="32dc1-116">Utilisez la procédure suivante pour configurer chaque stratégie d’accès externe que vous comptez utiliser pour contrôle l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="32dc1-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32dc1-117">Cette procédure décrit comment configurer une stratégie uniquement pour activer les communications avec les utilisateurs distants, mais chaque stratégie que vous configurez pour prendre en charge l’accès des utilisateurs distants peut également configurer l’accès des utilisateurs fédérés et des utilisateurs publics.</span><span class="sxs-lookup"><span data-stu-id="32dc1-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="32dc1-118">Pour plus d’informations sur la configuration des stratégies afin de prendre en charge les utilisateurs fédérés, voir <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configure Policies to Control Federated User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="32dc1-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="32dc1-119">Pour plus d’informations sur la configuration des stratégies afin de prendre en charge les utilisateurs publics, voir <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">créer ou modifier des fournisseurs fédérés SIP publics dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="32dc1-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="32dc1-120">Pour configurer une stratégie d’accès externe permettant de prendre en charge l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="32dc1-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="32dc1-121">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="32dc1-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="32dc1-122">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32dc1-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="32dc1-123">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="32dc1-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="32dc1-124">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="32dc1-125">Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32dc1-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="32dc1-126">Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs distants, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="32dc1-p105">Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="32dc1-p106">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableRemoteUsers** pour une stratégie utilisateur qui permet les communications des utilisateurs distants).</span><span class="sxs-lookup"><span data-stu-id="32dc1-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="32dc1-131">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="32dc1-132">(Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="32dc1-133">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32dc1-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="32dc1-134">Afin d’activer l’accès des utilisateurs distants pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs distants**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="32dc1-135">Afin de désactiver l’accès des utilisateurs distants pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs distants**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="32dc1-136">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="32dc1-136">Click **Commit**.</span></span>

<span data-ttu-id="32dc1-137">Pour activer l’accès des utilisateurs distants, vous devez aussi activer la prise en charge de l’accès des utilisateurs distants dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="32dc1-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="32dc1-138">Pour plus d’informations, consultez la rubrique [activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="32dc1-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="32dc1-139">S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à se connecter à distance.</span><span class="sxs-lookup"><span data-stu-id="32dc1-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="32dc1-140">Pour plus d’informations, reportez-vous à la rubrique [attribuer une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) dans la documentation de déploiement ou dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="32dc1-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

