---
title: Activer la traduction incorporée des messages
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
description: Découvrez comment activer la traduction incorporée dans Microsoft Teams à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 719f97e72f099edb4d14c22ef9d5a3de0f787ea7411f42f1d777ea842bcc4e27
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339642"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Désactiver la traduction incorporée des messages dans Microsoft Teams

La traduction incorporée des messages est une fonctionnalité de Microsoft Teams qui permet aux utilisateurs de traduire les messages des équipes dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres linguistiques personnels.

La traduction incorporée des messages est déployée par défaut pour votre organisation. Vous n’avez pas besoin d’apporter de modifications si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams.

> [!NOTE]
>Ce déploiement ne fait pas partie des abonnements Office 365 dans nos environnements Office 365 GCC et Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Utiliser PowerShell pour désactiver la traduction incorporée des messages

Vous pouvez utiliser la stratégie de messagerie pour désactiver la traduction incorporée des messages.

Désactiver la stratégie à l’aide de la cmdlet [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps). L’application de cette stratégie prend quelques minutes. Les utilisateurs devront peut-être se déconnecter, puis se reconnecter à Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Utiliser le Centre d'administration Microsoft Teams pour désactiver la traduction incorporée des messages dans Microsoft Teams

Dans le **Centre d’administration Microsoft Teams**, sélectionnez **Stratégies de messagerie** dans le menu de navigation gauche, créez une stratégie ou modifiez une stratégie existante, puis définissez l’option **Traduire les messages** sur **Off**.

> [!NOTE]
> Le service effectue, puis livre la traduction au client sans effet sur le contenu capturé dans les enregistrements de conformité. Si vous souhaitez en savoir plus sur la traduction, veuillez consulter la rubrique [Qu’est-ce que Microsoft Translator ?](/azure/cognitive-services/translator/translator-info-overview)