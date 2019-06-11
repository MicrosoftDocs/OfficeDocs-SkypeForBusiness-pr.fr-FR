---
title: 'Lync Server 2013 : Déplacement d’utilisateurs vers Voix Entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="69298-102">Déplacement d’utilisateurs vers Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69298-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69298-103">_**Dernière modification de la rubrique:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="69298-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="69298-104">Si vous déplacez les utilisateurs à partir d’une infrastructure de téléphonie PBX existante vers Enterprise Voice, le processus de déploiement comporte certaines étapes qui ne font pas partie du processus de planification déjà décrit dans [planification pour Enterprise Voice dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="69298-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="69298-105">Pour plus d’informations sur la migration des utilisateurs d’un déploiement voix entreprise antérieur, voir les documents de migration inclus dans votre support d’installation.</span><span class="sxs-lookup"><span data-stu-id="69298-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="69298-106">Le processus de déplacement des utilisateurs à partir d’une infrastructure de téléphonie existante vers Enterprise Voice comprend les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="69298-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="69298-107">Spécifiez les numéros de téléphone principaux.</span><span class="sxs-lookup"><span data-stu-id="69298-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="69298-108">activez les utilisateurs pour Voix Entreprise ;</span><span class="sxs-lookup"><span data-stu-id="69298-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="69298-109">Préparer les plans de numérotation pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="69298-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="69298-110">Planifiez les stratégies de voix des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="69298-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="69298-111">Planifiez les itinéraires d’appels.</span><span class="sxs-lookup"><span data-stu-id="69298-111">Plan call routes.</span></span>

6.  <span data-ttu-id="69298-112">Configurer le protocole PBX ou SIP Trunk pour rediriger les appels pour les utilisateurs activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="69298-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="69298-113">Déplacer les utilisateurs vers la messagerie unifiée Exchange (MU) (recommandée)</span><span class="sxs-lookup"><span data-stu-id="69298-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="69298-114">Cette rubrique décrit la planification nécessaire pour chacune de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="69298-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="69298-115">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="69298-115">Step 1.</span></span> <span data-ttu-id="69298-116">Désigner les numéros de téléphone principaux</span><span class="sxs-lookup"><span data-stu-id="69298-116">Designate primary phone numbers</span></span>

<span data-ttu-id="69298-117">Voix entreprise intègre la voix à d’autres médias de messagerie, de telle sorte qu’une fois qu’un appel entrant arrive sur le serveur, le serveur mappe le numéro à l’URI SIP de l’utilisateur, puis dévie l’appel à tous les points de terminaison client associés à cet URI SIP.</span><span class="sxs-lookup"><span data-stu-id="69298-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="69298-118">Ce processus nécessite que chaque utilisateur soit associé à un numéro de téléphone principal.</span><span class="sxs-lookup"><span data-stu-id="69298-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="69298-119">Le numéro de téléphone principal doit être:</span><span class="sxs-lookup"><span data-stu-id="69298-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="69298-120">Globalement unique ou, dans le cas d’extensions internes, uniques au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="69298-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="69298-121">Détenu et routable au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="69298-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="69298-122">Les numéros personnels ne doivent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="69298-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="69298-123">Les utilisateurs d’entreprise peuvent avoir au moins deux numéros de téléphone répertoriés dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="69298-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="69298-124">Tous les numéros de téléphone associés à un utilisateur particulier peuvent être affichés ou modifiés dans la feuille de propriétés de cet utilisateur dans le composant logiciel enfichable utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="69298-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="69298-125">Le champ **numéro de téléphone** de l’onglet **général** de la boîte de dialogue des propriétés de l' **utilisateur** doit contenir le numéro de poste principal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69298-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="69298-126">Ce numéro sera généralement désigné comme numéro de téléphone principal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69298-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="69298-127">Certains utilisateurs ont des exigences spéciales (par exemple, un dirigeant qui veut que tous les appels entrants soient acheminés par l’intermédiaire d’un assistant administratif), mais ces exceptions doivent être limitées uniquement aux personnes qui ont besoin d’être claires et critiques.</span><span class="sxs-lookup"><span data-stu-id="69298-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="69298-128">Après avoir choisi un numéro principal, il doit être:</span><span class="sxs-lookup"><span data-stu-id="69298-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="69298-129">Normalisé au format E. 164, dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="69298-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="69298-130">Copie dans l’attribut Active Directory **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="69298-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69298-131"><STRONG>Coexistence avec le contrôle d’appel distant (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="69298-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="69298-132">Le RCC est la possibilité d’utiliser Lync Server pour surveiller et contrôler un téléphone de bureau PBX.</span><span class="sxs-lookup"><span data-stu-id="69298-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="69298-133">Le contrôle est routé par le biais du serveur, qui sert de passerelle au PBX.</span><span class="sxs-lookup"><span data-stu-id="69298-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="69298-134">Même si vous ne pouvez pas configurer un utilisateur pour les utilisateurs RCC et voix entreprise, le paramètre URI de ligne désigne le numéro de téléphone principal d’un utilisateur dans chaque cas.</span><span class="sxs-lookup"><span data-stu-id="69298-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="69298-135">Si vous voulez que les utilisateurs sélectionnés disposent d’une infrastructure PBX existante, vous pouvez intégrer la voix entreprise de façon incrémentielle au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="69298-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="69298-136">Pour plus d’informations sur ce scénario de déploiement, voir <A href="lync-server-2013-direct-sip-deployment-options.md">options de déploiement SIP directes dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="69298-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="69298-137">Dans les versions précédentes, vous pouviez activer les fonctions RCC et voix entreprise pour un utilisateur, mais uniquement si vous avez également configuré l’utilisateur pour le double-branchement, une fonctionnalité dans laquelle un appel entrant sonne sur le téléphone PBX d’un utilisateur et sur Communicator simultanément.</span><span class="sxs-lookup"><span data-stu-id="69298-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="69298-138">Dans Lync Server 2010, le double-bifurcation n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="69298-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="69298-139">Il existe trois méthodes pour remplir l’attribut **msRTCSIP-Line** :</span><span class="sxs-lookup"><span data-stu-id="69298-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="69298-140">Serveur d’intégration d’identité Microsoft (recommandé)</span><span class="sxs-lookup"><span data-stu-id="69298-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="69298-141">Page **utilisateurs** du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="69298-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="69298-142">Lorsque de nombreux numéros de téléphone doivent être traités, un script personnalisé développé par votre organisation est le meilleur choix.</span><span class="sxs-lookup"><span data-stu-id="69298-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="69298-143">En fonction de la manière dont votre organisation représente les numéros de téléphone dans les services de domaine Active Directory (AD FS), le script risque de normaliser les numéros de téléphone principaux au format E. 164 avant de les copier dans l’attribut d' **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="69298-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="69298-144">Si votre organisation conserve tous les numéros de téléphone dans les services de domaine Active Directory (AD FS) dans un format unique et si ce format est E. 164, votre script doit uniquement écrire chaque numéro de téléphone principal dans l’attribut **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="69298-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="69298-145">Si votre organisation conserve tous les numéros de téléphone dans les services de domaine Active Directory (AD FS) dans un format unique, mais ce format n’est pas E. 164, votre script doit définir une règle de normalisation appropriée pour convertir les numéros de téléphone principal de leur format existant. pour E. 164 avant de les écrire dans l’attribut **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="69298-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="69298-146">Si votre organisation n’applique pas un format standard pour les numéros de téléphone dans les services de domaine Active Directory (AD FS), votre script doit définir des règles de normalisation appropriées pour convertir les numéros de téléphone principal de leurs différents formats vers E. 164 Compliance. écriture des numéros de téléphone principaux pour l’attribut **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="69298-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="69298-147">Votre script devra également insérer le préfixe **tel:** avant chaque numéro principal avant de l’écrire dans l’attribut **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="69298-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="69298-148">Le format attendu du numéro spécifié dans cet attribut est le suivant:</span><span class="sxs-lookup"><span data-stu-id="69298-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="69298-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="69298-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="69298-150">Tel: 5550100 (pour les extensions uniques à l’échelle de l’entreprise)</span><span class="sxs-lookup"><span data-stu-id="69298-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="69298-151">La normalisation réalisée par le service de carnet d’adresses (ABS) ne remplace pas ou n’entraîne aucune nécessité de normaliser le numéro de téléphone principal de chaque utilisateur dans les services de domaine Active Directory, car l’ABS n’a pas accès aux services de domaine Active Directory (AD DS) et par conséquent, il est impossible de copier des numéros principaux vers l’attribut <STRONG>msRTCSIP-Line</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="69298-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="69298-152">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="69298-152">Step 2.</span></span> <span data-ttu-id="69298-153">Activation des utilisateurs pour Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="69298-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="69298-154">En revanche, si vous n’avez pas besoin d’identifier les utilisateurs à activer, aucune planification spéciale n’est nécessaire pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="69298-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="69298-155">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="69298-155">Step 3.</span></span> <span data-ttu-id="69298-156">Préparer les plans de numérotation pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="69298-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="69298-157">Les utilisateurs qui sont activés pour voix entreprise ne seront pas en mesure de passer des appels vers le réseau PSTN sans utiliser de plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="69298-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="69298-158">Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="69298-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="69298-159">Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont routés vers chaque emplacement, utilisateur ou objet contact.</span><span class="sxs-lookup"><span data-stu-id="69298-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="69298-160">Pour plus d’informations sur la préparation de plans de numérotation, voir [plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="69298-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="69298-161">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="69298-161">Step 4.</span></span> <span data-ttu-id="69298-162">Planifier les stratégies de voix des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="69298-162">Plan user voice policies</span></span>

<span data-ttu-id="69298-163">Les paramètres de classe de service de l’utilisateur sur un PBX hérité, par exemple le droit de passer des appels longue distance ou internationaux depuis des téléphones d’entreprise, doivent être reconfigurés en tant que stratégies VoIP pour les utilisateurs transférés vers Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="69298-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="69298-164">Pour plus d’informations sur la planification et la création de stratégies pour Enterprise Voice, voir [stratégies vocales dans Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="69298-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="69298-165">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="69298-165">Step 5.</span></span> <span data-ttu-id="69298-166">Planifier les itinéraires des appels sortants</span><span class="sxs-lookup"><span data-stu-id="69298-166">Plan outbound call routes</span></span>

<span data-ttu-id="69298-167">Les itinéraires d’appels spécifient comment Lync Server gère les appels sortants placés par des utilisateurs d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="69298-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="69298-168">Lorsqu’un utilisateur compose un numéro, le serveur, le cas échéant, normalise la chaîne de numérotation au format E. 164 et tente de correspondre à un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="69298-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="69298-169">Si le serveur ne parvient pas à établir la correspondance, il applique la logique du routage des appels sortants en fonction du numéro.</span><span class="sxs-lookup"><span data-stu-id="69298-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="69298-170">Lors de la définition de cette logique, la dernière étape de la création d’un itinéraire d’appel nommé distinct pour chaque ensemble de numéros de téléphone de destination figurant dans chaque plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="69298-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="69298-171">Pour plus d’informations sur la planification des itinéraires d’appel, voir [itinéraires vocaux dans Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="69298-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="69298-172">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="69298-172">Step 6.</span></span> <span data-ttu-id="69298-173">Configurer le protocole PBX ou le Trunk SIP pour rediriger les appels pour les utilisateurs d’Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="69298-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="69298-174">Les utilisateurs qui étaient autrefois hébergés sur un système PBX classique ou sur une connexion SIP Trunk à un fournisseur de services de téléphonie Internet (ITSP) conservent leurs numéros de téléphone après le déplacement.</span><span class="sxs-lookup"><span data-stu-id="69298-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="69298-175">La seule obligation est qu’après le déplacement, le PBX ou le Trunk SIP doit être reconfiguré pour diriger les appels entrants des utilisateurs voix entreprise vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="69298-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="69298-176">Étape 7.</span><span class="sxs-lookup"><span data-stu-id="69298-176">Step 7.</span></span> <span data-ttu-id="69298-177">Déplacer des utilisateurs vers la messagerie unifiée Exchange (recommandé)</span><span class="sxs-lookup"><span data-stu-id="69298-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="69298-178">Le déplacement des utilisateurs vers la messagerie unifiée Exchange se compose des tâches suivantes:</span><span class="sxs-lookup"><span data-stu-id="69298-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="69298-179">Configurez la messagerie unifiée Exchange et Lync Server pour collaborer.</span><span class="sxs-lookup"><span data-stu-id="69298-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="69298-180">Permettre aux utilisateurs de répondre aux appels à la messagerie unifiée Exchange et à Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="69298-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="69298-181">Cette tâche est exécutée sur le serveur de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="69298-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="69298-182">Pour plus d’informations, reportez-vous à [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)la bibliothèque TechNet du serveur Exchange 2010 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="69298-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

