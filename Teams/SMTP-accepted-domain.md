---
title: Ajouter le domaine SMTP des équipes Microsoft comme domaine de l’expéditeur autorisés dans Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: anprakas
search.appverid: MET150
description: Apprenez à ajouter le domaine SMTP des équipes Microsoft comme domaine de l’expéditeur autorisés dans Exchange Online pour envoyer des notifications aux membres de l’équipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f94b18994e277b90f96bc4fdbdefaa0b1f7a72e8
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789049"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="ac33a-103">Ajouter le domaine SMTP des équipes Microsoft comme domaine de l’expéditeur autorisés dans Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ac33a-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="ac33a-p101">Si vous créez un groupe Office 365 dans la console d'administration ou à l'aide d'Outlook, Exchange Online est utilisé pour envoyer des notifications concernant l'ajout d'un membre d'équipe à un groupe. Ces messages sont générés à partir de votre client, car ils représentent votre nom de domaine complet SMTP par défaut.</span><span class="sxs-lookup"><span data-stu-id="ac33a-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="ac33a-107">Les équipes utilise également Microsoft Exchange Online pour envoyer des notifications aux membres de l’équipe lorsqu’ils ont été ajoutés.</span><span class="sxs-lookup"><span data-stu-id="ac33a-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="ac33a-108">La différence est le nom de domaine complet du message SMTP du domaine est « @email.teams.microsoft.com » pour les clients commercial/Business et « @GCC-email.teams.com » pour les clients pour le gouvernement et peut être interceptée par le filtrage du courrier indésirable.</span><span class="sxs-lookup"><span data-stu-id="ac33a-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commerical/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="ac33a-110">Pour les meilleurs résultats et un fonctionnement transparent, envisagez d’ajouter le domaine SMTP des équipes Microsoft à votre liste des « autorisés domaines expéditeur » dans la configuration du courrier indésirable Exchange Online :</span><span class="sxs-lookup"><span data-stu-id="ac33a-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Capture d'écran de la section des listes d'invités autorisés des paramètres de configuration anti-spam d'Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
