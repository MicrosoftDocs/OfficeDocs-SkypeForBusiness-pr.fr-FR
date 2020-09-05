---
title: Activer la traduction de messages en ligne
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment activer la traduction intraligne dans Microsoft teams à l’aide du centre d’administration Microsoft teams ou de PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395383"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Désactiver la traduction de messages en ligne dans Microsoft teams
=================================================

La traduction de messages en ligne est une fonctionnalité Microsoft teams qui permet aux utilisateurs de traduire des messages de teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels.

La traduction de messages incluse est déployée par défaut pour votre organisation. Vous n’avez pas besoin d’apporter des modifications si vous voulez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans le Cloud Office 365 Government Community et les environnements Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Utiliser PowerShell pour désactiver la traduction de messages en ligne

Vous pouvez utiliser la stratégie de messagerie pour désactiver la traduction de messages insérés.

Désactivez la stratégie à l’aide de l’applet de connexion [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . L’application de la stratégie prend quelques minutes. Vous devrez peut-être vous déconnecter et vous reconnecter à Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Utiliser le centre d’administration de Microsoft teams pour désactiver la traduction de messages en ligne

Dans le **Centre d’administration de Microsoft teams**, sélectionnez **stratégies de messagerie** dans le volet de navigation de gauche, puis créez une nouvelle stratégie ou modifiez une stratégie existante et définissez l’option **traduire les messages** sur **Désactiver**.

> [!NOTE]
> Le service effectue la traduction et le remet au client, sans effet sur le contenu capturé dans les enregistrements de conformité. Pour en savoir plus sur la traduction, voir [qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
