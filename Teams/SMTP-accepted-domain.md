---
title: Ajouter le domaine SMTP de Microsoft Teams comme domaine de l’expéditeur accepté dans Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Apprenez à ajouter le domaine SMTP des équipes Microsoft comme domaine de l’expéditeur autorisés dans Exchange Online pour envoyer des notifications aux membres de l’équipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4a1a94bec69b1c7953dea6802d62058b04700bb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194170"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Ajouter le domaine SMTP de Microsoft Teams comme domaine de l’expéditeur accepté dans Exchange Online 
=============================================================================

Si vous créez un groupe Office 365 dans la console d'administration ou à l'aide d'Outlook, Exchange Online est utilisé pour envoyer des notifications concernant l'ajout d'un membre d'équipe à un groupe. Ces messages sont générés à partir de votre client, car ils représentent votre nom de domaine complet SMTP par défaut.

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Les équipes utilise également Microsoft Exchange Online pour envoyer des notifications aux membres de l’équipe lorsqu’ils ont été ajoutés. La différence est le nom de domaine complet du message SMTP du domaine est « @email.teams.microsoft.com » pour les clients commerciaux/Business et « @GCC-email.teams.com » pour les clients pour le gouvernement et peut être interceptée par le filtrage du courrier indésirable.

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Pour les meilleurs résultats et un fonctionnement transparent, envisagez d’ajouter le domaine SMTP des équipes Microsoft à votre liste des « autorisés domaines expéditeur » dans la configuration du courrier indésirable Exchange Online :

![Capture d'écran de la section des listes d'invités autorisés des paramètres de configuration anti-spam d'Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
