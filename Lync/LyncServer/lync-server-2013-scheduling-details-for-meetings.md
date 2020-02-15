---
title: 'Lync Server 2013 : détails de la planification des réunions'
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
ms.openlocfilehash: 6537309f8c2a787c94897fa9f529c1abf8fd4791
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Détails de la planification pour les réunions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Après s’être assurée qu’aucune autre réunion n’est prévue à l’heure demandée, l’équipe de support des grandes réunions qui traite la demande planifie la réunion dans le pool de grandes réunions. Utilisez le complément de réunion en ligne pour Lync qui est installé avec le client Lync Server 2013 pour effectuer cette tâche, en utilisant les informations d’identification d’un utilisateur activé pour Lync Server dans le pool dédié aux grandes réunions.

Pour assurer la meilleure expérience utilisateur possible, il est important de planifier les grandes réunions avec les niveaux d’accès et les paramètres de réunion appropriés, en fonction des besoins de l’organisateur de la réunion. Nous vous recommandons de configurer les paramètres de planification suivants dans les options de réunion Lync :

  - Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié.

  - Spécifiez le niveau d’accès à la réunion comme suit :
    
      - Si au moins un invité ne fait pas partie de l’organisation, optez pour le type d’accès à la réunion **Tout le monde (aucune restriction)**. Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.
    
      - S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.
        
        <div>
        

        > [!NOTE]  
        > Évitez de choisir le type d’accès à la réunion <STRONG>Personnes de ma société invitées</STRONG>. En effet, ce paramètre contraint les organisateurs à ajouter toutes les adresses de messagerie des utilisateurs à la liste d’invités et il vous empêche d’inviter un groupe de distribution.<BR>Évitez de choisir le type d’accès à la réunion <STRONG>Seulement moi, l’organisateur de la réunion</STRONG>, car ce paramètre exige que chaque participant à la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure d’exécution de la réunion. La personne responsable de l’exécution de la grande réunion doit alors constamment surveiller la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.

        
        </div>

  - Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.

  - Invitez explicitement les utilisateurs suivants :
    
      - organisateur de la réunion et délégué (demandeur) ;
    
      - liste des présentateurs fournie par un demandeur de réunion.
    
    <div>
    

    > [!NOTE]  
    > Si le type d’accès à la réunion défini est <STRONG>Personnes que je choisis</STRONG>, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion.

    
    </div>

  - Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs suivants en tant que présentateurs :
    
      - organisateur de la réunion et délégué (demandeur) ;
    
      - liste des présentateurs fournie par les demandeurs de grande réunion.
    
    <div>
    

    > [!NOTE]  
    > En gérant explicitement les présentateurs, vous pouvez contrôler le nombre de présentateurs et ainsi favoriser le bon déroulement d’une grande réunion, avec un nombre de présentateurs limité. Si la majorité des participants à la réunion ont un rôle de participant, cela limite les chances de voir des personnes prendre accidentellement le contrôle de la présentation, supprimer une présentation PowerPoint, désactiver ou activer le son pour les présentateurs et perturber le déroulement de la réunion.

    
    </div>

  - Cochez le paramètre **Désactiver le son pour tous les participants** pour faire en sorte que seuls les présentateurs puissent diffuser du son au cours de la réunion.

  - Cochez le paramètre **Bloquer la vidéo des participants** pour faire en sorte que seuls les présentateurs puissent diffuser des vidéos au cours de la réunion.

La figure suivante illustre les paramètres recommandés pour le complément de réunion en ligne pour Lync.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

