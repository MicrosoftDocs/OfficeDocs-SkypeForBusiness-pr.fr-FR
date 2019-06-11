---
title: Messagerie instantanée et présence dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18eb3d4a7fa5daaa59817d2eefde7af3a8e3f494
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="f62f6-102">Messagerie instantanée et présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f62f6-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f62f6-103">_**Dernière modification de la rubrique:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f62f6-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f62f6-104">La messagerie instantanée et la présence sont automatiquement installés dans n’importe quel déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f62f6-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="f62f6-105">Les informations de *présence* permettent aux utilisateurs d’aborder les collègues au moment le plus opportun avec le bon moyen de communication, afin d’améliorer l’environnement de bureau.</span><span class="sxs-lookup"><span data-stu-id="f62f6-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="f62f6-106">La présence d’un utilisateur est une collection d’informations qui inclut la disponibilité, la volonté de communiquer, des notes supplémentaires (par exemple, l’emplacement et le statut) et la façon dont l’utilisateur peut être contacté.</span><span class="sxs-lookup"><span data-stu-id="f62f6-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="f62f6-107">La présence est améliorée dans Lync Server avec des images, des informations de géolocalisation et un ensemble complet d’États de présence incluant «arrêt du fonctionnement», «ne pas déranger» et «revenir de nouveau», en plus des États de base tels que «disponible», «occupé» et «en réunion».</span><span class="sxs-lookup"><span data-stu-id="f62f6-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="f62f6-108">Les administrateurs peuvent également définir des États de présence spécifiques de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="f62f6-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="f62f6-109">La gestion des contacts et les options d’accès des utilisateurs permettent aux utilisateurs de contrôler les informations qu’ils peuvent afficher.</span><span class="sxs-lookup"><span data-stu-id="f62f6-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="f62f6-110">Les utilisateurs peuvent définir différents niveaux de contacts, qui peuvent chacun afficher différents niveaux d’informations de présence.</span><span class="sxs-lookup"><span data-stu-id="f62f6-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="f62f6-111">La consultation d’une liste de contacts permet aux utilisateurs de trouver en un clin d’œil les informations dont ils ont besoin.</span><span class="sxs-lookup"><span data-stu-id="f62f6-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="f62f6-112">Les icônes de couleur simples indiquent le statut de présence d’autres utilisateurs et l’image et l’emplacement sont également affichés.</span><span class="sxs-lookup"><span data-stu-id="f62f6-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="f62f6-113">L’intégration de Lync Server à d’autres produits tels qu’Outlook et SharePoint, chaque fois que le nom d’un contact apparaît (par exemple, dans un message électronique ou sur un site Web d’équipe), les informations de statut et de contact sont également affichées.</span><span class="sxs-lookup"><span data-stu-id="f62f6-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="f62f6-114">Par ailleurs, si vous déployez Exchange 2013, Lync Server et Exchange 2013 peuvent partager un magasin de contacts unifié, lequel est accessible à tous les clients de chaque produit.</span><span class="sxs-lookup"><span data-stu-id="f62f6-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="f62f6-115">Avec la messagerie instantanée dans Lync Server, les utilisateurs peuvent s’échanger rapidement des messages avec des informations opportunes.</span><span class="sxs-lookup"><span data-stu-id="f62f6-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="f62f6-116">Si vous le souhaitez, vos utilisateurs peuvent également communiquer avec les utilisateurs de réseaux de messagerie instantanée publics tels que MSN/\!Windows Live, Yahoo et AOL.</span><span class="sxs-lookup"><span data-stu-id="f62f6-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="f62f6-117">Notez qu’une licence distincte peut être nécessaire pour la connectivité de messagerie instantanée publique avec Windows Live, AOL et Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="f62f6-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="f62f6-118">Lync Server inclut également la compatibilité de l’extensibilité du protocole et de la messagerie instantanée, afin que vos utilisateurs puissent échanger des messages instantanés et des informations de présence avec des utilisateurs de services XMPP tels que Google Talk.</span><span class="sxs-lookup"><span data-stu-id="f62f6-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f62f6-119">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="f62f6-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f62f6-120">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f62f6-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f62f6-121">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="f62f6-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="f62f6-122">Date de fin de vie du 2014 juin pour AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f62f6-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f62f6-123">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="f62f6-123">has been announced.</span></span> <span data-ttu-id="f62f6-124">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f62f6-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f62f6-125">La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f62f6-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f62f6-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f62f6-126">Messenger.</span></span> <span data-ttu-id="f62f6-127">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</span><span class="sxs-lookup"><span data-stu-id="f62f6-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f62f6-128">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="f62f6-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f62f6-129">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="f62f6-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f62f6-130">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="f62f6-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f62f6-131">L’historique des conversations permet aux utilisateurs d’effectuer le suivi d’anciennes conversations par messagerie instantanée et de récupérer des informations qui peuvent avoir été communiquées par des mois de mi auparavant.</span><span class="sxs-lookup"><span data-stu-id="f62f6-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="f62f6-132">La fonctionnalité de conversation permanente permet aux utilisateurs de participer à des conversations à plusieurs sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="f62f6-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="f62f6-133">Les messages publiés dans des salles de conversation (forums de discussion) peuvent être persistants (disponible dans le temps), de sorte que les personnes de différents sites et services peuvent participer, même s’ils ne sont pas en ligne en même temps.</span><span class="sxs-lookup"><span data-stu-id="f62f6-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="f62f6-134">Si votre organisation doit suivre des règles de conformité, vous pouvez déployer une fonctionnalité d’archivage des messages pour archiver le contenu des messages instantanés pour tous les utilisateurs de votre organisation, ou uniquement pour certains utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="f62f6-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="f62f6-135">Si vous déployez également Exchange 2013, votre archive de messagerie instantanée peut être intégrée à la fonctionnalité de conservation inaltérable d’Exchange, afin de fournir une interface d’administration unique pour votre conformité.</span><span class="sxs-lookup"><span data-stu-id="f62f6-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

