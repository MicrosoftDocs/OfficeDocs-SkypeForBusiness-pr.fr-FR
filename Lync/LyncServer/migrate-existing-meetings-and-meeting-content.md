---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="e189c-102">Migration des réunions existantes et du contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="e189c-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e189c-103">_**Dernière modification de la rubrique:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e189c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e189c-104">Lorsqu’un compte d’utilisateur est déplacé de Lync Server 2010 vers un serveur Lync Server 2013, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur:</span><span class="sxs-lookup"><span data-stu-id="e189c-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="e189c-105">**Réunions déjà planifiées par l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e189c-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="e189c-106">Cela inclut le déplacement des répertoires de conférences et des données de conférence.</span><span class="sxs-lookup"><span data-stu-id="e189c-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="e189c-107">**Code confidentiel (pin) de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e189c-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="e189c-108">Le code confidentiel actuel de l’utilisateur continue de fonctionner tant qu’il n’a pas expiré ou que l’utilisateur ne demande pas de nouveau code secret.</span><span class="sxs-lookup"><span data-stu-id="e189c-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="e189c-109">Les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="e189c-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="e189c-110">**Contenu**de la réunion.</span><span class="sxs-lookup"><span data-stu-id="e189c-110">**Meeting content**.</span></span> <span data-ttu-id="e189c-111">Pour déplacer le contenu partagé pendant une réunion (par exemple, PowerPoint, tableau blanc, pièces jointes ou interrogation), utilisez le paramètre **-MoveConferenceData** dans le cadre de l’applet de commande **Move-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="e189c-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

