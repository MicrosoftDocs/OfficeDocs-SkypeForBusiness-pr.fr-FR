---
title: Lync Server 2013 voix entreprise
description: Lync Server 2013 voix entreprise.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11f2497cf99319317a75b81f02ed0d8ca797fbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574230"
---
# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="b07a3-103">Voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b07a3-103">Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b07a3-104">_**Dernière modification de la rubrique :** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="b07a3-104">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="b07a3-105">Avec voix entreprise, Lync Server offre une solution autonome VoIP (Voice over Internet Protocol) pour améliorer ou remplacer les systèmes PBX (Private Branch Exchange) traditionnels.</span><span class="sxs-lookup"><span data-stu-id="b07a3-105">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="b07a3-106">Les utilisateurs de voix entreprise peuvent appeler des collègues sur le réseau VoIP ou le PBX de votre organisation, et ils peuvent appeler des numéros de téléphone traditionnels en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b07a3-106">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="b07a3-107">La solution voix entreprise inclut des fonctionnalités d’appel courantes telles que Answer, Forward, Transfer, Hold, reroutement, Release et parcage, ainsi qu’un appel amélioré 9-1-1 (E9-1-1) (E9-1-1 n’est disponible qu’aux États-Unis). Voix entreprise prend également en charge un large éventail d’appareils IP et USB plus anciens et actuels.</span><span class="sxs-lookup"><span data-stu-id="b07a3-107">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="b07a3-108">Émission et réception d’appels</span><span class="sxs-lookup"><span data-stu-id="b07a3-108">Placing and Receiving Calls</span></span>

<span data-ttu-id="b07a3-109">À l’aide de Lync, les utilisateurs peuvent passer des appels en tapant un nom ou un numéro de téléphone sur leur clavier, ou en utilisant un pavé de numérotation affiché à l’écran.</span><span class="sxs-lookup"><span data-stu-id="b07a3-109">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="b07a3-110">Ils peuvent également passer des appels directement à partir de leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="b07a3-110">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="b07a3-111">Vous pouvez également déployer des appareils Lync Phone Edition, qui sont des appareils de téléphonie IP autonomes fournis par des partenaires Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b07a3-111">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="b07a3-112">Les utilisateurs peuvent avoir plusieurs appareils téléphoniques enregistrés auprès de Lync Server et peuvent passer facilement de l’un à l’autre.</span><span class="sxs-lookup"><span data-stu-id="b07a3-112">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="b07a3-113">En cas d’appel entrant, les utilisateurs sont avertis simultanément sur tous leurs périphériques par des sonneries personnalisables sur les périphériques de téléphonie IP et par une notification similaire à un message instantané sur leur PC.</span><span class="sxs-lookup"><span data-stu-id="b07a3-113">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="b07a3-114">Ils peuvent également définir un numéro de téléphone auquel ils peuvent être contactés sur leur téléphone de bureau, leur PC et leur téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="b07a3-114">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="b07a3-115">Fonctionnalités d’appel de base</span><span class="sxs-lookup"><span data-stu-id="b07a3-115">Basic Call Features</span></span>

<span data-ttu-id="b07a3-p103">Lorsqu’il téléphone, un utilisateur peut répondre à d’autres appels entrants ou passer des appels sortants : l’appel en cours est alors automatiquement mis en attente. Il est possible de transférer un appel d’un utilisateur à l’autre, soit directement, soit après que le premier utilisateur ait parlé en privé au deuxième utilisateur. Les utilisateurs peuvent également transférer un appel vers un autre périphérique, par exemple vers leur téléphone mobile, lorsqu’ils quittent le bureau.</span><span class="sxs-lookup"><span data-stu-id="b07a3-p103">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold. Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user. Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="b07a3-119">Fonctionnalités de communication plus puissantes</span><span class="sxs-lookup"><span data-stu-id="b07a3-119">Richer Communications</span></span>

<span data-ttu-id="b07a3-120">Lorsqu’ils communiquent avec Lync, les utilisateurs peuvent facilement ajouter du texte, une vidéo ou un partage de bureau à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b07a3-120">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="b07a3-121">La fonctionnalité do-not-disrang est intégrée aux paramètres de présence dans Lync.</span><span class="sxs-lookup"><span data-stu-id="b07a3-121">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="b07a3-122">Avec la messagerie unifiée Exchange, Lync et Lync Server s’intègrent à Microsoft Exchange Server 2013 et Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="b07a3-122">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="b07a3-123">Les utilisateurs peuvent voir s’ils ont de nouveaux messages vocaux dans leur fenêtre Lync et dans leurs courriers électroniques.</span><span class="sxs-lookup"><span data-stu-id="b07a3-123">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="b07a3-124">Si le message vocal est enregistré dans un message électronique, l’utilisateur peut cliquer dessus pour l’écouter ou afficher la transcription du message vocal.</span><span class="sxs-lookup"><span data-stu-id="b07a3-124">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="b07a3-125">Fonctionnalités d’appel avancées</span><span class="sxs-lookup"><span data-stu-id="b07a3-125">Advanced Calling Features</span></span>

<span data-ttu-id="b07a3-126">Voix entreprise comprend également plusieurs fonctionnalités d’appel avancées, telles que la délégation d’appel Lync, l’appel d’équipe, la prise d’appel de groupe et les groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="b07a3-126">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="b07a3-127">La délégation d’appel Lync permet aux utilisateurs de déléguer la gestion des appels à un ou plusieurs assistants, en accédant à la section **Outils** \> **options** de \> **transfert d’appel**.</span><span class="sxs-lookup"><span data-stu-id="b07a3-127">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="b07a3-128">Le délégué peut effectuer plusieurs tâches d’appel au nom de l’utilisateur, y compris le filtrage et l’émission d’appels ou l’initialisation de conférences.</span><span class="sxs-lookup"><span data-stu-id="b07a3-128">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b07a3-129">Il se peut que vous cherchiez une autre fonctionnalité nommée de la même manière que la délégation de calendrier Lync.</span><span class="sxs-lookup"><span data-stu-id="b07a3-129">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="b07a3-130">Elle ne requiert pas la fonctionnalité voix entreprise et permet aux utilisateurs de planifier des réunions Lync en ligne à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="b07a3-130">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="b07a3-131">Si vous êtes à la recherche de ces informations, nous vous recommandons d’extraire <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> pour plus d’informations sur l’activation de la synchronisation des délégués Exchange.</span><span class="sxs-lookup"><span data-stu-id="b07a3-131">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="b07a3-132">L’appel d’équipe permet à un utilisateur de faire en sorte que les appels entrants sonnent simultanément sur les téléphones des coéquipiers afin que tout le monde de l’équipe puisse répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b07a3-132">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="b07a3-133">Group Call Pick, une nouvelle fonctionnalité des mises à jour cumulatives pour Lync Server 2013 : février 2013, permet aux utilisateurs de répondre à leurs collègues à partir de leurs propres téléphones.</span><span class="sxs-lookup"><span data-stu-id="b07a3-133">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="b07a3-134">La prise d’appel de groupe diffère de l’appel de l’équipe principalement dans le fait qu’un appel entrant sonne uniquement sur le téléphone du destinataire, mais que tous les autres utilisateurs peuvent le répondre en composant un numéro de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="b07a3-134">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="b07a3-p109">Le service Response Group peut être configuré en vue de mettre en attente et d’acheminer intelligemment les appels vers des agents désignés. Les supports techniques informatiques, les services d’assistance téléphoniques des ressources humaines et d’autres centres de contact internes l’utilisent couramment.</span><span class="sxs-lookup"><span data-stu-id="b07a3-p109">Response Groups can be set up for queuing and intelligently routing calls to designated agents. Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="b07a3-137">Administration de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="b07a3-137">Enterprise Voice Administration</span></span>

<span data-ttu-id="b07a3-138">Lync Server utilise des standards et des interfaces publiées pour interagir avec l’infrastructure existante.</span><span class="sxs-lookup"><span data-stu-id="b07a3-138">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="b07a3-139">Il prend en charge les options de passerelle et SIP (comme la jonction SIP) pour permettre l’interconnexion avec les systèmes PBX IP et les réseaux PSTN afin que vous puissiez migrer progressivement les utilisateurs vers Voix Entreprise, tout en minimisant les risques d’interruption.</span><span class="sxs-lookup"><span data-stu-id="b07a3-139">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="b07a3-140">Lync Server prend en charge les codecs traditionnels tels que G. 711, G. 722 et G. 723.1 pour l’interopérabilité avec les solutions VoIP traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="b07a3-140">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="b07a3-141">Avec le contrôle d’admission des appels (CAC), les administrateurs peuvent définir des limites sur la quantité de trafic vocal et vidéo Lync Server transitant sur des liaisons réseau restreintes, et spécifier l’action à effectuer si un nouvel appel dépasse la limite.</span><span class="sxs-lookup"><span data-stu-id="b07a3-141">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="b07a3-142">Par exemple, l’appel peut être routé par un autre chemin ou refusé.</span><span class="sxs-lookup"><span data-stu-id="b07a3-142">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="b07a3-143">Lync Server collabore avec des appliances Survivables Branch Office pour fournir des services d’appels locaux et une connexion RTC aux succursales, en cas de panne de réseau étendu (WAN) sur le site central.</span><span class="sxs-lookup"><span data-stu-id="b07a3-143">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

