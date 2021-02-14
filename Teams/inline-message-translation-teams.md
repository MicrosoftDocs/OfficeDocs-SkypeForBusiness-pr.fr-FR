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
description: Découvrez comment activer la traduction en ligne dans Microsoft Teams à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.
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
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Désactiver la traduction des messages dans Microsoft Teams
=================================================

La traduction de message en ligne est une fonctionnalité [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) de Microsoft Teams qui permet aux utilisateurs de traduire les messages Teams dans la langue spécifiée par leurs paramètres de langue personnels.

La traduction des messages en ligne est déployée par défaut pour votre organisation. Vous n’avez pas besoin d’effectuer de modifications si vous voulez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans nos environnements Office 365 Government Community Cloud et Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Utiliser PowerShell pour désactiver la traduction de messages en ligne

Vous pouvez utiliser la stratégie de messagerie pour désactiver la traduction des messages dans le texte.

Dés éteindre la stratégie à l’aide de l’cmdlet [Set-CsTeamsMesspolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) L’application de la stratégie prend quelques minutes. Les utilisateurs devront peut-être se sortir et se resserrer sur Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Utiliser le Centre d’administration Microsoft Teams pour désactiver la traduction de messages en ligne

Dans le Centre d’administration **Microsoft Teams,** sélectionnez Stratégies de messagerie dans le panneau de navigation de gauche, puis créez une stratégie ou modifiez une stratégie existante et définissez l’option Traduire les **messages** sur **Off.** 

> [!NOTE]
> Le service fait la traduction et la livre au client sans effet sur le contenu capturé dans les enregistrements de conformité. Pour en savoir plus sur la traduction, voir [Qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
