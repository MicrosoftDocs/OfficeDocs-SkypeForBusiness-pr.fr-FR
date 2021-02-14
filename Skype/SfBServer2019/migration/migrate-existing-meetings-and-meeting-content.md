---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Lorsqu’un compte d’utilisateur est déplacé d’un serveur Skype Entreprise Server 2019, les informations suivantes sont déplacées avec ce compte d’utilisateur :'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752686"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="00ceb-103">Migration des réunions existantes et du contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="00ceb-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="00ceb-104">Lorsqu’un compte d’utilisateur est déplacé vers un serveur Skype Entreprise Server 2019, les informations suivantes sont déplacées avec ce compte d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="00ceb-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="00ceb-105">**Réunions déjà planifiées par l’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="00ceb-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="00ceb-106">: cela comprend le déplacement des répertoires de conférence et des données de conférence.</span><span class="sxs-lookup"><span data-stu-id="00ceb-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="00ceb-107">Code confidentiel de **l’utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="00ceb-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="00ceb-108">Le code confidentiel actuel de l’utilisateur continue de fonctionner jusqu’à son expiration ou jusqu’à ce que l’utilisateur en demande un nouveau.</span><span class="sxs-lookup"><span data-stu-id="00ceb-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="00ceb-109">Les informations de compte d’utilisateur suivantes ne se déplacent pas vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="00ceb-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="00ceb-110">**Contenu de la réunion**</span><span class="sxs-lookup"><span data-stu-id="00ceb-110">**Meeting content**.</span></span> <span data-ttu-id="00ceb-111">Pour déplacer le contenu partagé au cours d’une réunion, tel que PowerPoint, Tableau blanc, pièces jointes ou données d’sondage, utilisez le paramètre **-MoveConferenceData** dans le cadre de l';cmdlet **Move-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="00ceb-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

