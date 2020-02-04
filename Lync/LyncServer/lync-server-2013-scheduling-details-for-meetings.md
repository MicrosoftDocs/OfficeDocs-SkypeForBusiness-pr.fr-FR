---
title: 'Lync Server 2013 : informations de planification pour les réunions'
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
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="18485-102">Détails de planification des réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18485-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18485-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="18485-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="18485-104">Une fois que l’équipe de support des grandes réunions qui traite la demande s’est assurée qu’aucune autre réunion n’est prévue à l’heure demandée, elle planifie la réunion dans le pool des grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="18485-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="18485-105">Utilisez le complément réunion en ligne pour Lync qui est installé avec le client Lync Server 2013 pour exécuter cette tâche, en utilisant les informations d’identification d’un utilisateur qui a activé le serveur Lync dans le pool de réunions volumineux dédié.</span><span class="sxs-lookup"><span data-stu-id="18485-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="18485-106">Pour assurer la meilleure expérience utilisateur possible, il est important de planifier les grandes réunions avec les niveaux d’accès et les paramètres de réunion appropriés, en fonction des besoins de l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="18485-107">Nous vous recommandons d’utiliser les paramètres de planification suivants configurés dans les options de réunion Lync :</span><span class="sxs-lookup"><span data-stu-id="18485-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="18485-108">Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié.</span><span class="sxs-lookup"><span data-stu-id="18485-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="18485-109">Spécifiez le niveau d’accès à la réunion, comme suit :</span><span class="sxs-lookup"><span data-stu-id="18485-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="18485-110">Si au moins un invité est externe à l’organisation, définissez le type d’accès à la réunion sur **tout le monde (aucune restriction**.</span><span class="sxs-lookup"><span data-stu-id="18485-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="18485-111">Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="18485-112">S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.</span><span class="sxs-lookup"><span data-stu-id="18485-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="18485-113">Évitez de choisir le type d’accès à la réunion <STRONG>Personnes de mon entreprise que j’invite</STRONG>, car lorsque vous utilisez ce paramètre, les organisateurs doivent ajouter toutes les adresses électroniques à la liste d’invités et vous ne pouvez pas inviter un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="18485-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="18485-114">Évitez de choisir le type d’accès à la réunion <STRONG>Seulement moi, l’organisateur de la réunion</STRONG>, car ce paramètre exige que chaque participant de la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="18485-115">La personne responsable du déroulement de la grande réunion doit alors surveiller constamment la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="18485-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="18485-116">Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.</span><span class="sxs-lookup"><span data-stu-id="18485-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="18485-117">Invitez explicitement les utilisateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="18485-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="18485-118">Organisateur de la réunion et délégué (demandeur)</span><span class="sxs-lookup"><span data-stu-id="18485-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="18485-119">Liste des présentateurs fournie par un demandeur de réunion</span><span class="sxs-lookup"><span data-stu-id="18485-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18485-120">Si le type d’accès à la réunion défini est <STRONG>Personnes que je choisis</STRONG>, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="18485-p105">Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs ci-dessous en tant que présentateurs :</span><span class="sxs-lookup"><span data-stu-id="18485-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="18485-123">Organisateur de la réunion et délégué (demandeur)</span><span class="sxs-lookup"><span data-stu-id="18485-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="18485-124">Liste des présentateurs fournie par les demandeurs de grande réunion</span><span class="sxs-lookup"><span data-stu-id="18485-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18485-125">En gérant explicitement les présentateurs, vous pouvez contrôler le nombre de présentateurs, afin que vous puissiez limiter le nombre de présentateurs à un nombre réduit de temps suffisant pour pouvoir compter une réunion de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="18485-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="18485-126">Si la majorité des participants à la réunion possèdent un rôle de participant, cela limite le risque que des personnes prennent accidentellement le contrôle de la présentation, suppriment une présentation PowerPoint, désactivent ou activent le son pour les présentateurs et perturbent le déroulement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="18485-127">Cochez le paramètre **Désactiver le son pour tous les participants** afin que seuls les présentateurs puissent diffuser du son lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="18485-128">Cochez le paramètre **Bloquer la vidéo des participants** afin que seuls les présentateurs puissent diffuser des vidéos lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="18485-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="18485-129">La figure suivante illustre les paramètres recommandés pour le complément réunion en ligne pour Lync.</span><span class="sxs-lookup"><span data-stu-id="18485-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="18485-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="18485-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

