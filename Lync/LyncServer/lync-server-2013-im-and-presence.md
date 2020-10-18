---
title: Messagerie instantanée et présence de Lync Server 2013
description: Messagerie instantanée et présence de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d04f0ee6decc03db1a6b5aa44cfedd7515c2d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573280"
---
# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="4c69f-103">Messagerie instantanée et présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c69f-103">IM and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c69f-104">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="4c69f-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="4c69f-105">La messagerie instantanée et la présence sont automatiquement installées dans n’importe quel déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c69f-105">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="4c69f-106">Les informations de *présence* permettent aux utilisateurs de contacter leurs collègues au bon moment et avec le bon mode de communication, et d’augmenter ainsi la productivité au sein de leur environnement de travail.</span><span class="sxs-lookup"><span data-stu-id="4c69f-106">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="4c69f-107">La présence d’un utilisateur est un ensemble d’informations qui incluent la disponibilité, la volonté de communiquer, des remarques supplémentaires (comme le lieu et le statut), ainsi que la façon dont l’utilisateur peut être contacté.</span><span class="sxs-lookup"><span data-stu-id="4c69f-107">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="4c69f-108">La présence est améliorée dans Lync Server avec des images, des informations d’emplacement et un ensemble complet d’États de présence, qui incluent les États de base tels que « disponible », « de «ne pas déranger » et « revenons » dans une conférence».</span><span class="sxs-lookup"><span data-stu-id="4c69f-108">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="4c69f-109">Les administrateurs peuvent aussi définir des états de présence personnalisés et spécifiques à l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4c69f-109">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="4c69f-p102">Les options de gestion des contacts et d’accès utilisateur permettent aux utilisateurs de contrôler les informations que les autres personnes peuvent consulter. Les utilisateurs peuvent définir différents niveaux de contacts, chacun d’eux pouvant afficher différents niveaux d’informations de présence.</span><span class="sxs-lookup"><span data-stu-id="4c69f-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="4c69f-p103">En effectuant simplement une recherche dans une liste de contacts, les utilisateurs peuvent trouver immédiatement tout ce dont ils ont besoin. Les icônes de couleur simples indiquent le statut de présence des autres utilisateurs, et l’image et le lieu sont également affichés.</span><span class="sxs-lookup"><span data-stu-id="4c69f-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="4c69f-114">Avec l’intégration entre Lync Server et d’autres produits tels qu’Outlook et SharePoint, lorsque le nom d’un contact apparaît, par exemple dans un message électronique ou sur un site Web d’équipe, l’État et les informations de contact sont également affichés.</span><span class="sxs-lookup"><span data-stu-id="4c69f-114">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="4c69f-115">En outre, si vous déployez Exchange 2013, Lync Server et Exchange 2013 peuvent partager un magasin de contacts unifié, qui est accessible par les clients de l’un ou l’autre produit.</span><span class="sxs-lookup"><span data-stu-id="4c69f-115">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="4c69f-116">Avec la messagerie instantanée dans Lync Server, les utilisateurs peuvent rapidement s’afficher avec des informations opportunes.</span><span class="sxs-lookup"><span data-stu-id="4c69f-116">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="4c69f-117">Si vous le souhaitez, vos utilisateurs peuvent également communiquer avec des utilisateurs de réseaux de messagerie instantanée publics, tels que MSN/Windows Live, Yahoo \! et AOL.</span><span class="sxs-lookup"><span data-stu-id="4c69f-117">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="4c69f-118">Notez qu’une licence distincte peut être requise pour la connectivité PIC avec Windows Live, AOL et Yahoo.\!</span><span class="sxs-lookup"><span data-stu-id="4c69f-118">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="4c69f-119">Lync Server inclut également la compatibilité XMPP (extensible Messaging and Presence Protocol), afin que vos utilisateurs puissent échanger des messages INSTANTANÉs et des informations de présence avec des utilisateurs de services XMPP tels que Google Talk.</span><span class="sxs-lookup"><span data-stu-id="4c69f-119">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4c69f-120">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="4c69f-120">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="4c69f-121">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="4c69f-121">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="4c69f-122">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="4c69f-122">Messenger until the service shut down date.</span></span> <span data-ttu-id="4c69f-123">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="4c69f-123">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="4c69f-124">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="4c69f-124">has been announced.</span></span> <span data-ttu-id="4c69f-125">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4c69f-125">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="4c69f-126">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="4c69f-126">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="4c69f-127">Messenger.</span><span class="sxs-lookup"><span data-stu-id="4c69f-127">Messenger.</span></span> <span data-ttu-id="4c69f-128">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="4c69f-128">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="4c69f-129">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="4c69f-129">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="4c69f-130">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="4c69f-130">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="4c69f-131">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="4c69f-131">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4c69f-132">L’historique des conversations permet aux utilisateurs de conserver les anciennes conversations de messagerie instantanée et de récupérer des informations qui ont pu être transmises par messagerie instantanée plusieurs mois auparavant.</span><span class="sxs-lookup"><span data-stu-id="4c69f-132">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="4c69f-133">La fonctionnalité de conversation permanente permet aux utilisateurs de participer à des conversations à plusieurs sujets qui persistent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="4c69f-133">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="4c69f-134">Les messages publiés dans les salles de conversation (forums de discussion) peuvent être permanents, afin que les personnes qui se trouvent dans des sites et départements différents puissent participer, même lorsqu’elles ne sont pas toutes en ligne en même temps.</span><span class="sxs-lookup"><span data-stu-id="4c69f-134">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="4c69f-135">Si votre organisation doit respecter des réglementations en matière de conformité, vous pouvez déployer une fonctionnalité d’archivage des messages, afin d’archiver le contenu des messages instantanés pour tous les utilisateurs de votre organisation ou seulement pour certains utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="4c69f-135">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="4c69f-136">Si vous déployez également Exchange 2013, votre archive de messagerie instantanée peut être intégrée à la fonctionnalité de mise en attente de In-Place d’Exchange, afin de fournir une expérience d’administration unique pour votre conformité.</span><span class="sxs-lookup"><span data-stu-id="4c69f-136">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

