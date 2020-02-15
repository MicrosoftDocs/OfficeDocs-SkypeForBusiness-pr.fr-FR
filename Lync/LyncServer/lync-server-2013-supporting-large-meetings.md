---
title: 'Lync Server 2013 : prise en charge des grandes réunions'
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
ms.openlocfilehash: 73c9a5d2ad4688f622298378c84b61574048a3b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="6dd15-102">Prise en charge des grandes réunions à l’aide de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd15-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd15-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6dd15-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6dd15-104">Les réunions de grande taille ne suivent pas le modèle de test décrit dans la section précédente, car elles ont les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dd15-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="6dd15-105">Le format de la réunion est celui d’une présentation un-à-plusieurs.</span><span class="sxs-lookup"><span data-stu-id="6dd15-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="6dd15-106">Un ou plusieurs utilisateurs constituent les présentateurs. Le reste de l’assistance constitue les participants.</span><span class="sxs-lookup"><span data-stu-id="6dd15-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="6dd15-107">Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.</span><span class="sxs-lookup"><span data-stu-id="6dd15-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="6dd15-108">L’audio est nécessaire et la vidéo peut également être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6dd15-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="6dd15-109">Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, prépare la réunion à l’avance.</span><span class="sxs-lookup"><span data-stu-id="6dd15-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="6dd15-110">Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6dd15-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="6dd15-111">La prise en charge de réunions de grande taille incluant jusqu’à 1 000 utilisateurs nécessite de régler les aspects liés au modèle matériel partagé et au modèle d’absence de réservation.</span><span class="sxs-lookup"><span data-stu-id="6dd15-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="6dd15-112">Pour disposer de ressources d’UC et de mémoire suffisantes pour les réunions allant jusqu’à 1000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas héberger de messagerie instantanée et de présence ou de charges de travail voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="6dd15-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="6dd15-113">Ils ne doivent pas non plus héberger d’autres réunions, quelles que soient leurs tailles.</span><span class="sxs-lookup"><span data-stu-id="6dd15-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="6dd15-114">Cela signifie que l’hébergement de réunions allant jusqu’à 1000 utilisateurs nécessite la mise en place d’un pool Lync Server distinct dédié à l’hébergement de grandes réunions allant jusqu’à 1000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6dd15-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="6dd15-115">Un pool Lync Server dédié à l’hébergement de grandes réunions ne doit héberger qu’une seule réunion d’un maximum de 1000 utilisateurs en même temps, de sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors bande pour garantir un support dédié à partir du service frontal Soft.</span><span class="sxs-lookup"><span data-stu-id="6dd15-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="6dd15-116">Pour prendre en charge plusieurs grandes réunions en même temps, nous vous recommandons de configurer plusieurs pools de réunions de grande taille dédiés.</span><span class="sxs-lookup"><span data-stu-id="6dd15-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="6dd15-p103">Nous vous recommandons de dédier une personne à la conduite et au contrôle de la partie en ligne d’une réunion de grande taille. Cette personne peut être l’organisateur, un assistant de l’organisateur ou du présentateur, ou bien un membre de l’équipe de support technique dédiée aux réunions de grande taille, en fonction des préférences de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6dd15-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="6dd15-119">Dans les sections suivantes, nous décrivons comment implémenter un pool dédié pour les grandes réunions, notamment les meilleures pratiques pour l’utilisation de Lync Server 2013 afin de prendre en charge les grands scénarios de réunion.</span><span class="sxs-lookup"><span data-stu-id="6dd15-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6dd15-120">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6dd15-120">In This Section</span></span>

  - [<span data-ttu-id="6dd15-121">Configuration de la prise en charge des grandes réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd15-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="6dd15-122">Gestion des grandes réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd15-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

