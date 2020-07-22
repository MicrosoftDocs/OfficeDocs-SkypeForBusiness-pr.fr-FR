---
title: Ajouter le domaine SMTP teams en tant que domaine expéditeur autorisé dans Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: Apprenez à ajouter le domaine SMTP Microsoft teams en tant que domaine d’expéditeur autorisé dans Exchange Online pour envoyer des notifications aux membres de l’équipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c60620a10bc5bb0cff37547313731ba214944ffc
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201138"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Ajouter le domaine SMTP de Microsoft Teams comme domaine de l’expéditeur accepté dans Exchange Online 
=============================================================================

Que vous soyez en train de créer un groupe Microsoft 365 dans la console d’administration ou à l’aide d’Outlook, Exchange Online est utilisé pour envoyer des notifications de l’ajout d’un membre d’équipe à un groupe. Ces messages sont générés par votre client, car ils représentent votre nom de domaine complet SMTP de domaine par défaut.

![Capture d’écran d’un en-tête de message indiquant qu’un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams utilise Microsoft Exchange Online et envoie des notifications aux membres de l’équipe lorsqu’ils ont été ajoutés. La différence est le nom de domaine complet du domaine du message SMTP qui est « @email. teams.microsoft.com » pour les clients commerciaux et commerciaux et « @GCC-email.teams.microsoft.com » pour les clients gouvernementaux et qui peut être intercepté par le filtrage du courrier indésirable.

![Capture d’écran d’un en-tête de message indiquant qu’un utilisateur a été ajouté à un groupe.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Pour un résultat optimal et un fonctionnement transparent, envisagez d’ajouter le domaine SMTP Microsoft teams à votre liste « domaines d’expéditeur autorisés » dans votre configuration de courrier indésirable Exchange Online :

![Capture d’écran de la section autoriser les listes des paramètres de configuration du courrier indésirable](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
