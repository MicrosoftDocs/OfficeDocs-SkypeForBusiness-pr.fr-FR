---
title: 'Lync Server 2013 : planification du contrôle d’appel distant'
description: 'Lync Server 2013 : planification du contrôle d’appel distant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a089a806683098a948d235559bbcb16224bdde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564690"
---
# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="66935-103">Planification du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66935-103">Planning for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66935-104">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="66935-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="66935-105">Dans Lync Server 2013, la prise en charge des scénarios de contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX (Private Branch Exchange) à l’aide de Lync 2013 sur leurs ordinateurs de bureau.</span><span class="sxs-lookup"><span data-stu-id="66935-105">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="66935-106">Cette section décrit les fonctionnalités de contrôle d’appel distant et les conditions nécessaires au déploiement du contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="66935-106">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="66935-107">L’intégration entre un PBX et Lync Server 2013 permet aux utilisateurs activés pour le contrôle d’appel distant d’utiliser l’interface utilisateur de Lync 2013 pour contrôler les appels sur leurs téléphones PBX des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="66935-107">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66935-108">En définitive, les capacités de l’autocommutateur privé (PBX) qui héberge le téléphone PBX d’un utilisateur déterminent les fonctionnalités de contrôle d’appel distant qui sont mises à la disposition de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66935-108">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="66935-109">Passer un appel sortant</span><span class="sxs-lookup"><span data-stu-id="66935-109">Make an outgoing call</span></span>

  - <span data-ttu-id="66935-110">Répondre à un appel entrant</span><span class="sxs-lookup"><span data-stu-id="66935-110">Answer an incoming call</span></span>

  - <span data-ttu-id="66935-111">Répondre à un appel entrant avec un message instantané</span><span class="sxs-lookup"><span data-stu-id="66935-111">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66935-112">C’est-à-dire, lorsque le numéro de téléphone de l’appelant peut être associé à une adresse de messagerie instantanée dans la liste d’adresses globale de votre organisation, dans la liste des contacts Lync de l’appelé ou dans l’organisation d’un partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="66935-112">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="66935-113">Transférer un appel</span><span class="sxs-lookup"><span data-stu-id="66935-113">Transfer a call</span></span>

  - <span data-ttu-id="66935-114">Transférer un appel entrant</span><span class="sxs-lookup"><span data-stu-id="66935-114">Forward an incoming call</span></span>

  - <span data-ttu-id="66935-115">Mettre des appels en attente</span><span class="sxs-lookup"><span data-stu-id="66935-115">Place calls on hold</span></span>

  - <span data-ttu-id="66935-116">Basculer entre plusieurs appels simultanés</span><span class="sxs-lookup"><span data-stu-id="66935-116">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="66935-117">Répondre à un deuxième appel pendant un appel en cours (c’est-à-dire, mise en attente d’un appel)</span><span class="sxs-lookup"><span data-stu-id="66935-117">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="66935-118">Composer des chiffres de numérotation en fréquences vocales (DTMF)</span><span class="sxs-lookup"><span data-stu-id="66935-118">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="66935-119">Dans la fenêtre de conversation, taper des notes dans le programme de prise de note Microsoft Office OneNote</span><span class="sxs-lookup"><span data-stu-id="66935-119">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="66935-120">De plus, lorsqu’un utilisateur est activé pour le contrôle d’appel distant, Lync 2013 fournit les informations d’appel suivantes :</span><span class="sxs-lookup"><span data-stu-id="66935-120">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="66935-121">Identification d’un appelant par son nom lorsque le numéro de téléphone de l’appelant existe dans la liste des contacts d’un client de messagerie et de collaboration Microsoft Office Outlook de l’utilisateur à extension à distance, liste de contacts Lync ou liste d’adresses globale de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="66935-121">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="66935-122">Appels entrants et sortants précédents, qui sont enregistrés dans le dossier Historique des conversations d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="66935-122">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="66935-123">Les notifications d’appels manqués, qui sont envoyées au dossier boîte de réception Outlook de l’utilisateur, mais sont générées uniquement si Lync est en cours d’exécution lors de la réception de l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="66935-123">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="66935-124">Contrôle d’appel distant et Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="66935-124">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="66935-125">Bien que les fonctionnalités de contrôle d’appel distant soient distinctes des fonctionnalités voix entreprise et que les utilisateurs ne puissent pas les activer, voix entreprise fournit un sous-ensemble de fonctionnalités également accessibles aux utilisateurs activés pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="66935-125">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="66935-126">Si Enterprise Voice est déployé, les utilisateurs qui sont activés pour le contrôle d’appel distant peuvent utiliser Lync pour accéder aux fonctionnalités voix entreprise suivantes :</span><span class="sxs-lookup"><span data-stu-id="66935-126">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="66935-127">Passer et recevoir des appels audio vers un autre client Lync</span><span class="sxs-lookup"><span data-stu-id="66935-127">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="66935-128">Joindre la partie audio d’une conférence créée par un utilisateur qui est activé pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="66935-128">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="66935-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="66935-129">In This Section</span></span>

  - [<span data-ttu-id="66935-130">Tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66935-130">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

