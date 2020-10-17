---
title: 'Lync Server 2013 : planification des lignes téléphoniques privées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5381d0f71dd6e15a3b4b6d76f2a03be558b9d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526521"
---
# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="de166-102">Planification des lignes téléphoniques privées avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de166-102">Planning for private telephone lines with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de166-103">_**Dernière modification de la rubrique :** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="de166-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="de166-104">Lync Server 2013 offre la possibilité de fournir aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale.</span><span class="sxs-lookup"><span data-stu-id="de166-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="de166-105">Les lignes téléphoniques privées sont souvent affectées aux cadres et aux autres qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.</span><span class="sxs-lookup"><span data-stu-id="de166-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="de166-106">Les lignes téléphoniques privées ne peuvent être configurées qu’avec Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="de166-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="de166-107">Vous ne pouvez pas configurer de lignes téléphoniques privées avec le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de166-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="de166-108">Les lignes téléphoniques privées doivent être configurées uniquement dans les déploiements de Lync Server et non dans des déploiements mixtes.</span><span class="sxs-lookup"><span data-stu-id="de166-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="de166-109">Caractéristiques des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="de166-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="de166-110">Bien que le concept de deuxième ligne téléphonique privée soit fondamentalement simple, il est important de comprendre les caractéristiques des lignes privées et les façons dont elles sont similaires et différentes des lignes téléphoniques principales des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="de166-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="de166-111">Caractéristiques générales des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="de166-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="de166-112">Un utilisateur ne peut avoir qu’une seule ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="de166-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="de166-113">Un utilisateur avec une ligne téléphonique privée n’a qu’une seule boîte aux lettres vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="de166-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="de166-114">Un utilisateur disposant d’une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée ne donne pas à un utilisateur une fonction de deuxième présence sur le réseau (par exemple, une deuxième identité de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="de166-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="de166-115">Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="de166-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="de166-116">Elles ne sont pas disponibles pour les déploiements hébergés de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de166-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="de166-117">Différences entre les lignes téléphoniques privées et les lignes téléphoniques principales</span><span class="sxs-lookup"><span data-stu-id="de166-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="de166-118">Les numéros de téléphone des lignes téléphoniques privées n’apparaissent pas dans les listes des annuaires téléphoniques ou des contacts qui sont dérivés des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="de166-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="de166-119">Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’équipe, prise d’appel de groupe et application Response Group.</span><span class="sxs-lookup"><span data-stu-id="de166-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="de166-120">Les appels vers une ligne téléphonique privée ont un anneau spécial, et la notification système pour l’appel indique à l’utilisateur que l’appel entrant se trouve sur sa ligne privée.</span><span class="sxs-lookup"><span data-stu-id="de166-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="de166-121">Les appels vers la ligne téléphonique privée sont toujours circulaires.</span><span class="sxs-lookup"><span data-stu-id="de166-121">Calls to the private telephone line always ring through.</span></span> <span data-ttu-id="de166-122">Elles ne suivent pas les règles « ne pas déranger ».</span><span class="sxs-lookup"><span data-stu-id="de166-122">They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="de166-123">Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour effectuer des appels sortants.</span><span class="sxs-lookup"><span data-stu-id="de166-123">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="de166-124">Lorsqu’un utilisateur avec une ligne téléphonique privée effectue un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom de l’utilisateur ou le numéro de téléphone principal de l’utilisateur de la personne appelée.</span><span class="sxs-lookup"><span data-stu-id="de166-124">When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="de166-125">Similitudes entre les lignes téléphoniques privées et les lignes téléphoniques principales</span><span class="sxs-lookup"><span data-stu-id="de166-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="de166-126">Les appels sans réponse à une ligne téléphonique privée sont routés vers la même boîte de réception de messagerie vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).</span><span class="sxs-lookup"><span data-stu-id="de166-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="de166-127">Le parcage d’appel et la prise d’appel fonctionnent avec des lignes téléphoniques privées exactement de la même manière qu’avec la ligne téléphonique principale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de166-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="de166-128">Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale d’un utilisateur, elle est également activée sur la ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="de166-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="de166-129">Le numéro de téléphone d’une ligne téléphonique privée est enregistré dans l’enregistrement des détails des appels de la même manière que le numéro de téléphone de la ligne téléphonique principale d’un utilisateur, mais avec une indication qu’il s’agit d’un numéro de téléphone privé.</span><span class="sxs-lookup"><span data-stu-id="de166-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="de166-130">Une fois qu’un utilisateur répond à un appel sur une ligne téléphonique privée, l’appel est traité de la même manière qu’un appel sur la ligne téléphonique principale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de166-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="de166-131">Par exemple, si un utilisateur qui reçoit un appel sur une ligne téléphonique privée transfère l’appel ou invite d’autres personnes à participer à une téléconférence, le nom de l’utilisateur s’affiche dans Lync 2013 et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur apparaît dans ID de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="de166-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="de166-132">Un utilisateur peut dévier un appel (rediriger l’appel vers une autre destination, telle qu’un téléphone mobile ou un téléphone personnel, avant de répondre) à partir de la ligne téléphonique privée de la même manière qu’avec une ligne téléphonique principale.</span><span class="sxs-lookup"><span data-stu-id="de166-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de166-133">Lorsqu’un appel à une ligne privée est acheminé vers un autre numéro de téléphone, le numéro de téléphone de la ligne téléphonique privée est mis à la disposition de l’autre numéro de téléphone et peut être affiché dans les journaux pour ce numéro.</span><span class="sxs-lookup"><span data-stu-id="de166-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de166-134">Les appels d’une conférence vers la ligne téléphonique privée n’auront aucune indication de <EM>ligne privée</EM> dans la notification système entrante.</span><span class="sxs-lookup"><span data-stu-id="de166-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="de166-135">Administration des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="de166-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="de166-136">En plus des aspects techniques de la création et de la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives pour celles-ci.</span><span class="sxs-lookup"><span data-stu-id="de166-136">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them.</span></span> <span data-ttu-id="de166-137">Cela inclut la détermination des stratégies pour les personnes de l’organisation qui sont éligibles pour une ligne privée, la création et la gestion de listes de personnes et de leurs lignes téléphoniques, éventuellement la création d’un annuaire téléphonique privé pour les cadres, la formation des utilisateurs et les tâches associées.</span><span class="sxs-lookup"><span data-stu-id="de166-137">This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de166-138">La ligne téléphonique privée est stockée dans Active Directory sous la forme d’un attribut msRTCSIP-PrivateLine sur l’objet de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de166-138">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object.</span></span> <span data-ttu-id="de166-139">Par défaut, tout membre du groupe utilisateurs authentifiés dispose d’un accès en lecture à cet attribut.</span><span class="sxs-lookup"><span data-stu-id="de166-139">By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="de166-140">Affectation de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="de166-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="de166-141">Les comptes pour les nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes sans ligne téléphonique privée, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="de166-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="de166-142">Utilisez la cmdlet **Set-Csuser** dans l’environnement de ligne de commande Lync Server Management Shell pour attribuer un numéro de téléphone à une ligne téléphonique privée pour un utilisateur, par exemple, **Set-Csuser-identity "SIP :joe@contoso.com"-PrivateLine "Tél : + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="de166-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="de166-143">Les numéros de téléphone des lignes téléphoniques privées peuvent avoir une longueur comprise entre 3 et 15 chiffres et doivent être précédés du préfixe « TEL : ».</span><span class="sxs-lookup"><span data-stu-id="de166-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="de166-144">Ils peuvent disposer de n’importe quel indicatif régional et de n’importe quel code de pays/région tant que votre organisation dispose d’un accès direct aux codes de zone et de pays/région.</span><span class="sxs-lookup"><span data-stu-id="de166-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="de166-145">Pour plus d’informations sur les applets de commande et sur Lync Server Management Shell, voir la documentation de [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="de166-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="de166-146">Lignes téléphoniques privées dans des déploiements mixtes</span><span class="sxs-lookup"><span data-stu-id="de166-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="de166-147">Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de166-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="de166-148">Dans un déploiement où se trouvent des serveurs Lync Server et Office Communications Server 2007 ou Office Communications Server 2007 R2, lorsqu’un utilisateur d’une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue car le serveur ne peut pas effectuer une recherche inversée de numéros sur une ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="de166-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

