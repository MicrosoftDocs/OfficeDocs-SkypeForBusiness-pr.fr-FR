---
title: 'Lync Server 2013 : Configuration des stratégies de contrôle d’accès des utilisateurs publics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="ddb4e-102">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddb4e-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddb4e-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ddb4e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ddb4e-104">La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs de services de messagerie instantanée publics, y\!compris le réseau Windows Live de services Internet, Yahoo et AOL.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="ddb4e-105">Pour contrôler si les utilisateurs publics peuvent collaborer avec des utilisateurs externes du serveur Lync, vous devez configurer une ou plusieurs stratégies d’accès aux utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="ddb4e-106">La connectivité de messagerie instantanée publique est une fonctionnalité ajoutée qui repose sur la configuration de votre déploiement et de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="ddb4e-107">Ce service dépend également de la configuration du service auprès du fournisseur de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="ddb4e-108">Pour plus d’informations sur la façon de configurer votre déploiement pour utiliser les fournisseurs publics, voir le Guide de mise en service de la connectivité PIC (Public IM Connectivity pour Microsoft Lync Server, Office Communications Server et Live Communications Server» :[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="ddb4e-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="ddb4e-109">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ddb4e-110">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="ddb4e-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ddb4e-111">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="ddb4e-112">Date de fin de vie du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="ddb4e-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ddb4e-113">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-113">has been announced.</span></span> <span data-ttu-id="ddb4e-114">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="ddb4e-115">La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="ddb4e-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ddb4e-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-116">Messenger.</span></span> <span data-ttu-id="ddb4e-117">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="ddb4e-118">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ddb4e-119">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ddb4e-120">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ddb4e-121">Pour accéder au site de mise en service de Microsoft Lync Server Public IM Connectivity, utilisez le lien suivant :[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="ddb4e-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="ddb4e-122">Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, au niveau du site et de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="ddb4e-123">Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir Configuration de la [prise en charge de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) dans la documentation de déploiement ou la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="ddb4e-124">Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="ddb4e-125">Le niveau de priorité de la stratégie de serveur Lync est défini comme suit : la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence).</span><span class="sxs-lookup"><span data-stu-id="ddb4e-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="ddb4e-126">Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="ddb4e-127">Dans le cas d’invitations de messagerie instantanée, la réponse dépend du logiciel client.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="ddb4e-128">La requête est acceptée sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (autrement dit, les paramètres du client de l’utilisateur **autorisent** et **bloquent** les listes).</span><span class="sxs-lookup"><span data-stu-id="ddb4e-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="ddb4e-129">Par ailleurs, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés de tous les utilisateurs qui ne figurent pas dans sa liste **verte** .</span><span class="sxs-lookup"><span data-stu-id="ddb4e-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ddb4e-130">Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs publics, même si vous n’avez pas activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="ddb4e-131">Toutefois, les stratégies que vous configurez ne s’appliquent que lorsque la Fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="ddb4e-132">Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="ddb4e-133">Par ailleurs, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="ddb4e-134">Pour plus d’informations sur la spécification des utilisateurs publics qui peuvent se connecter à Lync Server, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès utilisateur externe à un utilisateur compatible Lync dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="ddb4e-135">Utilisez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou de plusieurs fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="ddb4e-136">Pour configurer une stratégie d’accès externe pour prendre en charge l’accès public aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ddb4e-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="ddb4e-137">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ddb4e-138">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ddb4e-139">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ddb4e-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ddb4e-140">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ddb4e-141">Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddb4e-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ddb4e-142">Pour configurer la stratégie globale de manière à prendre en charge l’accès public aux utilisateurs, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="ddb4e-143">Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="ddb4e-144">Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="ddb4e-145">Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="ddb4e-146">Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnablePublicUsers** pour une stratégie utilisateur qui autorise les communications pour les utilisateurs publics).</span><span class="sxs-lookup"><span data-stu-id="ddb4e-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="ddb4e-147">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ddb4e-148">Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="ddb4e-149">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ddb4e-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="ddb4e-150">Pour activer l’accès public aux utilisateurs de la stratégie, activez la case à cocher **activer les communications avec les utilisateurs publics** .</span><span class="sxs-lookup"><span data-stu-id="ddb4e-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="ddb4e-151">Pour désactiver l’accès public aux utilisateurs de la stratégie, décochez la case **activer les communications avec les utilisateurs publics** .</span><span class="sxs-lookup"><span data-stu-id="ddb4e-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="ddb4e-152">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-152">Click **Commit**.</span></span>

<span data-ttu-id="ddb4e-153">Pour activer l’accès public aux utilisateurs, vous devez également activer la prise en charge de la Fédération au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="ddb4e-154">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ddb4e-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="ddb4e-155">S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs publics que vous souhaitez pouvoir collaborer avec des utilisateurs publics.</span><span class="sxs-lookup"><span data-stu-id="ddb4e-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="ddb4e-156">Pour plus d’informations, reportez-vous à la section [attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ddb4e-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ddb4e-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ddb4e-157">See Also</span></span>


[<span data-ttu-id="ddb4e-158">Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddb4e-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="ddb4e-159">Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddb4e-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

