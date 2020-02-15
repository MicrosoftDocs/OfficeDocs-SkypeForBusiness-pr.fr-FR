---
title: 'Lync Server 2013 : itinéraires des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 350b64c15b0819813b8287bb9b40272845f3a285
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="6de12-102">Itinéraires des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6de12-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6de12-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6de12-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6de12-104">Les itinéraires d’appels définissent la façon dont Lync Server gère les appels sortants passés par des utilisateurs voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="6de12-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="6de12-105">Lorsqu’un utilisateur compose un numéro, le serveur frontal normalise la chaîne de numérotation au format E. 164, si nécessaire, et tente de la faire correspondre à un URI SIP.</span><span class="sxs-lookup"><span data-stu-id="6de12-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="6de12-106">Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro.</span><span class="sxs-lookup"><span data-stu-id="6de12-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="6de12-107">La dernière étape de la définition de cette logique consiste à créer un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="6de12-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="6de12-108">Avant de définir des itinéraires d’appels sortants, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6de12-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="6de12-109">Déployer une ou plusieurs jonctions.</span><span class="sxs-lookup"><span data-stu-id="6de12-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="6de12-110">Créer des plans de numérotation selon les besoins des sites, des personnes, ainsi que des objets Contact.</span><span class="sxs-lookup"><span data-stu-id="6de12-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="6de12-111">Créer des enregistrements d’utilisation PSTN (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="6de12-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="6de12-p102">En outre, pour activer le routage des appels sortants, vous devez créer et assigner une ou plusieurs stratégies de voix. Vous pouvez effectuer cette tâche avant ou après la définition des itinéraires des appels sortants.</span><span class="sxs-lookup"><span data-stu-id="6de12-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="6de12-114">Pour chaque itinéraire, vous devez indiquer :</span><span class="sxs-lookup"><span data-stu-id="6de12-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="6de12-115">un nom sous lequel l’itinéraire peut être facilement identifié ;</span><span class="sxs-lookup"><span data-stu-id="6de12-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="6de12-116">une description facultative pour les cas où le nom seul peut ne pas être suffisant pour décrire l’itinéraire ;</span><span class="sxs-lookup"><span data-stu-id="6de12-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="6de12-117">le modèle correspondant à l’expression régulière qui identifie les numéros de téléphone de destination auxquels l’itinéraire est appliqué, ainsi que les exceptions auxquelles le modèle ne doit pas être appliqué ;</span><span class="sxs-lookup"><span data-stu-id="6de12-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="6de12-118">une ou plusieurs jonctions que vous souhaitez assigner à l’itinéraire ;</span><span class="sxs-lookup"><span data-stu-id="6de12-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="6de12-119">les enregistrements d’utilisation PSTN dont doivent disposer les utilisateurs afin d’appeler des numéros qui correspondent à l’expression régulière du numéro de téléphone de destination.</span><span class="sxs-lookup"><span data-stu-id="6de12-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="6de12-120">Vous pouvez spécifier les itinéraires d’appels dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6de12-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="6de12-121">Ces itinéraires d’appels remplissent la table de routage du serveur, que Lync Server utilise pour acheminer les appels destinés au RTC.</span><span class="sxs-lookup"><span data-stu-id="6de12-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="6de12-122">M:N Prise en charge des jonctions</span><span class="sxs-lookup"><span data-stu-id="6de12-122">M:N Trunk Support</span></span>

<span data-ttu-id="6de12-123">Lync Server offre une grande souplesse dans la façon dont les appels sont acheminés vers le RTC.</span><span class="sxs-lookup"><span data-stu-id="6de12-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="6de12-124">Un itinéraire des communications vocales spécifie un ensemble de jonctions au PSTN qui peuvent être utilisées pour un appel vocal particulier.</span><span class="sxs-lookup"><span data-stu-id="6de12-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="6de12-125">Une jonction associe un serveur de médiation et un numéro de port avec une passerelle PSTN et un numéro de port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="6de12-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="6de12-126">Cette association logique permet d’associer un serveur de médiation à plusieurs passerelles et d’avoir plusieurs connexions à la même passerelle.</span><span class="sxs-lookup"><span data-stu-id="6de12-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="6de12-127">Lors de la définition d’un itinéraire d’appel, vous spécifiez les jonctions associées à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="6de12-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="6de12-128">Pour créer des jonctions en définissant les relations entre les serveurs de médiation et les passerelles PSTN, les PBX IP et les contrôleurs de frontière de session (SBC), utilisez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6de12-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="6de12-129">Routage à moindre coût</span><span class="sxs-lookup"><span data-stu-id="6de12-129">Least-Cost Routing</span></span>

<span data-ttu-id="6de12-p105">La possibilité de spécifier les jonctions vers lesquelles différents numéros sont routés permet de déterminer les itinéraires qui offrent les coûts les plus bas et de les mettre en œuvre en conséquence. La règle générale concernant la sélection des jonctions consiste à choisir celle possédant la passerelle la plus proche du numéro de destination, afin de réduire les coûts des appels longue distance. Par exemple, si vous vous trouvez à New York et que vous appelez un numéro à Rome, vous transférerez l’appel via le réseau IP vers la jonction avec la passerelle de votre bureau romain, ne subissant ainsi que le coût d’un appel local.</span><span class="sxs-lookup"><span data-stu-id="6de12-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="6de12-133">Voici un exemple d’utilisation du routage à moindre coût : Fabrikam décide d’autoriser les utilisateurs allemands à composer des numéros américains à l’aide de la jonction correspondante.</span><span class="sxs-lookup"><span data-stu-id="6de12-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="6de12-134">Fabrikam souhaite également configurer le système de sorte que tous les appels des utilisateurs de Lync Server américains vers l’Allemagne et les pays/régions adjacents se terminent sur la jonction avec la passerelle en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="6de12-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="6de12-135">Ce routage est économique car un appel passé de l’Allemagne vers l’Australie, par exemple, est moins onéreux qu’un appel émis des États-Unis en direction de l’Australie.</span><span class="sxs-lookup"><span data-stu-id="6de12-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="6de12-136">Traduction des chaînes de numérotation sortantes</span><span class="sxs-lookup"><span data-stu-id="6de12-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="6de12-137">Lync Server 2013, comme ses prédécesseurs immédiats, nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 dans le but d’effectuer une recherche inversée des numéros (RNL).</span><span class="sxs-lookup"><span data-stu-id="6de12-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="6de12-138">Pour les jonctions avec passerelles ou PBX (Private Branch eXchanges) qui nécessitent des numéros traduits dans les formats de numérotation locale, Lync Server 2013 vous permet de créer une ou plusieurs règles qui facilitent la manipulation du numéro appelé (URI de demande) avant de l’acheminer vers le urbain.</span><span class="sxs-lookup"><span data-stu-id="6de12-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="6de12-139">Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».</span><span class="sxs-lookup"><span data-stu-id="6de12-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="6de12-140">Avec Lync Server 2013, il est possible de créer une ou plusieurs règles qui facilitent la manipulation du numéro d’appel avant de l’acheminer vers la jonction.</span><span class="sxs-lookup"><span data-stu-id="6de12-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="6de12-141">Lors de la planification de vos jonctions qui associent différentes passerelles : port avec le serveur de médiation : paires de ports, il peut s’avérer utile de regrouper les jonctions avec des exigences de numérotation locale similaires et de réduire ainsi le nombre de règles de traduction requises et le temps nécessaire pour les écrire.</span><span class="sxs-lookup"><span data-stu-id="6de12-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="6de12-142">Configuration d’un ID d’appelant</span><span class="sxs-lookup"><span data-stu-id="6de12-142">Configuring Caller ID</span></span>

<span data-ttu-id="6de12-143">Lync Server offre un moyen de manipuler l’ID de l’appelant pour les appels sortants.</span><span class="sxs-lookup"><span data-stu-id="6de12-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="6de12-144">Par exemple, si une organisation souhaite masquer les extensions de numérotation directe des employés et les remplacer par le numéro de société ou de service générique, un administrateur peut le faire à l’aide du panneau de configuration Lync Server pour supprimer l’ID de l’appelant et le remplacer par un ID de l’appelant alternatif spécifié.</span><span class="sxs-lookup"><span data-stu-id="6de12-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="6de12-145">Dans la planification de votre logique de routage, déterminez les personnes, groupes ou sites pour lesquels vous souhaiterez activer cette option (vous pourriez même l’activer pour l’ensemble des employés).</span><span class="sxs-lookup"><span data-stu-id="6de12-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6de12-p109">Pour les appels réacheminés sur le réseau téléphonique commuté, l’ID de l’appelant générique s’affiche à la place de l’ID initial. L’appel peut alors contourner les paramètres de confidentialité ou « Ne pas déranger » éventuellement configurés par l’appelé.</span><span class="sxs-lookup"><span data-stu-id="6de12-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="6de12-148">Logique de routage supplémentaire</span><span class="sxs-lookup"><span data-stu-id="6de12-148">Additional Routing Logic</span></span>

<span data-ttu-id="6de12-149">Lors de la création d’itinéraires téléphoniques sortants, vous devez avoir conscience des facteurs suivants susceptibles d’affecter la logique de routage :</span><span class="sxs-lookup"><span data-stu-id="6de12-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="6de12-150">Lorsqu’un appel est établi sur une limite fédérée, la partie domaine de l’URI permet d’acheminer l’appel vers l’entreprise chargée de l’application de la logique du routage sortant.</span><span class="sxs-lookup"><span data-stu-id="6de12-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="6de12-151">Si la partie domaine de l’URI demandé ne contient pas de domaine pris en charge pour l’entreprise, le composant de routage sortant sur le serveur ne traite pas l’appel.</span><span class="sxs-lookup"><span data-stu-id="6de12-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="6de12-152">Si un utilisateur n’est pas activé pour voix entreprise, le serveur applique une autre logique de routage, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="6de12-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="6de12-p110">Si un appel est acheminé vers une passerelle totalement occupée (toutes les lignes de la jonction sont occupées), la passerelle refuse l’appel et la logique de routage des appels sortants le redirige vers l’itinéraire à moindre coût suivant. Vous devez tenir compte de ces éléments, car une passerelle dont la taille est adaptée à un petit bureau à l’étranger (par exemple, Zurich) peut en réalité transporter une quantité considérable de trafic non local pour des appels internationaux vers la Suisse. Si la taille de la passerelle ne convient pas à ce trafic supplémentaire, les appels vers la Suisse peuvent être acheminés via une passerelle située en Allemagne, ce qui augmente les frais téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="6de12-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

