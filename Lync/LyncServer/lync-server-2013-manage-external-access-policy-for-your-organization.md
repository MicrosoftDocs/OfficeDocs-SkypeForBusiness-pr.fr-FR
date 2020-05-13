---
title: 'Lync Server 2013 : gestion de la stratégie d’accès externe pour votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afc2b1599551cfc3b7ee7341e441946610166ba0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="ab2ec-102">Gérer la stratégie d’accès externe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab2ec-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ab2ec-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ab2ec-104">Une fois que vous avez déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externes qui seront pris en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="ab2ec-p101">Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge. Les étendues de stratégies suivantes sont disponibles à des fins de création et de configuration. Par défaut, la stratégie globale est créée mais elle ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="ab2ec-109">**Stratégie globale**   la stratégie globale est créée lorsque vous déployez vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="ab2ec-110">Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="ab2ec-111">Pour prendre en charge l’accès utilisateur externe au niveau global, vous devez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="ab2ec-112">La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="ab2ec-113">Si vous supprimez la stratégie globale, vous ne la supprimez pas.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="ab2ec-114">Au lieu de cela, vous la réinitialisez au paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="ab2ec-115">**Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="ab2ec-116">La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="ab2ec-117">Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="ab2ec-118">Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur qui supplante la configuration de la stratégie de site.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="ab2ec-119">**Stratégie d’utilisateur**   Vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="ab2ec-120">La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="ab2ec-121">Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="ab2ec-122">Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ab2ec-p105">Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-p105">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level. Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="ab2ec-126">Ces options incluent les types d’accès externe suivants :</span><span class="sxs-lookup"><span data-stu-id="ab2ec-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="ab2ec-127">**Activer les communications avec les utilisateurs fédérés**   Activez cette option si vous voulez assurer la prise en charge de l’accès des utilisateurs aux domaines partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="ab2ec-128">Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés comme Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="ab2ec-129">Si vous choisissez ce paramètre, vous pouvez sélectionner l’option autorisant les communications avec les domaines fédérés XMPP.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="ab2ec-p107">Éventuellement, vous pouvez sélectionner **Autoriser les communications avec des partenaires fédérés XMPP** si vous sélectionnez au préalable **Autoriser les communications avec des utilisateurs fédérés**. La fédération XMPP est une fédération avec les organisations qui utilisent le protocole XMPP (Extensible Messaging And Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="ab2ec-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab2ec-132">Si vous activez la Fédération XMPP, vous devez également choisir de déployer la <STRONG>Fédération XMPP</STRONG> dans la section Configuration des pools de serveurs Edge du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="ab2ec-133">La configuration de la Fédération XMPP consiste à déployer un proxy XMPP sur le serveur Edge et une passerelle XMPP sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="ab2ec-134">**Activer les communications avec des utilisateurs**     distants Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, puissent se connecter à Lync Server via Internet.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="ab2ec-135">**Activer les communications avec des utilisateurs publics**     Activez cette option si vous souhaitez que les utilisateurs internes soient en mesure de communiquer avec les contacts des fournisseurs de messagerie instantanée publics, tels que ceux fournis par Windows Live, Yahoo \! et America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="ab2ec-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="ab2ec-136">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ab2ec-137">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ab2ec-138">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="ab2ec-139">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="ab2ec-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ab2ec-140">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-140">has been announced.</span></span> <span data-ttu-id="ab2ec-141">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ab2ec-142">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="ab2ec-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ab2ec-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-143">Messenger.</span></span> <span data-ttu-id="ab2ec-144">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ab2ec-145">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ab2ec-146">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ab2ec-147">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="ab2ec-148">En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous devez aussi configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs externes dans votre organisation avant que tout type d’accès des utilisateurs externes ne soit mis à la disposition des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="ab2ec-149">Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ab2ec-150">**Pour afficher les stratégies d’accès externe à l’aide des applets de commande Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ab2ec-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="ab2ec-151">Vous pouvez afficher les stratégies d’accès externe à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ab2ec-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="ab2ec-152">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab2ec-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ab2ec-153">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ab2ec-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="ab2ec-154">Pour afficher des informations sur l’ensemble de vos stratégies d’accès externes, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="ab2ec-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="ab2ec-155">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="ab2ec-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="ab2ec-156">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ab2ec-156">In This Section</span></span>

  - [<span data-ttu-id="ab2ec-157">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="ab2ec-158">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="ab2ec-159">Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="ab2ec-160">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="ab2ec-161">Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="ab2ec-162">Réinitialisation ou suppression des stratégies d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2ec-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

