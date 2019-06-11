---
title: Présentation de la Conférence rendez-vous dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 820c880d44a1ecede139a8d3caddf3f6c40e65a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="1ef9d-102">Présentation de la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ef9d-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ef9d-103">_**Dernière modification de la rubrique:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="1ef9d-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="1ef9d-104">Si votre organisation a des utilisateurs qui ont besoin de participer à des conférences en local Lync Server 2013 lorsqu’elles ne sont pas en mesure d’accéder à un ordinateur, vous pouvez déployer la Conférence rendez-vous pour pouvoir participer à la Conférence en utilisant un téléphone commuté public. téléphone réseau (RTC).</span><span class="sxs-lookup"><span data-stu-id="1ef9d-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="1ef9d-105">La fonction de conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lors du déploiement de conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="1ef9d-106">Bien que la Conférence rendez-vous utilise certains des mêmes composants Lync Server 2013 qu’utilise la voix d’entreprise, vous pouvez déployer les conférences rendez-vous, même si vous ne déployez pas Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ef9d-107">Si vous déployez la Conférence rendez-vous, vous devez la déployer dans chaque liste où vous déployez Lync Server 2013 Conferencing.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="1ef9d-108">Vous n’êtes pas obligé d’attribuer des numéros d’accès dans chaque liste, mais vous devez déployer la fonctionnalité de connexion dans chaque liste.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="1ef9d-109">Cette condition prend en charge la fonctionnalité de nom enregistré quand un utilisateur appelle un numéro d’accès à partir d’un pool pour participer à une conférence 2013 Server Lync dans un autre pool.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="1ef9d-110">Les conférences doivent être activées pour l’accès rendez-vous dans la stratégie de réunion.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="1ef9d-111">Par défaut, l’invitation à une conférence pour les conférences activées pour les accès par modem comporte les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ef9d-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="1ef9d-112">ID de conférence numérique identifiant la Conférence.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="1ef9d-113">Un ou plusieurs numéros d’accès PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="1ef9d-114">Un lien vers une page de paramètres de conférence rendez-vous, qui contient la liste complète des numéros d’accès avec les langues associées; un emplacement de création, de réinitialisation et de déblocage des numéros d’identification personnels. ainsi que d’autres informations, telles que les contrôles DTMF (multifrequency Multitone).</span><span class="sxs-lookup"><span data-stu-id="1ef9d-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="1ef9d-115">La fonction de conférence rendez-vous est prise en charge pour les utilisateurs d’entreprise et les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="1ef9d-116">Les utilisateurs de l’entreprise disposent des informations d’identification de services de domaine Active Directory et de comptes Lync Server 2013 au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="1ef9d-117">Les utilisateurs anonymes ne disposent pas d’informations d’identification dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="1ef9d-118">Dans le contexte d’une conférence rendez-vous, un utilisateur d’une organisation d’un partenaire fédéré qui utilise le RTC pour se connecter à une conférence est considéré comme un utilisateur anonyme.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="1ef9d-119">Pour la conférence rendez-vous, contrairement aux autres contextes, les utilisateurs fédérés ne sont pas authentifiés.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="1ef9d-p105">Les utilisateurs d’entreprise ou les organisateurs de conférence qui participent à une conférence activée pour l’accès par modem composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Si un organisateur n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur extension de communications unifiées (ou leur numéro de téléphone complet) et leur code confidentiel ou attendre d’être admis par l’organisateur. L’organisateur de la réunion peut participer à la réunion en tant que tel en entrant seulement son code confidentiel. Le serveur frontal utilise l’association de l’extension du numéro de téléphone complet et du code confidentiel pour mapper de manière unique les utilisateurs d’entreprise à leurs informations d’identification Active Directory. Ils sont ainsi authentifiés et identifiés à l’aide de leur nom dans la conférence. Ils peuvent également adopter un rôle de conférence prédéfini par l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-p105">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ef9d-126">Les utilisateurs d’entreprise qui se connectent à partir d’un téléphone IP Office ou de Lync Server 2013 ou Lync 2010 attendant ne sont pas invités à entrer leur numéro de téléphone, car ils sont déjà authentifiés.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="1ef9d-p106">Les utilisateurs anonymes qui souhaitent participer à une conférence composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Les utilisateurs anonymes non identifiés sont également invités à enregistrer leur nom. Le nom enregistré identifie les utilisateurs non authentifiés au sein de la conférence. Les utilisateurs anonymes ne sont pas admis à la conférence tant qu’au moins un organisateur ou utilisateur authentifié ne l’a pas rejointe. Aucun rôle prédéfini ne peut leur être attribué.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ef9d-p107">Les utilisateurs d’entreprise qui décident de ne pas entrer leur numéro de téléphone ni leur code confidentiel ne sont pas considérés comme authentifiés. Ils sont invités à enregistrer leur nom et traités comme des utilisateurs anonymes dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="1ef9d-133">Au moment de l’échéancier, l’organisateur de la réunion peut choisir de limiter l’accès à la réunion en mettant celle-ci en tant que fermé ou verrouillé.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="1ef9d-134">Dans ce cas, les utilisateurs appelants sont invités à s’authentifier.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="1ef9d-135">Si les utilisateurs d’appels entrants échouent ou choisissent de ne pas s’authentifier, ils sont transférés vers la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="1ef9d-136">Ce dernier patiente dans la salle d’attente jusqu’à ce qu’il soit accepté ou rejeté par un leader ou qu’il se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="1ef9d-137">Les utilisateurs d’appels entrants entendent de la musique s’ils sont en attente d’admission à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="1ef9d-138">Une fois admis dans une conférence, les utilisateurs d’appels entrants peuvent participer à la portion audio de la conférence et exécuter des commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="1ef9d-139">Les responsables de conférences rendez-vous peuvent exécuter des commandes DTMF pour admettre des personnes de la salle d’attente, activer ou désactiver le micro des participants, verrouiller ou déverrouiller la conférence et activer ou désactiver les annonces d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="1ef9d-140">Les organisateurs peuvent également utiliser une commande DTMF pour admettre toutes les personnes de la salle d’attente, ce qui a pour effet de modifier les autorisations de la réunion en autorisant toute personne qui rejoint ultérieurement la réunion.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="1ef9d-141">Tous les participants d’appels entrants peuvent exécuter des commandes DTMF pour écouter l’aide, lire la liste de conférence ou désactiver eux-mêmes leur micro.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="1ef9d-142">Les participants rendez-vous (qu’il s’agisse d’un numéro à partir du RTC), d’entendre les annonces personnelles pendant la Conférence (par exemple, si elles ont été désactivées ou désactivées), si la réunion est enregistrée ou si elle se trouve dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ef9d-143">Les participants qui rejoignent la conférence en cliquant sur un lien au lieu de composer un numéro n’entendent pas les annonces personnelles.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

