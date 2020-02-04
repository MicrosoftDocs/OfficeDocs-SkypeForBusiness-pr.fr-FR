---
title: Voix Entreprise dans Lync Server 2013
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
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="105ed-102">Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="105ed-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="105ed-103">_**Dernière modification de la rubrique :** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="105ed-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="105ed-104">Avec Enterprise Voice, Lync Server fournit une offre VoIP (voix sur IP) autonome pour améliorer ou remplacer les systèmes PBX (Private Branch Exchange) traditionnels.</span><span class="sxs-lookup"><span data-stu-id="105ed-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="105ed-105">Les utilisateurs d’Enterprise Voice peuvent appeler des collègues sur le réseau VoIP ou le PBX de votre organisation, et ils peuvent appeler des numéros de téléphone traditionnels à l’extérieur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="105ed-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="105ed-106">La solution voix entreprise inclut des fonctionnalités d’appel courantes, telles que réponse, transfert, transfert, mise en attente, dérouter, libérer et parc, et 9-1-1 (E9-1-1-1). Voix entreprise prend également en charge un vaste éventail d’appareils IP et USB plus courants.</span><span class="sxs-lookup"><span data-stu-id="105ed-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="105ed-107">Placement et réception d’appels</span><span class="sxs-lookup"><span data-stu-id="105ed-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="105ed-108">Lync permet aux utilisateurs de passer des appels en tapant un nom ou un numéro de téléphone sur leur clavier, ou à l’aide d’un pavé de numérotation affiché à l’écran.</span><span class="sxs-lookup"><span data-stu-id="105ed-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="105ed-109">Les utilisateurs peuvent également lancer des appels directement depuis leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="105ed-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="105ed-110">Vous pouvez également déployer des appareils Lync Phone Edition, qui sont des appareils de téléphone IP autonomes proposés par des partenaires Microsoft.</span><span class="sxs-lookup"><span data-stu-id="105ed-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="105ed-111">Les utilisateurs peuvent utiliser plusieurs appareils téléphoniques enregistrés sur Lync Server et pouvoir basculer entre eux facilement.</span><span class="sxs-lookup"><span data-stu-id="105ed-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="105ed-112">Les utilisateurs sont avertis de tous les appels entrants sur tous leurs appareils, avec des sonneries personnalisées sur les appareils de téléphone IP et une notification similaire à un message instantané sur leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="105ed-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="105ed-113">Les utilisateurs peuvent également définir un numéro de téléphone qui se connecte à leur téléphone de bureau, leur PC et leur téléphone mobile, afin de pouvoir y accéder où qu’ils se trouvent.</span><span class="sxs-lookup"><span data-stu-id="105ed-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="105ed-114">Fonctionnalités d’appel de base</span><span class="sxs-lookup"><span data-stu-id="105ed-114">Basic Call Features</span></span>

<span data-ttu-id="105ed-115">Pendant un appel, un utilisateur peut répondre à d’autres appels entrants ou lancer des appels sortants, et l’appel actif actuel est mis automatiquement en attente.</span><span class="sxs-lookup"><span data-stu-id="105ed-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="105ed-116">Les appels peuvent être transférés d’un utilisateur à un autre, directement ou après que le premier utilisateur parle en privé.</span><span class="sxs-lookup"><span data-stu-id="105ed-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="105ed-117">Les utilisateurs peuvent également transférer des appels vers un autre appareil. par exemple, ils pourraient transférer un appel actif vers leur téléphone mobile, car ils découvrent la porte de leur bureau.</span><span class="sxs-lookup"><span data-stu-id="105ed-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="105ed-118">Communications plus complètes</span><span class="sxs-lookup"><span data-stu-id="105ed-118">Richer Communications</span></span>

<span data-ttu-id="105ed-119">Lorsque vous parlez à un autre utilisateur avec Lync, les utilisateurs peuvent facilement ajouter du texte, de la vidéo ou du partage de bureau à l’appel.</span><span class="sxs-lookup"><span data-stu-id="105ed-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="105ed-120">La fonctionnalité ne pas déranger est intégrée aux paramètres de présence dans Lync.</span><span class="sxs-lookup"><span data-stu-id="105ed-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="105ed-121">Avec la messagerie unifiée Exchange, Lync et Lync Server s’intègrent à Microsoft Exchange Server 2013 et Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="105ed-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="105ed-122">Les utilisateurs peuvent voir s’ils ont de nouveaux messages vocaux dans leur fenêtre Lync et dans leurs messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="105ed-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="105ed-123">Dans un courrier électronique, ils peuvent cliquer pour lire le fichier audio de la messagerie vocale dans un message électronique ou afficher une transcription du message vocal.</span><span class="sxs-lookup"><span data-stu-id="105ed-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="105ed-124">Fonctionnalités d’appel avancées</span><span class="sxs-lookup"><span data-stu-id="105ed-124">Advanced Calling Features</span></span>

<span data-ttu-id="105ed-125">Voix entreprise inclut plusieurs fonctionnalités d’appel avancées, telles que la délégation d’appels Lync, les appels d’équipe, la collecte d’appels de groupe et les groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="105ed-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="105ed-126">La délégation d’appel Lync permet aux utilisateurs de déléguer la gestion des appels à un ou plusieurs assistants, en accédant à **Outils** \> **options** \> de **transfert d’appel**.</span><span class="sxs-lookup"><span data-stu-id="105ed-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="105ed-127">Le délégué peut effectuer plusieurs tâches d’appel de la part de l’utilisateur, y compris les appels de filtrage, le placement d’appels et l’initiation de conférences.</span><span class="sxs-lookup"><span data-stu-id="105ed-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="105ed-128">Il est possible que vous souhaitiez Rechercher une autre fonctionnalité nommée de la même façon, délégation de calendrier Lync.</span><span class="sxs-lookup"><span data-stu-id="105ed-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="105ed-129">La fonctionnalité voix entreprise n’est pas obligatoire et permet aux utilisateurs de planifier des réunions Lync en ligne à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="105ed-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="105ed-130">Si vous recherchez ces informations, nous vous recommandons de consulter <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> pour plus d’informations sur l’activation de la synchronisation de délégué Exchange.</span><span class="sxs-lookup"><span data-stu-id="105ed-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="105ed-131">Les appels d’équipe permettent à un utilisateur de faire sonner simultanément les téléphones des membres de l’équipe pour que tous les membres de l’équipe puissent répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="105ed-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="105ed-132">Le prélèvement d’appels de groupe, une nouvelle fonctionnalité dans les mises à jour cumulatives de Lync Server 2013 : février 2013, permet aux utilisateurs de répondre aux appels entrants de leurs collègues à partir de leur propre téléphone.</span><span class="sxs-lookup"><span data-stu-id="105ed-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="105ed-133">Le prélèvement d’appels de groupe diffère de l’appel d’équipe dans la mesure où un appel entrant sonne uniquement sur le téléphone du destinataire prévu, mais que les autres utilisateurs peuvent choisir d’y répondre en composant un numéro de groupe.</span><span class="sxs-lookup"><span data-stu-id="105ed-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="105ed-134">Les groupes de réponse peuvent être configurés pour la mise en file d’attente et le routage intelligent des appels vers les agents désignés.</span><span class="sxs-lookup"><span data-stu-id="105ed-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="105ed-135">Les utilisations courantes incluent les support informatiques, les services d’assistance aux ressources humaines et autres centres de contacts internes.</span><span class="sxs-lookup"><span data-stu-id="105ed-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="105ed-136">Administration de voix entreprise</span><span class="sxs-lookup"><span data-stu-id="105ed-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="105ed-137">Lync Server utilise des normes et des interfaces publiées pour interagir avec l’infrastructure existante.</span><span class="sxs-lookup"><span data-stu-id="105ed-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="105ed-138">Il prend en charge les options passerelle et SIP (par exemple, le trunking SIP) pour une interconnexion aux systèmes PBX IP et aux réseaux RTC, afin que vous puissiez migrer les utilisateurs vers Enterprise Voice dans le temps, tout en minimisant les interruptions.</span><span class="sxs-lookup"><span data-stu-id="105ed-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="105ed-139">Lync Server prend en charge les codecs traditionnels tels que G. 711, G. 722 et G. 723.1 pour l’interopérabilité avec les solutions VoIP traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="105ed-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="105ed-140">Le contrôle d’admission des appels permet aux administrateurs de définir des limites sur le volume de trafic audio et vidéo de Lync Server transporté par des liaisons réseau contraintes et de spécifier l’action à entreprendre si un nouvel appel dépasse la limite.</span><span class="sxs-lookup"><span data-stu-id="105ed-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="105ed-141">Les actions peuvent inclure le routage via un autre chemin ou le rejet de l’appel.</span><span class="sxs-lookup"><span data-stu-id="105ed-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="105ed-142">Lync Server fonctionne avec des appareils de succursales Survivables tiers pour fournir des services d’appel local et une connexion RTC aux succursales, en cas de panne du WAN sur le site central.</span><span class="sxs-lookup"><span data-stu-id="105ed-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

