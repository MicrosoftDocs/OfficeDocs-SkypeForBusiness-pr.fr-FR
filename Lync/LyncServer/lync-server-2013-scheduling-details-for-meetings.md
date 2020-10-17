---
title: 'Lync Server 2013 : détails de la planification des réunions'
description: 'Lync Server 2013 : détails de la planification des réunions.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef7a6907aedbc880731b3fb474c9294c1c111b80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561980"
---
# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="47639-103">Détails de la planification pour les réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47639-103">Scheduling details for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47639-104">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="47639-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="47639-105">Après s’être assurée qu’aucune autre réunion n’est prévue à l’heure demandée, l’équipe de support des grandes réunions qui traite la demande planifie la réunion dans le pool de grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="47639-105">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="47639-106">Utilisez le complément de réunion en ligne pour Lync qui est installé avec le client Lync Server 2013 pour effectuer cette tâche, en utilisant les informations d’identification d’un utilisateur activé pour Lync Server dans le pool dédié aux grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="47639-106">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="47639-107">Pour assurer la meilleure expérience utilisateur possible, il est important de planifier les grandes réunions avec les niveaux d’accès et les paramètres de réunion appropriés, en fonction des besoins de l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-107">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="47639-108">Nous vous recommandons de configurer les paramètres de planification suivants dans les options de réunion Lync :</span><span class="sxs-lookup"><span data-stu-id="47639-108">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="47639-109">Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié.</span><span class="sxs-lookup"><span data-stu-id="47639-109">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="47639-110">Spécifiez le niveau d’accès à la réunion comme suit :</span><span class="sxs-lookup"><span data-stu-id="47639-110">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="47639-p103">Si au moins un invité ne fait pas partie de l’organisation, optez pour le type d’accès à la réunion **Tout le monde (aucune restriction)**. Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="47639-113">S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.</span><span class="sxs-lookup"><span data-stu-id="47639-113">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="47639-114">Évitez de choisir le type d’accès à la réunion <STRONG>Personnes de ma société invitées</STRONG>. En effet, ce paramètre contraint les organisateurs à ajouter toutes les adresses de messagerie des utilisateurs à la liste d’invités et il vous empêche d’inviter un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="47639-114">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="47639-p104">Évitez de choisir le type d’accès à la réunion <STRONG>Seulement moi, l’organisateur de la réunion</STRONG>, car ce paramètre exige que chaque participant à la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure d’exécution de la réunion. La personne responsable de l’exécution de la grande réunion doit alors constamment surveiller la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="47639-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="47639-117">Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.</span><span class="sxs-lookup"><span data-stu-id="47639-117">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="47639-118">Invitez explicitement les utilisateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="47639-118">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="47639-119">organisateur de la réunion et délégué (demandeur) ;</span><span class="sxs-lookup"><span data-stu-id="47639-119">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="47639-120">liste des présentateurs fournie par un demandeur de réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-120">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47639-121">Si le type d’accès à la réunion défini est <STRONG>Personnes que je choisis</STRONG>, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-121">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="47639-p105">Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs suivants en tant que présentateurs :</span><span class="sxs-lookup"><span data-stu-id="47639-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="47639-124">organisateur de la réunion et délégué (demandeur) ;</span><span class="sxs-lookup"><span data-stu-id="47639-124">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="47639-125">liste des présentateurs fournie par les demandeurs de grande réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-125">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47639-p106">En gérant explicitement les présentateurs, vous pouvez contrôler le nombre de présentateurs et ainsi favoriser le bon déroulement d’une grande réunion, avec un nombre de présentateurs limité. Si la majorité des participants à la réunion ont un rôle de participant, cela limite les chances de voir des personnes prendre accidentellement le contrôle de la présentation, supprimer une présentation PowerPoint, désactiver ou activer le son pour les présentateurs et perturber le déroulement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="47639-128">Cochez le paramètre **Désactiver le son pour tous les participants** pour faire en sorte que seuls les présentateurs puissent diffuser du son au cours de la réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-128">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="47639-129">Cochez le paramètre **Bloquer la vidéo des participants** pour faire en sorte que seuls les présentateurs puissent diffuser des vidéos au cours de la réunion.</span><span class="sxs-lookup"><span data-stu-id="47639-129">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="47639-130">La figure suivante illustre les paramètres recommandés pour le complément de réunion en ligne pour Lync.</span><span class="sxs-lookup"><span data-stu-id="47639-130">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="47639-131">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="47639-131">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

