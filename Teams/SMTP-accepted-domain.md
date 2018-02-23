---
title: "Ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: "Découvrez comment ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online pour envoyer des notifications aux membres d'équipe."
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcddc2f2d36ed4ec6dd0bc12038b88ac0ec93103
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online 
=============================================================================

Si vous créez un groupe Office 365 dans la console d'administration ou à l'aide d'Outlook, Exchange Online est utilisé pour envoyer des notifications concernant l'ajout d'un membre d'équipe à un groupe. Ces messages sont générés à partir de votre client, car ils représentent votre nom de domaine complet SMTP par défaut.

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams utilise Microsoft Exchange Online également pour envoyer des notifications lorsque des membres d'équipes sont ajoutés. La partie différente du nom de domaine complet du message SMTP est « @email.teams.microsoft.com », qui peut alors tomber dans le filtre anti-spam. Comme illustré dans l'image ci-dessous, Outlook considère ce message comme un expéditeur externe soumis aux fonctionnalités standards de sécurité, telles que le blocage d'images et de certain contenu.

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Pour obtenir des résultats optimaux et un fonctionnement correct, vous pouvez ajouter le domaine SMTP de Microsoft Teams à votre liste de domaine acceptés dans votre configuration anti-spam Exchange Online :

![Capture d'écran de la section des listes d'invités autorisés des paramètres de configuration anti-spam d'Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
