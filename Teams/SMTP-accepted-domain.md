---
title: "Ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online pour envoyer des notifications aux membres d'équipe."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 2006cde3cf2fc41a64b98fdc14004aa64876cb1a
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online 
=============================================================================

Si vous créez un groupe Office 365 dans la console d'administration ou à l'aide d'Outlook, Exchange Online est utilisé pour envoyer des notifications concernant l'ajout d'un membre d'équipe à un groupe. Ces messages sont générés à partir de votre client, car ils représentent votre nom de domaine complet SMTP par défaut.

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams utilise Microsoft Exchange Online également pour envoyer des notifications lorsque des membres d'équipes sont ajoutés. La partie différente du nom de domaine complet du message SMTP est « @email.teams.microsoft.com », qui peut alors tomber dans le filtre anti-spam. Comme illustré dans l'image ci-dessous, Outlook considère ce message comme un expéditeur externe soumis aux fonctionnalités standards de sécurité, telles que le blocage d'images et de certain contenu.

![Capture d'écran d'un en-tête de message e-mail Outlook d'exemple indiquant qu'un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Pour obtenir des résultats optimaux et un fonctionnement correct, vous pouvez ajouter le domaine SMTP de Microsoft Teams à votre liste de domaine acceptés dans votre configuration anti-spam Exchange Online :

![Capture d'écran de la section des listes d'invités autorisés des paramètres de configuration anti-spam d'Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
