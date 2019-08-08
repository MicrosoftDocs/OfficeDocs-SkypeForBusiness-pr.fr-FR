---
title: Ajouter le domaine SMTP de Microsoft Teams comme domaine de l’expéditeur accepté dans Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Apprenez à ajouter le domaine SMTP Microsoft teams en tant que domaine d’expéditeur autorisé dans Exchange Online pour envoyer des notifications aux membres de l’équipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc4b72e973bf6763b817c9bc4f133961cd000f7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245760"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="80c97-103">Ajouter le domaine SMTP de Microsoft Teams comme domaine de l’expéditeur accepté dans Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80c97-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="80c97-p101">Si vous créez un groupe Office 365 dans la console d'administration ou à l'aide d'Outlook, Exchange Online est utilisé pour envoyer des notifications concernant l'ajout d'un membre d'équipe à un groupe. Ces messages sont générés à partir de votre client, car ils représentent votre nom de domaine complet SMTP par défaut.</span><span class="sxs-lookup"><span data-stu-id="80c97-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Capture d’écran d’un en-tête de message indiquant qu’un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="80c97-107">Teams utilise Microsoft Exchange Online et envoie des notifications aux membres de l’équipe lorsqu’ils ont été ajoutés.</span><span class="sxs-lookup"><span data-stu-id="80c97-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="80c97-108">La différence est le nom de domaine complet du domaine du message SMTP qui est «@email. teams.microsoft.com» pour les clients commerciaux et commerciaux et «@GCC-email.teams.com» pour les clients gouvernementaux et qui peut être intercepté par le filtrage du courrier indésirable.</span><span class="sxs-lookup"><span data-stu-id="80c97-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Capture d’écran d’un en-tête de message indiquant qu’un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="80c97-110">Pour un résultat optimal et un fonctionnement transparent, envisagez d’ajouter le domaine SMTP Microsoft teams à votre liste «domaines d’expéditeur autorisés» dans votre configuration de courrier indésirable Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="80c97-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Capture d’écran de la section autoriser les listes des paramètres de configuration du courrier indésirable](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
