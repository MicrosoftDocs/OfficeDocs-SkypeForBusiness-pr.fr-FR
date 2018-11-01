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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851567"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Utiliser la traduction des messages incorporée dans Microsoft Teams 
=================================================

La traduction des messages incorporée est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire automatiquement les messages Teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.

La traduction des messages incorporée est déployée par défaut pour votre organisation. Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams, vous devez activer ce paramètre à l’aide de PowerShell. Cette option n’est pas disponible actuellement dans le Centre d’administration de Microsoft Teams et Skype Entreprise, mais elle le sera prochainement.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans notre cloud communautaire pour le service public Office 365 et dans les environnements Office 365 en Allemagne. 

## <a name="enable-by-using-powershell"></a>Activer à l’aide de PowerShell

Vous pouvez activer la fonctionnalité de traduction des messages incorporée en utilisant la stratégie de messagerie. 

1. Activez la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. L’application de la stratégie prend quelques minutes. Les utilisateurs devront peut-être se déconnecter et se reconnecter à Teams.

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a>Activer à l’aide du Microsoft Teams & Skype entreprise centre d’administration

L’option pour activer la fonctionnalité de traduction en ligne message avec le modèle Microsoft Teams & Skype entreprise centre d’administration seront prochainement disponibles.

> [!NOTE]
>La traduction ne s’applique que du côté client et n’a aucune incidence sur le contenu capturé dans les enregistrements de conformité. Pour en savoir plus sur la traduction, reportez-vous à la section [Qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).