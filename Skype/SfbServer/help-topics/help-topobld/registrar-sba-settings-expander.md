---
title: Expanseur des paramètres SBA du serveur d’inscriptions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: 6424b43ea7c56760bb8d58ee35d9804c49c435dd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217215"
---
# <a name="registrar-sba-settings-expander"></a>Expanseur des paramètres SBA du serveur d’inscriptions

Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :

- Sélectionnez **Pool de serveurs d’inscriptions de sauvegarde et service utilisateur associé** dans la liste.

    Éventuellement, activez la case à cocher **Basculement et restauration automatiques pour Voice**.

    Configurez les options **Intervalle de détection d’échec Voice (en secondes)** et **Intervalle de restauration automatique Voice (en secondes)**. Par défaut, les intervalles sont de 120 secondes pour la détection d’échec Voice et de 240 secondes pour la restauration automatique Voice.

    > [!CAUTION]
    > Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé afin de garantir le bon fonctionnement de la résilience. Si l’intervalle est trop faible (c’est-à-dire moins de 120 secondes) ou si le basculement et la restauration automatique sont définis de manière trop rapprochée, il peut en résulter un fonctionnement inattendu du basculement ou de la restauration automatique.

  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.

  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.

  **Aide** permet d’afficher cet écran d’aide.

## <a name="see-also"></a>Voir aussi

[Planification de la résistance voix entreprise](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
