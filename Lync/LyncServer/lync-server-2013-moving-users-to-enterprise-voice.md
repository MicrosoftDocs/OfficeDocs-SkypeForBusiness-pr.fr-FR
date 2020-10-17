---
title: 'Lync Server 2013 : transfert d’utilisateurs vers voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dfd2507f57265b53beea6f84d07760d35abe6e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507051"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d39f3-102">Transfert d’utilisateurs vers voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d39f3-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d39f3-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d39f3-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d39f3-104">Si vous déplacez des utilisateurs d’une infrastructure de téléphonie PBX existante vers voix entreprise, le processus de déploiement inclut certaines étapes qui ne font pas partie du processus de planification déjà décrit dans [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="d39f3-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="d39f3-105">Pour plus d’informations sur la migration des utilisateurs d’un déploiement antérieur de Voix Entreprise, voir les documents de migration inclus dans votre support d’installation.</span><span class="sxs-lookup"><span data-stu-id="d39f3-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="d39f3-106">Le processus de déplacement d’utilisateurs à partir d’une infrastructure téléphonique existante vers Voix Enterprise comprend les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d39f3-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="d39f3-107">Indiquer les numéros de téléphone principaux.</span><span class="sxs-lookup"><span data-stu-id="d39f3-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="d39f3-108">activez les utilisateurs pour Voix Entreprise ;</span><span class="sxs-lookup"><span data-stu-id="d39f3-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="d39f3-109">Préparer les plans de numérotation des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d39f3-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="d39f3-110">Planifier des stratégies de voix utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d39f3-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="d39f3-111">Planifier des itinéraires téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="d39f3-111">Plan call routes.</span></span>

6.  <span data-ttu-id="d39f3-112">Configurer le système PBX ou la jonction SIP pour rediriger les appels destinés aux utilisateurs activés pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d39f3-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="d39f3-113">Déplacez les utilisateurs vers la messagerie unifiée Exchange (messagerie unifiée) (recommandé).</span><span class="sxs-lookup"><span data-stu-id="d39f3-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="d39f3-114">Cette rubrique décrit la planification nécessaire à chacune de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="d39f3-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="d39f3-p102">Étape 1 : indiquer les numéros de téléphone principaux</span><span class="sxs-lookup"><span data-stu-id="d39f3-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="d39f3-p103">Voix Entreprise intègre la voix à d’autres médias de messagerie ; par exemple, lorsqu’un appel entrant arrive sur le serveur, celui-ci mappe le numéro sur l’URI SIP de l’utilisateur, puis dirige l’appel vers tous les systèmes d’extrémité clients associés à cet URI SIP. Ce processus requiert que chaque utilisateur soit associé à un numéro de téléphone principal.</span><span class="sxs-lookup"><span data-stu-id="d39f3-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="d39f3-119">Un numéro de téléphone principal doit :</span><span class="sxs-lookup"><span data-stu-id="d39f3-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="d39f3-120">être globalement unique ou, dans le cas de numéros de postes internes, unique dans l’entreprise ;</span><span class="sxs-lookup"><span data-stu-id="d39f3-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="d39f3-p104">appartenir à l’entreprise et y être routable. Les numéros personnels ne doivent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="d39f3-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="d39f3-123">Les utilisateurs d’entreprise peuvent avoir au moins deux numéros de téléphone dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d39f3-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="d39f3-124">Tous les numéros de téléphone associés à un utilisateur particulier peuvent être affichés ou modifiés dans la feuille de propriétés de cet utilisateur, dans le composant logiciel enfichable Utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d39f3-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="d39f3-p106">La zone **Numéro de téléphone** située sous l’onglet **Général** de la boîte de dialogue **Propriétés de l’utilisateur** doit contenir le numéro professionnel principal de l’utilisateur. Ce numéro est habituellement indiqué comme numéro de téléphone principal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d39f3-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="d39f3-127">Certains utilisateurs peuvent avoir des exigences particulières (par exemple, un cadre qui veut que tous les appels entrants soient routés par le biais d’un assistant administratif), mais de telles exceptions doivent se limiter à des cas où le besoin est précis et essentiel.</span><span class="sxs-lookup"><span data-stu-id="d39f3-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="d39f3-128">Une fois qu’un numéro principal est choisi, il doit être :</span><span class="sxs-lookup"><span data-stu-id="d39f3-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="d39f3-129">normalisé au format E.164, si possible ;</span><span class="sxs-lookup"><span data-stu-id="d39f3-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="d39f3-130">copié dans l’attribut Active Directory **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="d39f3-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d39f3-131"><STRONG>Coexistence avec le contrôle d’appel distant</STRONG></span><span class="sxs-lookup"><span data-stu-id="d39f3-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="d39f3-132">Le RCC est la possibilité d’utiliser Lync Server pour surveiller et contrôler un téléphone PBX de bureau.</span><span class="sxs-lookup"><span data-stu-id="d39f3-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="d39f3-133">Le contrôle est routé par le serveur, qui joue le rôle de passerelle vers le système PBX.</span><span class="sxs-lookup"><span data-stu-id="d39f3-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="d39f3-134">Bien que vous ne puissiez pas configurer un utilisateur à la fois pour le contrôle d’appel distant et Voix Entreprise, le paramètre URI de ligne spécifie un numéro de téléphone principal de l’utilisateur dans un cas comme dans l’autre.</span><span class="sxs-lookup"><span data-stu-id="d39f3-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="d39f3-135">Si vous disposez d’une infrastructure PBX existante et que vous voulez que certains utilisateurs sélectionnés continuent à l’utiliser, vous pouvez introduire Voix Entreprise de manière incrémentielle dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d39f3-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="d39f3-136">Pour plus d’informations sur ce scénario de déploiement, voir <A href="lync-server-2013-direct-sip-deployment-options.md">options de déploiement SIP direct dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="d39f3-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="d39f3-137">Dans les versions précédentes, vous pouviez activer le RCC et la voix entreprise pour un utilisateur, mais seulement si vous avez également configuré l’utilisateur pour la double bifurcation, une fonctionnalité dans laquelle un appel entrant sonnera simultanément sur le téléphone PBX d’un utilisateur et sur Communicator.</span><span class="sxs-lookup"><span data-stu-id="d39f3-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="d39f3-138">Dans Lync Server 2010, la double interplication n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d39f3-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="d39f3-139">Il existe trois façons de renseigner l’attribut **msRTCSIP-line** :</span><span class="sxs-lookup"><span data-stu-id="d39f3-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="d39f3-140">serveur MIIS (Microsoft Identity Integration Server) (recommandé) ;</span><span class="sxs-lookup"><span data-stu-id="d39f3-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="d39f3-141">Page **utilisateurs** dans le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="d39f3-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="d39f3-142">Lorsqu’un grand nombre de numéros de téléphone doivent être traités, un script personnalisé développé par votre organisation est le meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="d39f3-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="d39f3-143">En fonction de la façon dont votre organisation affiche les numéros de téléphone dans les services de domaine Active Directory, le script devra peut-être normaliser les numéros de téléphone principaux au format E.164 avant de les copier dans l’attribut **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="d39f3-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="d39f3-144">Si votre organisation gère tous les numéros de téléphone dans les services de domaine Active Directory sous un seul format et si ce format est E.164, il suffit que votre script écrive chaque numéro de téléphone principal dans l’attribut **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="d39f3-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="d39f3-145">Si votre organisation gère tous les numéros de téléphone dans les services de domaine Active Directory sous un seul format, mais que ce format n’est pas E.164, votre script doit définir une règle de normalisation appropriée pour convertir les numéros de téléphone principaux sous leur format existant au format E.164 avant de les écrire dans l’attribut **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="d39f3-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="d39f3-146">Si votre organisation n’applique pas de format standard pour les numéros de téléphone dans les services de domaine Active Directory, votre script doit définir des règles de normalisation appropriées pour convertir les numéros de téléphone principaux au format E.164 avant de les écrire dans l’attribut **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="d39f3-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="d39f3-147">Votre script doit également insérer le préfixe \*\*Tel: \*\* avant chaque numéro principal avant de l’écrire dans l’attribut **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="d39f3-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="d39f3-148">Le format attendu du numéro spécifié dans cet attribut est :</span><span class="sxs-lookup"><span data-stu-id="d39f3-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="d39f3-149">Tél : + 14255550100 ; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="d39f3-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="d39f3-150">Tel:5550100 (pour les postes uniques à l’échelle de l’entreprise)</span><span class="sxs-lookup"><span data-stu-id="d39f3-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d39f3-151">La normalisation effectuée par le Service de carnet d’adresses ne remplace, ni n’élimine le besoin de normaliser le numéro de téléphone principal de chaque utilisateur dans les services de domaine Active Directory, car le Service de carnet d’adresses n’a pas accès à ces services et ne peut, par conséquent, pas copier les numéros principaux dans l’attribut <STRONG>msRTCSIP-line</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d39f3-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="d39f3-p111">Étape 2 : activer les utilisateurs pour Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="d39f3-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="d39f3-154">Une fois que vous avez identifié les utilisateurs à activer, aucune planification spéciale n’est requise pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="d39f3-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="d39f3-p112">Étape 3 : préparer les plans de numérotation des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d39f3-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="d39f3-p113">Les utilisateurs activés pour Voix Entreprise ne pourront pas passer d’appel sur le réseau téléphonique commuté sans la mise en place de plans de numérotation. Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels. Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact.</span><span class="sxs-lookup"><span data-stu-id="d39f3-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="d39f3-160">Pour plus d’informations sur la préparation des plans de numérotation, voir [Dial plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="d39f3-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="d39f3-161">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="d39f3-161">Step 4.</span></span> <span data-ttu-id="d39f3-162">Planifier les stratégies de voix utilisateur</span><span class="sxs-lookup"><span data-stu-id="d39f3-162">Plan user voice policies</span></span>

<span data-ttu-id="d39f3-163">Les paramètres de classe de service utilisateur du système PBX hérité, tels que l’autorisation à passer des appels longue distance ou internationaux depuis les téléphones de la société, doivent être reconfigurés en tant que stratégies VoIP pour les utilisateurs déplacés vers Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d39f3-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="d39f3-164">Pour plus d’informations sur la planification et la création de stratégies pour voix entreprise, voir [stratégies de voix dans Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d39f3-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="d39f3-165">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="d39f3-165">Step 5.</span></span> <span data-ttu-id="d39f3-166">Planifier les itinéraires d’appels sortants</span><span class="sxs-lookup"><span data-stu-id="d39f3-166">Plan outbound call routes</span></span>

<span data-ttu-id="d39f3-167">Les itinéraires d’appels définissent la façon dont Lync Server gère les appels sortants passés par des utilisateurs voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="d39f3-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="d39f3-168">Lorsqu’un utilisateur compose un numéro, le serveur, si nécessaire, normalise la chaîne de numérotation au format E.164 et tente de le mettre en correspondance avec un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="d39f3-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="d39f3-169">Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro.</span><span class="sxs-lookup"><span data-stu-id="d39f3-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="d39f3-170">Dernière étape de la définition : la logique crée un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="d39f3-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="d39f3-171">Pour plus d’informations sur la planification des itinéraires d’appels, consultez la rubrique [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="d39f3-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="d39f3-172">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="d39f3-172">Step 6.</span></span> <span data-ttu-id="d39f3-173">Configurer un PBX ou une jonction SIP pour réacheminer les appels pour les utilisateurs de voix entreprise</span><span class="sxs-lookup"><span data-stu-id="d39f3-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="d39f3-174">Les utilisateurs qui étaient auparavant hébergés sur un système PBX traditionnel ou une connexion de jonction SIP auprès d’un fournisseur de services de téléphonie Internet conservent leurs numéros de téléphone après le déplacement.</span><span class="sxs-lookup"><span data-stu-id="d39f3-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="d39f3-175">Le seul besoin est qu’après le déplacement, le PBX ou la jonction SIP doit être reconfigurée pour acheminer les appels entrants pour les utilisateurs voix entreprise vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d39f3-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="d39f3-p120">Étape 7 : déplacer des utilisateurs vers la messagerie unifiée Exchange (recommandé)</span><span class="sxs-lookup"><span data-stu-id="d39f3-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="d39f3-178">Le déplacement d’utilisateurs vers la messagerie unifiée Exchange comprend les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d39f3-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="d39f3-179">Configurez la messagerie unifiée Exchange et Lync Server pour qu’ils fonctionnent ensemble.</span><span class="sxs-lookup"><span data-stu-id="d39f3-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="d39f3-180">Activer les utilisateurs pour le répondeur automatique de la messagerie unifiée Exchange et Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="d39f3-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="d39f3-181">Cette tâche est effectuée sur le serveur de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="d39f3-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="d39f3-182">Pour plus d’informations, reportez-vous à la bibliothèque TechNet Exchange Server 2010 à l’adresse [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .</span><span class="sxs-lookup"><span data-stu-id="d39f3-182">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

