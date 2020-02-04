---
title: 'Lync Server 2013 : processus de planification de grande réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Processus de planification de grande réunion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Étant donné qu’une seule grande réunion à la fois est prise en charge sur le pool de réunions important, nous vous recommandons d’implémenter un processus de planification de réunion volumineux pour éviter les conflits de réunion importants. L’objectif du processus de planification consiste à faciliter la configuration des réunions de grande envergure. Cette fonctionnalité n’est pas fournie directement par les clients Lync Server ou Lync Server. Le recours au le système de tickets du support de votre organisation, le cas échéant, est l’une des méthodes disponibles pour mettre en œuvre cette procédure.

Pour les organisateurs de réunion de grande taille, la planification d’une réunion importante implique les étapes suivantes :

1.  Outre la liste de présentateurs, l’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion. Si la taille de réunion prévue dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué envoie une demande pour une grande réunion.

2.  Le personnel chargé de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier des grandes réunions pour déterminer si une autre réunion est planifiée à la date et à l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.

3.  S’il s’agit d’une demande approuvée, le personnel de planification (à l’aide des informations d’identification de la réserve dédiée) utilise le complément réunion en ligne pour Lync 2013 avec Outlook pour configurer une réunion sur le pool de réunion volumineux dédié. L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.

4.  L’organisateur de réunion ou le délégué utilise Outlook pour planifier la réunion suivante en ajoutant l’URL de l’invitation à participer à la réunion. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.
    
    La figure suivante illustre un flux de travail de demande et d’approbation standard pour planifier des réunions de grande taille.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

