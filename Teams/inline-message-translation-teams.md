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
description: Découvrez comment utiliser la traduction incorporée dans Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4de799959e5e387ad768c3f82e379e464f42191c
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141097"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Activer la traduction de messages en ligne dans Microsoft teams 
=================================================

La traduction de messages incorporés est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire des messages de teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.

La traduction des messages incorporée est déployée par défaut pour votre organisation. Si vous voulez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams, vous devez activer ce paramètre.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans le Cloud Office 365 Government Community et les environnements Office 365 Germany.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Utiliser PowerShell pour activer la traduction de messages en ligne

Vous pouvez utiliser la stratégie de messagerie pour activer la traduction des messages insérés.

Activez la stratégie à l’aide de l’applet de cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . L’application de la stratégie prend quelques minutes. Vous devrez peut-être vous déconnecter et vous reconnecter à Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Utiliser le centre d’administration de Microsoft teams pour activer la traduction de messages en ligne

Dans le **Centre d’administration de Microsoft teams**, sélectionnez **stratégies de messagerie** dans le volet de navigation de gauche, puis créez une nouvelle stratégie ou modifiez une stratégie existante et définissez l’option **autoriser les utilisateurs à traduire les messages** sur **activé**.

> [!NOTE]
> Le service effectue la traduction et le remet au client, sans effet sur le contenu capturé dans les enregistrements de conformité. Pour en savoir plus sur la traduction, voir [qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).