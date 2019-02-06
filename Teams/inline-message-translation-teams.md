---
title: Utiliser la traduction des messages incorporée dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser la traduction incorporée dans Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 466160616adea80a2fcb6a3bfd035ca397d73754
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754425"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Utiliser la traduction des messages incorporée dans Microsoft Teams 
=================================================

La traduction des messages incorporée est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire automatiquement les messages Teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.

La traduction des messages incorporée est déployée par défaut pour votre organisation. Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client d’équipes, vous devez activer ce paramètre.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans les environnements de notre nuage de la Communauté Office 365 pour le gouvernement et Office 365 Allemagne.

## <a name="enable-by-using-powershell"></a>Activer à l’aide de PowerShell

Vous pouvez activer la fonctionnalité de traduction de messages incorporés à l’aide de la stratégie de messagerie.

1. Activer la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. La stratégie prend quelques minutes à appliquer. Vous devrez vous déconnecter et vous reconnecter aux équipes des utilisateurs.

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>Activer à l’aide du centre d’administration Microsoft Teams

Dans le **Centre d’administration de Microsoft équipes**, sélectionnez **Stratégies de messagerie** dans la barre de gauche, soit créer une nouvelle stratégie ou modifier une stratégie existante, puis définissez l’option **Autoriser les utilisateurs à convertir des messages** **sur**.

> [!NOTE]
>Traduction est effectuée par le service et remise au client avec aucun effet sur le contenu capturé dans les enregistrements de conformité. Pour plus d’informations sur la traduction, voir [What ' s Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).