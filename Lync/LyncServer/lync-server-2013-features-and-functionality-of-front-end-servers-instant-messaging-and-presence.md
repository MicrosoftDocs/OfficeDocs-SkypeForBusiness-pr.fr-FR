---
title: 'Lync Server 2013 : fonctionnalités des serveurs frontaux, de la messagerie instantanée et de la présence'
description: 'Lync Server 2013 : caractéristiques et fonctionnalités des serveurs frontaux, de la messagerie instantanée et de la présence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c8bc3db255228da3366eb5aa142cd5adc233d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543410"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="b3986-103">Fonctionnalités des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3986-103">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3986-104">_**Dernière modification de la rubrique :** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="b3986-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="b3986-105">Les serveurs frontaux fournissent la plupart des fonctionnalités Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3986-105">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="b3986-106">Deux éditions sont disponibles : Lync Server Enterprise Edition, conçu principalement pour les grandes organisations et Lync Server Standard Edition, conçu principalement pour les organisations de petite taille qui souhaitent un investissement matériel réduit et ne nécessitent pas de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b3986-106">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="b3986-107">Les deux éditions prennent en charge toutes les charges de travail Lync Server, y compris la messagerie instantanée, la présence, les conférences et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="b3986-107">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="b3986-p102">La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels.. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="b3986-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b3986-112">Les clients Lync et Communicator impliqués dans une communication une vers une, sont souvent appelés P2P (peer-to-peer).</span><span class="sxs-lookup"><span data-stu-id="b3986-112">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="b3986-113">Techniquement, les deux clients communiquent dans une conversation une à une, avec l’unité de contrôle multipoint de messagerie instantanée (IMMCU) au milieu.</span><span class="sxs-lookup"><span data-stu-id="b3986-113">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="b3986-114">Le IMMCU est un composant de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b3986-114">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="b3986-115">La mise en place du IMMCU dans le flux de travail de communication requis permet l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b3986-115">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="b3986-116">La communication provient d’un port source dynamique sur le client vers le port de serveur frontal TLS/TCP/5061 (en supposant l’utilisation de la sécurité de la couche de transport recommandée).</span><span class="sxs-lookup"><span data-stu-id="b3986-116">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="b3986-117">Par conception, la communication P2P (ainsi que la messagerie instantanée multipartie) n’est possible que lorsque Lync Server et le IMMCU sont actifs et disponibles.</span><span class="sxs-lookup"><span data-stu-id="b3986-117">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="b3986-118">La *présence* fournit aux utilisateurs des informations sur l’état de présence des autres utilisateurs sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="b3986-118">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="b3986-119">Le statut de présence d’un utilisateur fournit des informations pour permettre aux autres utilisateurs de décider s’ils doivent essayer de contacter l’utilisateur et s’ils doivent pour cela utiliser la messagerie instantanée, le téléphone ou la messagerie électronique.</span><span class="sxs-lookup"><span data-stu-id="b3986-119">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="b3986-120">La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="b3986-120">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="b3986-121">Cet état de présence est affiché sous la forme d’une icône de présence dans Lync et d’autres applications prenant en charge la présence, y compris le client de messagerie et de collaboration Microsoft Outlook, les technologies Microsoft SharePoint, Microsoft Word et le logiciel de feuille de calcul Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b3986-121">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="b3986-122">L’icône de présence indique la disponibilité actuelle de l’utilisateur et sa volonté à communiquer.</span><span class="sxs-lookup"><span data-stu-id="b3986-122">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

