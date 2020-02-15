---
title: 'Lync Server 2013 : prise en charge de la messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590fa404e614ce02832239879353e22fd95ff47f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="39aa5-102">Prise en charge de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39aa5-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39aa5-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="39aa5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="39aa5-104">Lync Server 2013 prend en charge l’utilisation de fournisseurs de connectivité de messagerie instantanée publique sous licence, ainsi que l’utilisation du protocole XMPP (eXtensible Messaging and Presence Protocol) pour mettre en œuvre un type spécial de Fédération qui permet à un serveur Lync d’accéder à XMPP configurée partenaires de domaine à l’aide du client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="39aa5-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="39aa5-105">Prise en charge des fournisseurs de services de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="39aa5-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="39aa5-106">Les partenaires de connectivité PIC (Public Instant Messaging) actuellement pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="39aa5-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="39aa5-107">America Online</span><span class="sxs-lookup"><span data-stu-id="39aa5-107">America Online</span></span>

  - <span data-ttu-id="39aa5-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="39aa5-108">Windows Live</span></span>

  - <span data-ttu-id="39aa5-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="39aa5-109">Yahoo\!</span></span>

<span data-ttu-id="39aa5-110">Pour les communications avec les utilisateurs de Windows Live, Lync Server 2013 prend en charge les appels audio et vidéo d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="39aa5-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="39aa5-111">Pour les communications avec AOL et\!Yahoo, Lync Server 2013 prend en charge la messagerie instantanée P2P.</span><span class="sxs-lookup"><span data-stu-id="39aa5-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="39aa5-112">Une licence distincte peut être nécessaire.</span><span class="sxs-lookup"><span data-stu-id="39aa5-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="39aa5-113">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="39aa5-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="39aa5-114">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="39aa5-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="39aa5-115">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="39aa5-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="39aa5-116">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="39aa5-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="39aa5-117">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="39aa5-117">has been announced.</span></span> <span data-ttu-id="39aa5-118">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="39aa5-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="39aa5-119">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="39aa5-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="39aa5-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="39aa5-120">Messenger.</span></span> <span data-ttu-id="39aa5-121">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="39aa5-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="39aa5-122">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="39aa5-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="39aa5-123">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="39aa5-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="39aa5-124">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="39aa5-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="39aa5-125">Prise en charge de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="39aa5-125">XMPP Federation Support</span></span>

<span data-ttu-id="39aa5-p105">La fédération XMPP prend en charge la communication des utilisateurs Lync avec les utilisateurs du domaine XMPP configuré qui utilisent un fournisseur public, tel que GTalk. Les communications avec ces utilisateurs peuvent inclure :</span><span class="sxs-lookup"><span data-stu-id="39aa5-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="39aa5-128">la messagerie instantanée d’égal à égal et la présence ;</span><span class="sxs-lookup"><span data-stu-id="39aa5-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="39aa5-129">la création de contacts XMPP fédérés dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="39aa5-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

