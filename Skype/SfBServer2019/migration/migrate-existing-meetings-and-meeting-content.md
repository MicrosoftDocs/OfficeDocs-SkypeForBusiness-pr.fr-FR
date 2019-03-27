---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsqu’un compte d’utilisateur est déplacé à partir d’à un Skype pour Business Server 2019 server, les informations suivantes sont déplacées avec ce compte d’utilisateur :'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874660"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="89421-103">Migration des réunions existantes et du contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="89421-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="89421-104">Lorsqu’un compte d’utilisateur est déplacé vers un Skype pour Business Server 2019 server, les informations suivantes sont déplacées avec ce compte d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="89421-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="89421-105">**Réunions déjà planifiées par l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="89421-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="89421-106">Cela inclut le déplacement des annuaires de conférence et données de conférence.</span><span class="sxs-lookup"><span data-stu-id="89421-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="89421-107">**Confidentiel l’utilisateur (PIN)**.</span><span class="sxs-lookup"><span data-stu-id="89421-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="89421-108">Code confidentiel actuel de l’utilisateur continue de fonctionner jusqu'à ce qu’il expire ou que l’utilisateur demande un nouveau code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="89421-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="89421-109">Les informations de compte d’utilisateur suivantes ne déplacent pas vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="89421-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="89421-110">**Contenu de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="89421-110">**Meeting content**.</span></span> <span data-ttu-id="89421-111">Afin de déplacer le contenu partagé au cours d’une réunion, telles que PowerPoint, tableau blanc, les pièces jointes ou les données de sondage, utilisent le paramètre **- MoveConferenceData** dans le cadre de l’applet de commande **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="89421-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

