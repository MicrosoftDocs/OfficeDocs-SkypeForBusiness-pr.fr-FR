---
title: 'Lync Server 2013 : planification du contrôle d’appel distant'
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
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="0306e-102">Planification du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0306e-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0306e-103">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="0306e-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="0306e-104">Dans Lync Server 2013, la prise en charge des scénarios de contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX en utilisant Lync 2013 sur leur ordinateur de bureau.</span><span class="sxs-lookup"><span data-stu-id="0306e-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="0306e-105">Cette section décrit les fonctionnalités de contrôle d’appel distant et la configuration requise pour le déploiement du contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="0306e-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="0306e-106">L’intégration entre un système PBX et Lync Server 2013 permet aux utilisateurs ayant activé le contrôle d’appel distant d’utiliser l’interface utilisateur de Lync 2013 pour contrôler les appels sur leurs téléphones PBX comme suit :</span><span class="sxs-lookup"><span data-stu-id="0306e-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0306e-107">Enfin, les fonctionnalités du PBX qui héberge le téléphone PBX d’un utilisateur déterminent les fonctionnalités de contrôle d’appel distant qui seront disponibles pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0306e-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="0306e-108">Passer un appel sortant</span><span class="sxs-lookup"><span data-stu-id="0306e-108">Make an outgoing call</span></span>

  - <span data-ttu-id="0306e-109">Répondre à un appel entrant</span><span class="sxs-lookup"><span data-stu-id="0306e-109">Answer an incoming call</span></span>

  - <span data-ttu-id="0306e-110">Réponse à un appel entrant avec un message instantané</span><span class="sxs-lookup"><span data-stu-id="0306e-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0306e-111">En d’autres termes, lorsque le numéro de téléphone de l’appelant peut être associé à une adresse de messagerie instantanée dans la liste d’adresses globale de votre organisation, dans la liste de contacts Lync du destinataire, ou dans une organisation de partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="0306e-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="0306e-112">Transférer un appel</span><span class="sxs-lookup"><span data-stu-id="0306e-112">Transfer a call</span></span>

  - <span data-ttu-id="0306e-113">Transférer un appel entrant</span><span class="sxs-lookup"><span data-stu-id="0306e-113">Forward an incoming call</span></span>

  - <span data-ttu-id="0306e-114">Bloquer les appels</span><span class="sxs-lookup"><span data-stu-id="0306e-114">Place calls on hold</span></span>

  - <span data-ttu-id="0306e-115">Alterner entre plusieurs appels simultanés</span><span class="sxs-lookup"><span data-stu-id="0306e-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="0306e-116">Répondre à un deuxième appel alors qu’il est déjà en cours d’appel (en attente d’appel)</span><span class="sxs-lookup"><span data-stu-id="0306e-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="0306e-117">Composer un numéro à deux tonalités (DTMF)</span><span class="sxs-lookup"><span data-stu-id="0306e-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="0306e-118">Dans la fenêtre de conversation, tapez des notes dans le programme de prises de notes Microsoft Office OneNote</span><span class="sxs-lookup"><span data-stu-id="0306e-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="0306e-119">En outre, lorsqu’un utilisateur est activé pour le contrôle d’appel distant, Lync 2013 fournit les informations d’appel suivantes :</span><span class="sxs-lookup"><span data-stu-id="0306e-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="0306e-120">Identification d’un appelant par son nom lorsque le numéro de téléphone de l’appelant figure dans la liste des contacts d’un client de messagerie et de collaboration Microsoft Office Outlook prenant en charge la gestion des appels distants, liste de contacts Lync ou GAL de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0306e-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="0306e-121">Avez passé les appels entrants et sortants, qui sont enregistrés dans le dossier historique des conversations dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="0306e-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="0306e-122">Les notifications d’appels manqués, qui sont envoyées au dossier de la boîte de réception Outlook de l’utilisateur, mais qui sont générées uniquement si Lync est en cours d’exécution lors de la réception de l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="0306e-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="0306e-123">Contrôle d’appel distant et voix entreprise</span><span class="sxs-lookup"><span data-stu-id="0306e-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="0306e-124">Bien que les fonctionnalités de contrôle d’appel distant soient distinctes des fonctions vocales d’entreprise et que les utilisateurs ne peuvent pas être activés pour les deux, Enterprise Voice fournit un sous-ensemble de fonctionnalités qui sont également disponibles pour les utilisateurs disposant d’un contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="0306e-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="0306e-125">Si Enterprise Voice est déployé, les utilisateurs dotés du contrôle d’appel distant peuvent utiliser Lync pour accéder aux fonctions vocales d’entreprise suivantes :</span><span class="sxs-lookup"><span data-stu-id="0306e-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="0306e-126">Passer et recevoir des appels audio vers un autre client Lync</span><span class="sxs-lookup"><span data-stu-id="0306e-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="0306e-127">Rejoindre la partie audio d’une conférence créée par un utilisateur activé pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="0306e-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0306e-128">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0306e-128">In This Section</span></span>

  - [<span data-ttu-id="0306e-129">Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0306e-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

