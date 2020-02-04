---
title: Expandeur des paramètres SBA du serveur d’inscriptions avancé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: 3fd2ea5a1ea2f0621a4df840a6e2af7581d39e9f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696739"
---
# <a name="registrar-sba-settings-expander"></a>Expandeur des paramètres SBA du serveur d’inscriptions avancé

Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :

- Dans la liste **, sélectionnez service d’utilisateurs associé et pool d’inscriptions de sauvegarde** .

    Vous pouvez également activer la case à cocher **basculement et retour automatique pour la voix** .

    Configurer l' **intervalle de détection de panne vocale (s)** et l’intervalle de restauration de la **voix (s)**. Par défaut, les intervalles sont de 120 secondes pour la détection de la panne vocale et 240 secondes pour le rétablissement de la voix.

    > [!CAUTION]
    > Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé pour s’assurer que la résilience fonctionne comme prévu. Le fait de définir l’intervalle sur faible (c’est-à-dire inférieur à 120 secondes), le basculement et la restauration automatique risquent de provoquer le basculement réel et le rétablissement ne fonctionne pas comme prévu.

  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.

  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.

  **Aide** permet d’afficher cet écran d’aide.

## <a name="see-also"></a>Voir aussi

[Planification de la résilience vocale entreprise](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
