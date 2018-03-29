---
title: Modification de Configuration de journal de périphérique
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Vous pouvez ajouter une configuration de périphérique de journal à la page Modifier les paramètres de journal qui détermine la taille maximale du cache du journal, la taille maximale du journal ou la durée pendant laquelle qu'un fichier journal est conservé avant d’être purgée. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
ms.openlocfilehash: 8003014f7b94824d0ef36a8d1328c6430e98d894
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration-edit"></a>Configuration des journaux de périphérique : modifier
 
Vous pouvez ajouter une configuration de périphérique de journal à la page **Modifier les paramètres de journal** qui détermine la taille maximale du cache du journal, la taille maximale du journal ou la durée pendant laquelle qu'un fichier journal est conservé avant d’être purgée. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
  
> [!CAUTION]
> Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer. 
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Modifier les paramètres de journal** :
  
- Ajouter une configuration de journal de périphérique globalement ou pour un site particulier.
    
- Modification des options d’une configuration de fichier journal d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Champ d’application** Identifie la portée (Global ou Site) de la configuration de journal de périphérique.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de journaux de périphérique.
    
- **Taille de fichier maximale (octets)** Vous pouvez spécifier la taille maximale, qu'un fichier journal peut devenir avant d’être purgée. La valeur par défaut est de 1,024,000 octets (1 Mo).
    
- **Taille de cache maximale (octets)** Vous pouvez spécifier la quantité d’informations maximale (en octets) qui peuvent être présentes dans le cache de fichier journal avant que cache doit être effacé et les données sont écrites dans un fichier journal. La valeur par défaut est de 512,000 octets (0,5 Mo).
    
- **Minutes pour vider le cache (1-60)** Vous pouvez spécifier la fréquence à laquelle les informations stockées dans le cache de fichier journal sont écrit dans le fichier journal actuel. Une fois que les données sont enregistrées, le cache est effacé. La valeur par défaut est de cinq minutes.
    
- **Jours de conservation des journaux (1-365)** Vous pouvez spécifier le nombre de jours que les fichiers journaux sont conservés avant leur suppression. La valeur par défaut est de 10 jours.
    
## <a name="see-also"></a>Voir aussi

#### 

[Configuration des journaux de périphérique](device-log-configuration.md)

