---
title: 'Lync Server 2013 : planification de la Conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b7f20857eded55c2488582c4b228bf0a53905c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ee86d-102">Planification de la Conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee86d-103">_**Dernière modification de la rubrique :** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="ee86d-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="ee86d-104">Lync Server 2013 offre un ensemble complet de fonctionnalités de conférence :</span><span class="sxs-lookup"><span data-stu-id="ee86d-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="ee86d-105">Conférence Web, qui inclut la collaboration sur des documents, le partage d’application et le partage de bureau.</span><span class="sxs-lookup"><span data-stu-id="ee86d-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="ee86d-106">Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ee86d-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="ee86d-107">Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ee86d-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="ee86d-108">Conférence audio/vidéo (A/V), qui permet aux utilisateurs d’effectuer des conférences audio ou vidéo en temps réel sans avoir besoin de recourir à des services externes, tels que le service Microsoft Live Meeting ou un pont audio tiers.</span><span class="sxs-lookup"><span data-stu-id="ee86d-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="ee86d-109">Conférence rendez-vous, qui permet aux utilisateurs de rejoindre la partie audio d’une conférence Lync Server 2013 à l’aide d’un téléphone RTC sans avoir besoin d’un fournisseur de services d’audioconférence tiers.</span><span class="sxs-lookup"><span data-stu-id="ee86d-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="ee86d-110">Conférence par messagerie instantanée, dans laquelle plus de deux parties communiquent dans une session de messagerie instantanée unique.</span><span class="sxs-lookup"><span data-stu-id="ee86d-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="ee86d-111">Pour plus d’informations sur les conférences de messagerie instantanée, voir [planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="ee86d-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="ee86d-112">Lync Server 2013 prend en charge les conférences planifiées et les conférences impromptues.</span><span class="sxs-lookup"><span data-stu-id="ee86d-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="ee86d-113">Lorsque vous déployez Lync Server 2013, serveur frontal, vous pouvez choisir de déployer également la conférence Web, la conférence A/V et les fonctionnalités de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="ee86d-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="ee86d-114">Les fonctionnalités de conférence par messagerie instantanée sont toujours déployées automatiquement avec les fonctionnalités de conversation par messagerie instantanée sur les serveurs frontaux Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee86d-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee86d-115">Si votre déploiement inclut des réunions organisées à l’aide de clients Office Communicator 2007 R2 (y compris la console Live Meeting ou le complément de conférence pour Microsoft Office Outlook), les limites suivantes seront appliquées après la migration vers Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="ee86d-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ee86d-116">Les utilisateurs de la réunion ne pourront pas utiliser les fonctionnalités de collaboration de données, notamment la collaboration sur les documents, le partage d’application et le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="ee86d-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="ee86d-117">Des problèmes de stabilité peuvent survenir, car les clients Office Communicator 2007 R2 ne sont pas pris en charge avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee86d-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="ee86d-118">Pour éviter ces problèmes, replanifiez toutes les réunions organisées à l’aide de clients Office Communicator 2007 R2 avec Outlook 2010 ou Outlook 2013 en utilisant le complément de réunion en ligne pour Lync 2010 ou le complément de réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ee86d-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="ee86d-119">Les sections suivantes décrivent les éléments nécessaires au déploiement des différents types de fonctionnalités de conférence, dont le processus de planification, les composants, la configuration matérielle et logicielle requise, ainsi que le processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ee86d-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee86d-120">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ee86d-120">In This Section</span></span>

  - [<span data-ttu-id="ee86d-121">Vue d’ensemble des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="ee86d-122">Définition de la configuration requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="ee86d-123">Composants et topologies pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="ee86d-124">Configuration technique requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="ee86d-125">Liste de vérification du déploiement pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="ee86d-126">Prise en charge des grandes réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee86d-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

