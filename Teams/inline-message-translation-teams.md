---
title: Utiliser la traduction des messages incorporée dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
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
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016836"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Utiliser la traduction des messages incorporée dans Microsoft Teams 
=================================================

La traduction des messages incorporée est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire automatiquement les messages Teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.

Traduction des messages incorporés est déployée par défaut pour votre organisation. Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client d’équipes, vous devez activer ce paramètre à l’aide de PowerShell. Actuellement, cette option n’est pas disponible dans le Microsoft Teams et Skype entreprise centre d’administration, mais sera bientôt.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans notre cloud communautaire pour le service public Office 365 et dans les environnements Office 365 en Allemagne. 

## <a name="enable-by-using-powershell"></a>Activer à l’aide de PowerShell

Vous pouvez activer la fonctionnalité de traduction des messages incorporée en utilisant la stratégie de messagerie. 

1. Activez la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. La stratégie prend quelques minutes à appliquer. Vous devrez vous déconnecter et vous reconnecter aux équipes des utilisateurs.

## <a name="enable-by-using-the-teams-admin-center"></a>Activer en utilisant le Centre d’administration de Teams

L’option permettant d’activer la fonctionnalité de traduction des messages iincorporée à l’aide du Centre d’administration de Teams sera disponible prochainement.

> [!NOTE]
>Traduction est strictement côté client et n’a aucun effet sur le contenu capturé dans les enregistrements de conformité. Pour plus d’informations sur la traduction, voir [What ' s Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).