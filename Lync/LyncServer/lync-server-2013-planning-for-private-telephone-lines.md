---
title: 'Lync Server 2013 : planification de lignes téléphoniques privées'
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
ms.openlocfilehash: 0df93d8a8de73a3119e7ca9a1a7abd76e9157a17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="fb003-102">Planification de lignes téléphoniques privées avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb003-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb003-103">_**Dernière modification de la rubrique :** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="fb003-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="fb003-104">Lync Server 2013 offre la possibilité de proposer aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale.</span><span class="sxs-lookup"><span data-stu-id="fb003-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="fb003-105">Les lignes téléphoniques privées sont souvent attribuées aux cadres et aux personnes qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.</span><span class="sxs-lookup"><span data-stu-id="fb003-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="fb003-106">Les lignes téléphoniques privées ne peuvent être configurées qu’avec Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fb003-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="fb003-107">Vous ne pouvez pas configurer de lignes téléphoniques privées avec le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb003-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="fb003-108">Les lignes téléphoniques privées doivent être configurées uniquement dans les déploiements de Lync Server et non dans les déploiements mixtes.</span><span class="sxs-lookup"><span data-stu-id="fb003-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="fb003-109">Caractéristiques des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="fb003-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="fb003-110">Même si le concept de la deuxième ligne téléphonique privée est simple à la base, il est important de comprendre les caractéristiques des lignes privées, ainsi que leurs similitudes et différences par rapport aux lignes téléphoniques principales des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb003-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="fb003-111">Caractéristiques générales des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="fb003-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="fb003-112">Un utilisateur ne peut disposer que d’une seule ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="fb003-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="fb003-113">Un utilisateur avec une ligne téléphonique privée n’est doté que d’une seule messagerie vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="fb003-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="fb003-114">Un utilisateur avec une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée n’accorde pas à l’utilisateur une deuxième présence sur le réseau (comme une deuxième identité de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="fb003-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="fb003-115">Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="fb003-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="fb003-116">Elles ne sont pas disponibles pour les déploiements hébergés de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb003-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="fb003-117">Différences entre les lignes téléphoniques privées et principales</span><span class="sxs-lookup"><span data-stu-id="fb003-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="fb003-118">Les numéros de téléphone des lignes privées ne s’affichent pas dans les annuaires ou les listes de contacts dérivés des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb003-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="fb003-119">Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’appel d’équipe, prise d’appel de groupe et application Response Group.</span><span class="sxs-lookup"><span data-stu-id="fb003-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="fb003-120">Les appels sur une ligne téléphonique privée présentent une sonnerie spéciale et la notification système de l’appel indique à l’utilisateur que l’appel entre sur sa ligne privée.</span><span class="sxs-lookup"><span data-stu-id="fb003-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="fb003-p104">Les appels sur la ligne téléphonique privée sonnent systématiquement. Ils ne suivent pas les règles « Ne pas déranger ».</span><span class="sxs-lookup"><span data-stu-id="fb003-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="fb003-p105">Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour passer des appels sortants. Lorsqu’un utilisateur doté d’une ligne téléphonique privée passe un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom ou le numéro de téléphone principal de l’utilisateur à la personne appelée.</span><span class="sxs-lookup"><span data-stu-id="fb003-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="fb003-125">Similitudes entre les lignes téléphoniques privées et principales</span><span class="sxs-lookup"><span data-stu-id="fb003-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="fb003-126">Les appels sans réponse sur une ligne téléphonique privée sont routés vers la même boîte de réception vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).</span><span class="sxs-lookup"><span data-stu-id="fb003-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="fb003-127">Le parcage d’appel et la prise d’appel fonctionnent avec les lignes téléphoniques privées exactement de la même manière qu’avec la ligne téléphonique principale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb003-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="fb003-128">Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale de l’utilisateur, elle l’est également sur la ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="fb003-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="fb003-129">Le numéro de téléphone d’une ligne téléphonique privée est consigné dans l’enregistrement des détails des appels comme le numéro de la ligne principale d’un utilisateur, mais en précisant qu’il s’agit d’un numéro de téléphone privé.</span><span class="sxs-lookup"><span data-stu-id="fb003-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="fb003-130">Une fois que l’utilisateur a répondu à un appel sur la ligne téléphonique privée, l’appel est traité de la même manière qu’un appel passé sur la ligne téléphonique principale d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb003-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="fb003-131">Par exemple, si un utilisateur qui reçoit un appel sur une ligne téléphonique privée transfère l’appel ou invitez d’autres personnes à participer à une conférence téléphonique, le nom de l’utilisateur apparaît dans Lync 2013 et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur apparaît dans l’identification de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fb003-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="fb003-132">Un utilisateur peut rediriger un appel (vers une autre destination, comme un téléphone mobile ou personnel, avant de répondre) provenant de la ligne téléphonique privée comme avec une ligne téléphonique principale.</span><span class="sxs-lookup"><span data-stu-id="fb003-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb003-133">Lorsqu’un appel sur la ligne privée est routé sur un autre numéro de téléphone, le numéro de la ligne privée est mis à la disposition de l’autre numéro et peut être affiché dans les journaux pour ce numéro.</span><span class="sxs-lookup"><span data-stu-id="fb003-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb003-134">Les appels d’une conférence vers la ligne téléphonique privée ne porteront pas la mention de <EM>ligne privée</EM> dans la notification système entrante.</span><span class="sxs-lookup"><span data-stu-id="fb003-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="fb003-135">Administration des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="fb003-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="fb003-p107">Outre les aspects techniques liés à la création et à la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives, entre autres déterminer des stratégies afin de définir qui est autorisé à obtenir une ligne privée dans l’organisation, créer et gérer des listes de personnes et de leurs lignes téléphoniques, créer éventuellement un annuaire téléphonique privé pour les cadres, organiser des formations pour les utilisateurs, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="fb003-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb003-p108">La ligne téléphonique privée est stockée dans Active Directory en tant qu’attribut msRTCSIP-PrivateLine de l’objet utilisateur. Par défaut, tout membre du groupe Utilisateurs authentifiés dispose d’un accès en lecture à cet attribut.</span><span class="sxs-lookup"><span data-stu-id="fb003-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="fb003-140">Attribution de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="fb003-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="fb003-141">Les comptes pour les nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes sans lignes téléphoniques privées, à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fb003-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="fb003-142">Utilisez l’applet de commande **Set-Csuser** dans Lync Server Management Shell pour affecter un numéro de téléphone à une ligne téléphonique privée pour un utilisateur, par exemple, **Set-Csuser-identity "SIP :joe@contoso.com"-PrivateLine "Tél : + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="fb003-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="fb003-143">Les numéros de téléphone des lignes téléphoniques privées peuvent contenir entre 3 et 15 numéros de longueur et doivent être précédés du préfixe « TEL : ».</span><span class="sxs-lookup"><span data-stu-id="fb003-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="fb003-144">Ils peuvent ne pas présenter d’indicatif régional, ni d’indicatif de pays/région si l’organisation dispose d’une sélection directe à l’arrivée pour ces indicatifs.</span><span class="sxs-lookup"><span data-stu-id="fb003-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="fb003-145">Pour plus d’informations sur les applets de applet et Lync Server Management Shell, voir la documentation [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="fb003-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="fb003-146">Lignes téléphoniques privées dans des déploiements mixtes</span><span class="sxs-lookup"><span data-stu-id="fb003-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="fb003-147">Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb003-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="fb003-148">Dans le cadre d’un déploiement dans lequel les serveurs Lync Server et Office Communications 2007 Server 2007 ou Office Communications Server R2 sont tous deux configurés sur une ligne téléphonique privée, le routage de l’appel échoue, car le serveur ne peut pas effectuer une recherche de numéro inverse sur une ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="fb003-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

