---
title: Expanseur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: 4f29c453016f371f1c9a07561209ea5174583392
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773794"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expandeur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010
 
Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :
  
- Sélectionnez **Pool de serveurs d’inscriptions de sauvegarde associé** dans la liste.
    
    Éventuellement, activez la case à cocher **Basculement et restauration automatiques pour Voice**.
    
    Configurez les options **Intervalle de détection d’échec Voice (en secondes)** et **Intervalle de restauration automatique Voice (en secondes)**. Par défaut, les intervalles sont de 120 secondes pour la détection d’échec Voice et de 240 secondes pour la restauration automatique Voice.
    
    > [!CAUTION]
    > Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé afin de garantir le bon fonctionnement de la résilience. Si l’intervalle est trop faible (c’est-à-dire moins de 120 secondes) ou si le basculement et la restauration automatique sont définis de manière trop rapprochée, il peut en résulter un fonctionnement inattendu du basculement ou de la restauration automatique. 
  
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

