---
title: Vue d’ensemble de la Conférence rendez-vous Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d6717f183066688fdf94d0fc83e0e662c9a6b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="8b889-102">Vue d’ensemble de la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b889-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b889-103">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8b889-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8b889-104">Si votre organisation a des utilisateurs qui ont besoin de participer à des conférences locales Lync Server 2013 lorsqu’elles n’ont pas accès à un ordinateur, vous pouvez déployer la Conférence rendez-vous afin qu’ils puissent rejoindre la Conférence à l’aide d’un téléphone commuté public. téléphone réseau (PSTN).</span><span class="sxs-lookup"><span data-stu-id="8b889-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="8b889-105">La Conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lors du déploiement de la Conférence Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b889-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="8b889-106">Même si la fonctionnalité de conférence rendez-vous utilise certains des mêmes composants Lync Server 2013 que voix entreprise, vous pouvez déployer la Conférence rendez-vous même si vous ne déployez pas voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="8b889-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b889-107">Si vous déployez la Conférence rendez-vous, vous devez la déployer dans tous les pools où vous déployez les conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b889-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="8b889-108">Vous n’avez pas besoin d’attribuer des numéros d’accès dans chaque pool, mais vous devez déployer la fonctionnalité d’accès entrant dans chaque pool.</span><span class="sxs-lookup"><span data-stu-id="8b889-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="8b889-109">Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour joindre une conférence Lync Server 2013 dans un autre pool.</span><span class="sxs-lookup"><span data-stu-id="8b889-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="8b889-110">Les conférences doivent être activées pour l’accès à distance dans la stratégie de réunion.</span><span class="sxs-lookup"><span data-stu-id="8b889-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="8b889-111">Par défaut, les conférences qui sont activées pour l’accès à distance incluent les informations suivantes dans l’invitation à la Conférence :</span><span class="sxs-lookup"><span data-stu-id="8b889-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="8b889-112">ID de conférence numérique qui identifie la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="8b889-113">Un ou plusieurs numéros d’accès PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b889-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="8b889-114">Un lien vers une page de paramètres de conférence rendez-vous, qui contient une liste complète des numéros d’accès avec leurs langues associées ; emplacement de création, de réinitialisation ou de déblocage des codes confidentiels (pin); et d’autres informations, telles que les contrôles DTMF (Dual-Tone Multi-Frequency).</span><span class="sxs-lookup"><span data-stu-id="8b889-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="8b889-115">La Conférence rendez-vous prend en charge les utilisateurs d’entreprise et les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="8b889-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="8b889-116">Les utilisateurs d’entreprise ont des informations d’identification des services de domaine Active Directory et des comptes Lync Server 2013 au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="8b889-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="8b889-117">Les utilisateurs anonymes ne disposent pas d’informations d’identification d’entreprise au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8b889-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="8b889-118">Dans le contexte de la Conférence rendez-vous, un utilisateur de l’organisation d’un partenaire fédéré qui utilise le RTC pour se connecter à une conférence est considéré comme un utilisateur anonyme.</span><span class="sxs-lookup"><span data-stu-id="8b889-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="8b889-119">Pour les conférences rendez-vous, contrairement aux autres contextes, les utilisateurs fédérés ne sont pas authentifiés.</span><span class="sxs-lookup"><span data-stu-id="8b889-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="8b889-120">Les utilisateurs d’entreprise ou les responsables de conférence qui rejoignent une conférence activée pour l’accès à distance composent l’un des numéros d’accès de conférence, puis sont invités à entrer l’ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="8b889-121">Si un organisateur n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur extension de communications unifiées (UC) (ou numéro de téléphone complet) et le code confidentiel ou attendre qu’ils soient admis par un organisateur.</span><span class="sxs-lookup"><span data-stu-id="8b889-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="8b889-122">L’organisateur de la réunion peut participer à la réunion en tant que leader en entrant uniquement son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="8b889-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="8b889-123">Le serveur frontal utilise la combinaison de numéro de téléphone ou de poste complet, ainsi que le code confidentiel, pour mapper de manière unique les utilisateurs d’entreprise avec leurs informations d’identification Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8b889-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="8b889-124">Par conséquent, les utilisateurs de l’entreprise sont authentifiés et identifiés par leur nom dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="8b889-125">Les utilisateurs d’entreprise peuvent également supposer qu’un rôle de conférence prédéfini par l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="8b889-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b889-126">Les utilisateurs d’entreprise qui se connectent à partir d’un téléphone IP Office ou de Lync Server 2013 ou Lync 2010 attendant ne sont pas invités à entrer leur numéro de téléphone, car ils sont déjà authentifiés.</span><span class="sxs-lookup"><span data-stu-id="8b889-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="8b889-127">Les utilisateurs anonymes qui souhaitent participer à une conférence rendez-vous composent l’un des numéros d’accès de conférence, puis ils sont invités à entrer l’ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-127">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID.</span></span> <span data-ttu-id="8b889-128">Les utilisateurs anonymes non authentifiés sont également invités à enregistrer leur nom.</span><span class="sxs-lookup"><span data-stu-id="8b889-128">Unauthenticated anonymous users are also prompted to record their name.</span></span> <span data-ttu-id="8b889-129">Le nom enregistré identifie les utilisateurs non authentifiés de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-129">The recorded name identifies unauthenticated users in the conference.</span></span> <span data-ttu-id="8b889-130">Les utilisateurs anonymes ne sont pas admis à la Conférence tant qu’au moins un utilisateur de l’organisateur ou authentifié ne s’est pas associé à un rôle prédéfini.</span><span class="sxs-lookup"><span data-stu-id="8b889-130">Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b889-131">Les utilisateurs d’entreprise qui choisissent de ne pas entrer leur numéro de téléphone et leur code confidentiel ne sont pas authentifiés.</span><span class="sxs-lookup"><span data-stu-id="8b889-131">Enterprise users who choose not to enter their phone number and PIN are not authenticated.</span></span> <span data-ttu-id="8b889-132">Ils sont invités à enregistrer leur nom et sont traités comme des utilisateurs anonymes dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-132">They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="8b889-133">Au moment de la planification, l’organisateur de la réunion peut choisir de restreindre l’accès à la réunion en faisant en sorte que la réunion soit fermée ou verrouillée.</span><span class="sxs-lookup"><span data-stu-id="8b889-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="8b889-134">Dans ce cas, les utilisateurs d’appels entrants sont invités à s’authentifier.</span><span class="sxs-lookup"><span data-stu-id="8b889-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="8b889-135">Si les utilisateurs d’appels entrants échouent ou ne s’authentifient pas, ils sont transférés vers la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="8b889-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="8b889-136">Ils attendent dans la salle d’attente jusqu’à ce qu’un organisateur les accepte ou les refuse, ou qu’ils expirent et soient déconnectés.</span><span class="sxs-lookup"><span data-stu-id="8b889-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="8b889-137">Les utilisateurs d’appels entrants entendent la musique s’ils attendent d’être admis à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="8b889-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="8b889-138">Une fois qu’elles sont admises à une conférence, les utilisateurs d’appels entrants peuvent participer à la partie audio de la Conférence et peuvent exercer des commandes DTMF (Dual-Tone Multi-Frequency) à l’aide du clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="8b889-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="8b889-139">Les responsables rendez-vous peuvent exercer des commandes DTMF pour activer ou désactiver la fonctionnalité de désactivation des participants, verrouiller ou déverrouiller la Conférence, admettre des personnes de la salle d’attente et activer ou désactiver les annonces d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="8b889-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="8b889-140">Les dirigeants peuvent également utiliser une commande DTMF pour admettre tout le monde à partir de la salle d’attente, ce qui permet de modifier les autorisations de la réunion afin d’autoriser les personnes qui rejoignent par la suite.</span><span class="sxs-lookup"><span data-stu-id="8b889-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="8b889-141">Tous les participants à la Conférence rendez-vous peuvent exécuter des commandes DTMF pour écouter l’aide, écouter la liste des conférences et s’activer.</span><span class="sxs-lookup"><span data-stu-id="8b889-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="8b889-142">Les participants à la Conférence rendez-vous (c’est-à-dire, s’ils composent ou non le numéro de téléphone RTC), écoutez des annonces personnelles pendant la Conférence, par exemple si elles ont été désactivées ou désactivées, si elles sont en cours d’enregistrement ou si une autre personne attend dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="8b889-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b889-143">Les participants qui rejoignent la Conférence en cliquant sur un lien au lieu de composer un numéro n’entendent pas les annonces personnelles.</span><span class="sxs-lookup"><span data-stu-id="8b889-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

