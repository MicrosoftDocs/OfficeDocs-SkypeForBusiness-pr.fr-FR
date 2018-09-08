---
title: Utiliser la traduction en ligne d’un message dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser Microsoft Teams traduction en ligne.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882907"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Utiliser la traduction en ligne d’un message dans Microsoft Teams 
=================================================

Traduction en ligne d’un message est une nouvelle fonctionnalité Teams Microsoft qui permet aux utilisateurs de traduire automatiquement des messages d’équipes dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres personnels de langue pour Office 365.

Traduction des messages incorporés est déployée par défaut pour votre organisation. Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client d’équipes, vous devez activer ce paramètre à l’aide de PowerShell. Actuellement, cette option n’est pas disponible dans le Microsoft Teams et Skype entreprise centre d’administration, mais sera bientôt.

> [!NOTE]
>Ce déploiement est exclu des abonnements Office 365 dans les environnements de notre nuage de la Communauté Office 365 pour le gouvernement et Office 365 Allemagne. 

## <a name="enable-by-using-powershell"></a>Activer à l’aide de PowerShell

Vous pouvez activer la fonctionnalité de traduction de messages incorporés à l’aide de la stratégie de messagerie. 

1. Activer la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. La stratégie prend quelques minutes à appliquer. Vous devrez vous déconnecter et vous reconnecter aux équipes des utilisateurs.

## <a name="enable-by-using-the-teams-admin-center"></a>Activer à l’aide du centre d’administration équipes

L’option pour activer la fonctionnalité de traduction de messages incorporés à l’aide du centre d’administration équipes seront prochainement disponibles.

> [!NOTE]
>Traduction est strictement côté client et n’a aucun effet sur le contenu capturé dans les enregistrements de conformité. Pour plus d’informations sur la traduction, voir [What ' s Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).