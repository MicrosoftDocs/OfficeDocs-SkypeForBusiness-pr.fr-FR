---
title: 'Lync Server 2013 : configuration des stratégies de contrôle d’accès des utilisateurs publics'
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
ms.openlocfilehash: a967f186d924a199b007ceba8390bf968253ec72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520411"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="1848d-102">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1848d-102">Configure policies to control public user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1848d-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="1848d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="1848d-104">La connectivité PIC (Public IM Connectivity) permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée fournis par des fournisseurs de services de messagerie instantanée publics, notamment le réseau Windows Live des services Internet, Yahoo \! et AOL.</span><span class="sxs-lookup"><span data-stu-id="1848d-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="1848d-105">Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs publics peuvent collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1848d-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="1848d-106">La connectivité de messagerie instantanée publique est une fonctionnalité ajoutée qui s’appuie sur la configuration de votre déploiement et de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1848d-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="1848d-107">Elle dépend également de la mise en service du service au niveau du fournisseur de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="1848d-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="1848d-108">Pour plus d’informations sur la façon de configurer votre déploiement pour utiliser les fournisseurs publics, voir le Guide de mise en service de la connectivité PIC (Public IM Connectivity pour Microsoft Lync Server, Office Communications Server et Live Communications Server) : [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="1848d-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="1848d-109">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="1848d-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1848d-110">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="1848d-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1848d-111">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="1848d-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="1848d-112">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="1848d-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1848d-113">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="1848d-113">has been announced.</span></span> <span data-ttu-id="1848d-114">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1848d-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="1848d-115">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="1848d-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1848d-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="1848d-116">Messenger.</span></span> <span data-ttu-id="1848d-117">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="1848d-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="1848d-118">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="1848d-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1848d-119">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="1848d-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1848d-120">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="1848d-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1848d-121">Pour accéder au site de mise en service de la connectivité PIC de Microsoft Lync Server, utilisez le lien suivant : [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="1848d-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="1848d-122">Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, du site et des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1848d-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="1848d-123">Pour plus d’informations sur les types de stratégies que vous pouvez configurer, reportez-vous à la rubrique Configuration de la [prise en charge de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) dans la documentation de déploiement ou dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1848d-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="1848d-124">Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="1848d-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1848d-125">La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="1848d-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1848d-126">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="1848d-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="1848d-p106">Dans le cas des invitations de messagerie instantanée, la réponse dépend du logiciel client. La demande est acceptée, sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (c’est-à-dire les paramètres figurant dans les listes **Autoriser** et **Bloquer**). De plus, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés des utilisateurs qui ne figurent pas dans sa liste **Autoriser**.</span><span class="sxs-lookup"><span data-stu-id="1848d-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1848d-130">Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs publics, même si vous n’avez pas activé la fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1848d-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="1848d-131">Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1848d-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="1848d-132">Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1848d-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="1848d-133">En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="1848d-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="1848d-134">Pour plus d’informations sur la spécification des utilisateurs publics pouvant se connecter à Lync Server, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync server 2013</A> dans la documentation de déploiement ou dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1848d-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="1848d-135">Effectuez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou plusieurs fournisseurs de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="1848d-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="1848d-136">Pour configurer une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs publics</span><span class="sxs-lookup"><span data-stu-id="1848d-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="1848d-137">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1848d-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1848d-138">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1848d-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1848d-139">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1848d-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1848d-140">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="1848d-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1848d-141">Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1848d-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1848d-142">Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs publics, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1848d-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="1848d-p109">Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1848d-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="1848d-p110">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui autorise les communications des utilisateurs publics).</span><span class="sxs-lookup"><span data-stu-id="1848d-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="1848d-147">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1848d-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1848d-148">(Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="1848d-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="1848d-149">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1848d-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="1848d-150">Pour activer l’accès des utilisateurs publics pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs publics**.</span><span class="sxs-lookup"><span data-stu-id="1848d-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="1848d-151">Pour désactiver l’accès des utilisateurs publics pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs publics**.</span><span class="sxs-lookup"><span data-stu-id="1848d-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="1848d-152">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1848d-152">Click **Commit**.</span></span>

<span data-ttu-id="1848d-153">Pour activer l’accès des utilisateurs publics, vous devez aussi activer la prise en charge de la fédération dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1848d-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="1848d-154">Pour plus d’informations, consultez la rubrique [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1848d-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="1848d-155">S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs publics que vous souhaitez autoriser à collaborer avec les utilisateurs publics.</span><span class="sxs-lookup"><span data-stu-id="1848d-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="1848d-156">Pour plus d’informations, reportez-vous à la rubrique [affectation de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1848d-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1848d-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1848d-157">See Also</span></span>


[<span data-ttu-id="1848d-158">Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1848d-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="1848d-159">Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1848d-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

