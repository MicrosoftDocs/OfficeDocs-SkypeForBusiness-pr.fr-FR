---
title: 'Lync Server 2013: informations de planification pour les réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f027aac5372865bfb2803e19591dadaa1aca4805
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Détails de planification des réunions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Une fois que l’équipe de support des grandes réunions qui traite la demande s’est assurée qu’aucune autre réunion n’est prévue à l’heure demandée, elle planifie la réunion dans le pool des grandes réunions. Utilisez le complément réunion en ligne pour Lync qui est installé avec le client Lync Server 2013 pour exécuter cette tâche, en utilisant les informations d’identification d’un utilisateur qui a activé le serveur Lync dans le pool de réunions volumineux dédié.

Pour assurer la meilleure expérience utilisateur possible, il est important de planifier les grandes réunions avec les niveaux d’accès et les paramètres de réunion appropriés, en fonction des besoins de l’organisateur de la réunion. Nous vous recommandons d’utiliser les paramètres de planification suivants configurés dans les options de réunion Lync:

  - Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié.

  - Spécifiez le niveau d’accès à la réunion, comme suit :
    
      - Si au moins un invité est externe à l’organisation, définissez le type d’accès à la réunion sur **tout le monde (aucune restriction**. Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.
    
      - S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.
        
        <div>
        

        > [!NOTE]  
        > Évitez de choisir le type d’accès à la réunion <STRONG>Personnes de mon entreprise que j’invite</STRONG>, car lorsque vous utilisez ce paramètre, les organisateurs doivent ajouter toutes les adresses électroniques à la liste d’invités et vous ne pouvez pas inviter un groupe de distribution.<BR>Évitez de choisir le type d’accès à la réunion <STRONG>Seulement moi, l’organisateur de la réunion</STRONG>, car ce paramètre exige que chaque participant de la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure de la réunion. La personne responsable du déroulement de la grande réunion doit alors surveiller constamment la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.

        
        </div>

  - Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.

  - Invitez explicitement les utilisateurs suivants :
    
      - Organisateur de la réunion et délégué (demandeur)
    
      - Liste des présentateurs fournie par un demandeur de réunion
    
    <div>
    

    > [!NOTE]  
    > Si le type d’accès à la réunion défini est <STRONG>Personnes que je choisis</STRONG>, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion.

    
    </div>

  - Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs ci-dessous en tant que présentateurs :
    
      - Organisateur de la réunion et délégué (demandeur)
    
      - Liste des présentateurs fournie par les demandeurs de grande réunion
    
    <div>
    

    > [!NOTE]  
    > En gérant explicitement les présentateurs, vous pouvez contrôler le nombre de présentateurs, afin que vous puissiez limiter le nombre de présentateurs à un nombre réduit de temps suffisant pour pouvoir compter une réunion de grande envergure. Si la majorité des participants à la réunion possèdent un rôle de participant, cela limite le risque que des personnes prennent accidentellement le contrôle de la présentation, suppriment une présentation PowerPoint, désactivent ou activent le son pour les présentateurs et perturbent le déroulement de la réunion.

    
    </div>

  - Cochez le paramètre **Désactiver le son pour tous les participants** afin que seuls les présentateurs puissent diffuser du son lors de la réunion.

  - Cochez le paramètre **Bloquer la vidéo des participants** afin que seuls les présentateurs puissent diffuser des vidéos lors de la réunion.

La figure suivante illustre les paramètres recommandés pour le complément réunion en ligne pour Lync.

![54e4e70d-06b0-45CD-8d94-bab649cd5dc0] (images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45CD-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

