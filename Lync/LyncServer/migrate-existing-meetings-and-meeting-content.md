---
title: Migration de réunions et de contenu de réunion existants
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a6036421dd84f466df0f2353b6d5264e0680c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="551e1-102">Migration de réunions et de contenu de réunion existants</span><span class="sxs-lookup"><span data-stu-id="551e1-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="551e1-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="551e1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="551e1-104">Lorsqu’un compte d’utilisateur est déplacé de Lync Server 2010 vers un serveur Lync Server 2013, les informations suivantes sont déplacées avec ce compte d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="551e1-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="551e1-p101">**Réunions déjà planifiées par l’utilisateur** : cela comprend le déplacement des répertoires de conférence et des données de conférence.</span><span class="sxs-lookup"><span data-stu-id="551e1-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="551e1-p102">**Code confidentiel de l’utilisateur** : le code confidentiel actuel de l’utilisateur fonctionne jusqu’à ce qu’il expire ou que l’utilisateur en demande un nouveau.</span><span class="sxs-lookup"><span data-stu-id="551e1-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="551e1-109">Les informations de compte d’utilisateur suivantes ne se déplacent pas vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="551e1-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="551e1-p103">**Contenu de la réunion** : pour déplacer le contenu partagé pendant une réunion, par exemple, PowerPoint, Tableau blanc, pièces jointes ou données d’interrogation, utilisez le paramètre **-MoveConferenceData** dans le cadre de l’applet de commande **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="551e1-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

