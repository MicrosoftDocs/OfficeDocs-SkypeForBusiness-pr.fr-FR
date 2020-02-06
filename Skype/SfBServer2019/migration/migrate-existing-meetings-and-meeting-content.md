---
title: Migration des réunions existantes et du contenu des réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Lorsque vous dépassez un compte d’utilisateur d’un serveur 2019 Skype entreprise Server, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur :'
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813472"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="c4faa-103">Migration des réunions existantes et du contenu des réunions</span><span class="sxs-lookup"><span data-stu-id="c4faa-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="c4faa-104">Lorsqu’un compte d’utilisateur est déplacé vers un serveur Skype entreprise Server 2019, les informations suivantes sont déplacées à l’aide de ce compte d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="c4faa-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="c4faa-105">**Réunions déjà planifiées par l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="c4faa-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="c4faa-106">Cela inclut le déplacement des répertoires de conférences et des données de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4faa-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="c4faa-107">**Code confidentiel (pin) de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="c4faa-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="c4faa-108">Le code confidentiel actuel de l’utilisateur continue de fonctionner tant qu’il n’a pas expiré ou que l’utilisateur ne demande pas de nouveau code secret.</span><span class="sxs-lookup"><span data-stu-id="c4faa-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="c4faa-109">Les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="c4faa-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="c4faa-110">**Contenu**de la réunion.</span><span class="sxs-lookup"><span data-stu-id="c4faa-110">**Meeting content**.</span></span> <span data-ttu-id="c4faa-111">Pour déplacer le contenu partagé pendant une réunion, tel que PowerPoint, un tableau blanc, des pièces jointes ou des données de sondage, utilisez le paramètre **-MoveConferenceData** dans le cadre de l’applet de commande **Move-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="c4faa-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

