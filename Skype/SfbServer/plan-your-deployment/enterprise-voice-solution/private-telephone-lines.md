---
title: Planifier des lignes téléphoniques privées avec Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planification de lignes téléphoniques privées (secondaires) dans Skype entreprise Server Voice.
ms.openlocfilehash: 001a83e4bd81f0f47546f51f1d4993c6b1cec4bf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802564"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="44467-103">Planifier des lignes téléphoniques privées avec Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="44467-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="44467-104">Planification de lignes téléphoniques privées (secondaires) dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="44467-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="44467-105">Skype entreprise Server vous permet de donner aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale.</span><span class="sxs-lookup"><span data-stu-id="44467-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="44467-106">Les lignes téléphoniques privées sont souvent attribuées aux cadres et aux personnes qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.</span><span class="sxs-lookup"><span data-stu-id="44467-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="44467-107">Les lignes téléphoniques privées ne peuvent être configurées qu’avec Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="44467-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="44467-108">Vous ne pouvez pas configurer de lignes téléphoniques privées avec le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="44467-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="44467-109">Les lignes téléphoniques privées doivent être configurées uniquement dans les déploiements de Skype entreprise Server et non dans les déploiements mixtes.</span><span class="sxs-lookup"><span data-stu-id="44467-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="44467-110">Caractéristiques des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="44467-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="44467-111">Même si le concept d’une deuxième ligne téléphonique privée est fondamentalement simple, il est important de bien comprendre les caractéristiques des lignes privées et celles selon lesquelles celles-ci sont similaires et différentes des principales lignes de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44467-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="44467-112">Caractéristiques générales des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="44467-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="44467-113">Un utilisateur ne peut disposer que d’une seule ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="44467-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="44467-114">Un utilisateur avec une ligne téléphonique privée n’est doté que d’une seule messagerie vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="44467-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="44467-115">Un utilisateur avec une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée n’accorde pas à l’utilisateur une deuxième présence sur le réseau (comme une deuxième identité de messagerie instantanée).</span><span class="sxs-lookup"><span data-stu-id="44467-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="44467-116">Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="44467-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="44467-117">Elles ne sont pas disponibles dans les déploiements hébergés de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="44467-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="44467-118">Différences entre les lignes téléphoniques privées et principales</span><span class="sxs-lookup"><span data-stu-id="44467-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="44467-119">Les numéros de téléphone des lignes privées ne s’affichent pas dans les annuaires ou les listes de contacts dérivés des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44467-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="44467-120">Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’appel d’équipe, prise d’appel de groupe et application Response Group.</span><span class="sxs-lookup"><span data-stu-id="44467-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="44467-121">Les appels sur une ligne téléphonique privée présentent une sonnerie spéciale et la notification système de l’appel indique à l’utilisateur que l’appel entre sur sa ligne privée.</span><span class="sxs-lookup"><span data-stu-id="44467-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="44467-p104">Les appels sur la ligne téléphonique privée sonnent systématiquement. Ils ne suivent pas les règles « Ne pas déranger ».</span><span class="sxs-lookup"><span data-stu-id="44467-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="44467-124">Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour passer des appels sortants.</span><span class="sxs-lookup"><span data-stu-id="44467-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="44467-125">Lorsqu’un utilisateur disposant d’une ligne téléphonique privée effectue un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom de l’utilisateur ou le numéro de téléphone principal de l’utilisateur de la personne appelée.</span><span class="sxs-lookup"><span data-stu-id="44467-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="44467-126">Similitudes entre les lignes téléphoniques privées et principales</span><span class="sxs-lookup"><span data-stu-id="44467-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="44467-127">Les appels sans réponse sur une ligne téléphonique privée sont routés vers la même boîte de réception vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).</span><span class="sxs-lookup"><span data-stu-id="44467-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="44467-128">Le parc d’appels et le prélèvement d’appel fonctionnent avec des lignes téléphoniques privées de la même manière que pour la ligne téléphonique principale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44467-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="44467-129">Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale d’un utilisateur, celle-ci est également activée sur la ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="44467-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="44467-130">Le numéro de téléphone d’une ligne téléphonique privée est enregistré dans l’enregistrement des détails de l’appel de la même manière que le numéro de téléphone de la ligne téléphonique principale d’un utilisateur, mais il indique qu’il s’agit d’un numéro de téléphone privé.</span><span class="sxs-lookup"><span data-stu-id="44467-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="44467-131">Lorsque l’utilisateur répond à un appel sur une ligne téléphonique privée, l’appel est traité comme un appel sur la ligne téléphonique principale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44467-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="44467-132">Par exemple, si un utilisateur qui reçoit un appel sur une ligne téléphonique privée transfère l’appel ou invitez d’autres personnes à participer à une conférence téléphonique, le nom de l’utilisateur apparaît dans Skype entreprise et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur apparaît dans l’identification de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="44467-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="44467-133">Un utilisateur peut rediriger un appel (vers une autre destination, comme un téléphone mobile ou personnel, avant de répondre) provenant de la ligne téléphonique privée comme avec une ligne téléphonique principale.</span><span class="sxs-lookup"><span data-stu-id="44467-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="44467-134">Lorsqu’un appel sur la ligne privée est routé sur un autre numéro de téléphone, le numéro de la ligne privée est mis à la disposition de l’autre numéro et peut être affiché dans les journaux pour ce numéro.</span><span class="sxs-lookup"><span data-stu-id="44467-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="44467-135">Les appels d’une conférence vers la ligne téléphonique privée n’indiquent pas de *ligne privée* dans la notification du système entrant.</span><span class="sxs-lookup"><span data-stu-id="44467-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="44467-136">Administration des lignes téléphoniques privées</span><span class="sxs-lookup"><span data-stu-id="44467-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="44467-p107">Outre les aspects techniques liés à la création et à la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives, entre autres déterminer des stratégies afin de définir qui est autorisé à obtenir une ligne privée dans l’organisation, créer et gérer des listes de personnes et de leurs lignes téléphoniques, créer éventuellement un annuaire téléphonique privé pour les cadres, organiser des formations pour les utilisateurs, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="44467-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44467-p108">La ligne téléphonique privée est stockée dans Active Directory en tant qu’attribut msRTCSIP-PrivateLine de l’objet utilisateur. Par défaut, tout membre du groupe Utilisateurs authentifiés dispose d’un accès en lecture à cet attribut.</span><span class="sxs-lookup"><span data-stu-id="44467-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="44467-141">Attribution de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="44467-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="44467-142">Les comptes pour les nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes sans lignes téléphoniques privées, en utilisant le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="44467-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="44467-143">Utilisez l’applet de commande **Set-Csuser** dans Skype entreprise Server Management Shell pour affecter un numéro de téléphone à une ligne téléphonique privée pour un utilisateur (par exemple, **Set-Csuser-identity "SIP :joe@contoso.com"-PrivateLine "Tél : + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="44467-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="44467-144">Les numéros de téléphone des lignes téléphoniques privées peuvent contenir entre 3 et 15 numéros de longueur et doivent être précédés du préfixe « TEL : ».</span><span class="sxs-lookup"><span data-stu-id="44467-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="44467-145">Ils peuvent ne pas présenter d’indicatif régional, ni d’indicatif de pays/région si l’organisation dispose d’une sélection directe à l’arrivée pour ces indicatifs.</span><span class="sxs-lookup"><span data-stu-id="44467-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="44467-146">Pour plus d’informations sur les applets de applet et Skype entreprise Server Management Shell, voir la documentation de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="44467-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="44467-147">Lignes téléphoniques privées dans des déploiements mixtes</span><span class="sxs-lookup"><span data-stu-id="44467-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="44467-148">Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Skype entreprise Server ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44467-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="44467-149">Dans le cadre d’un déploiement dans lequel des serveurs exécutent des versions antérieures de Lync Server, quand un utilisateur sur une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue, car le serveur ne peut pas effectuer de recherche inverse sur une ligne téléphonique privée.</span><span class="sxs-lookup"><span data-stu-id="44467-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

