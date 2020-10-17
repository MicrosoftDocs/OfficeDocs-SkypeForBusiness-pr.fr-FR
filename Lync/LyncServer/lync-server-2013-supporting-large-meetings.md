---
title: 'Lync Server 2013 : prise en charge des grandes réunions'
description: 'Lync Server 2013 : prise en charge des grandes réunions.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e116f4668c37fd26eea5cec322a8c6483385e7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554780"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="d4f9d-103">Prise en charge des grandes réunions à l’aide de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f9d-103">Supporting large meetings using Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f9d-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d4f9d-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d4f9d-105">Les réunions de grande taille ne suivent pas le modèle de test décrit dans la section précédente, car elles ont les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d4f9d-105">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="d4f9d-106">Le format de la réunion est celui d’une présentation un-à-plusieurs.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-106">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="d4f9d-107">Un ou plusieurs utilisateurs constituent les présentateurs. Le reste de l’assistance constitue les participants.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-107">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="d4f9d-108">Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-108">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="d4f9d-109">L’audio est nécessaire et la vidéo peut également être utilisée.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-109">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="d4f9d-110">Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, prépare la réunion à l’avance.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-110">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="d4f9d-111">Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-111">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="d4f9d-112">La prise en charge de réunions de grande taille incluant jusqu’à 1 000 utilisateurs nécessite de régler les aspects liés au modèle matériel partagé et au modèle d’absence de réservation.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-112">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="d4f9d-113">Pour disposer de ressources d’UC et de mémoire suffisantes pour les réunions allant jusqu’à 1000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas héberger de messagerie instantanée et de présence ou de charges de travail voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-113">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="d4f9d-114">Ils ne doivent pas non plus héberger d’autres réunions, quelles que soient leurs tailles.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-114">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="d4f9d-115">Cela signifie que l’hébergement de réunions allant jusqu’à 1000 utilisateurs nécessite la mise en place d’un pool Lync Server distinct dédié à l’hébergement de grandes réunions allant jusqu’à 1000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-115">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="d4f9d-116">Un pool Lync Server dédié à l’hébergement de grandes réunions ne doit héberger qu’une seule réunion d’un maximum de 1000 utilisateurs en même temps, de sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors bande pour garantir un support dédié à partir des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-116">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="d4f9d-117">Pour prendre en charge plusieurs grandes réunions en même temps, nous vous recommandons de configurer plusieurs pools de réunions de grande taille dédiés.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-117">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="d4f9d-p103">Nous vous recommandons de dédier une personne à la conduite et au contrôle de la partie en ligne d’une réunion de grande taille. Cette personne peut être l’organisateur, un assistant de l’organisateur ou du présentateur, ou bien un membre de l’équipe de support technique dédiée aux réunions de grande taille, en fonction des préférences de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="d4f9d-120">Dans les sections suivantes, nous décrivons comment implémenter un pool dédié pour les grandes réunions, notamment les meilleures pratiques pour l’utilisation de Lync Server 2013 afin de prendre en charge les grands scénarios de réunion.</span><span class="sxs-lookup"><span data-stu-id="d4f9d-120">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4f9d-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d4f9d-121">In This Section</span></span>

  - [<span data-ttu-id="d4f9d-122">Configuration de la prise en charge des grandes réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f9d-122">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="d4f9d-123">Gestion des grandes réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f9d-123">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

