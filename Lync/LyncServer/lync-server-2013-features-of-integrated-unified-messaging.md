---
title: 'Lync Server 2013 : fonctionnalités de la messagerie unifiée intégrée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55da4422ec0151ddc6638ea21b4a5e1c551541ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="25816-102">Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25816-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25816-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="25816-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="25816-104">Lync Server 2013, voix entreprise utilise l’infrastructure de messagerie unifiée Exchange pour fournir des services de répondeur automatique, de notification d’appel, d’accès vocal (y compris la messagerie vocale) et de services de standard automatique.</span><span class="sxs-lookup"><span data-stu-id="25816-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="25816-105">Répondeur automatique</span><span class="sxs-lookup"><span data-stu-id="25816-105">Call Answering</span></span>

<span data-ttu-id="25816-106">Le répondeur automatique est la réception de messages vocaux pour le compte des utilisateurs dont les appels ne sont pas traités ou qui sont occupés.</span><span class="sxs-lookup"><span data-stu-id="25816-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="25816-107">Elle inclut la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message pour être mis en file d’attente pour remise à la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="25816-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="25816-p102">Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est stockée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.</span><span class="sxs-lookup"><span data-stu-id="25816-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="25816-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="25816-112">Outlook Voice Access</span></span>

<span data-ttu-id="25816-113">Outlook Voice Access permet à un utilisateur de Voix Entreprise d’accéder non seulement à la messagerie vocale, mais également à la boîte de réception Exchange, y compris à la messagerie électronique, au calendrier et aux contacts à partir d’une interface de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="25816-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="25816-114">Le numéro d’accès abonné est affecté par un administrateur de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="25816-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="25816-115">Standard automatique</span><span class="sxs-lookup"><span data-stu-id="25816-115">Auto Attendant</span></span>

<span data-ttu-id="25816-116">Le standard automatique est une fonctionnalité de messagerie unifiée Exchange qui permet de configurer un numéro de téléphone que les utilisateurs externes peuvent composer pour atteindre les représentants d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="25816-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="25816-117">Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus.</span><span class="sxs-lookup"><span data-stu-id="25816-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="25816-118">La liste des options disponibles est configurée sur le serveur de messagerie unifiée Exchange par l’administrateur de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="25816-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="25816-119">Services de télécopie</span><span class="sxs-lookup"><span data-stu-id="25816-119">Fax Services</span></span>

<span data-ttu-id="25816-120">La messagerie unifiée Exchange inclut des fonctionnalités de télécopie, qui permettent aux utilisateurs de recevoir des télécopies entrantes dans leurs boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="25816-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="25816-121">Pour plus d’informations, reportez-vous à la rubrique « messagerie [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652)unifiée » dans la documentation de Microsoft Exchange Server à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="25816-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25816-122">Les services de télécopie fournis par le serveur de messagerie unifiée Exchange ne sont pas disponibles dans les déploiements Lync Server qui sont intégrés à Microsoft Exchange Server 2010, Exchange 2010 avec le Service Pack le plus récent ou Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="25816-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

