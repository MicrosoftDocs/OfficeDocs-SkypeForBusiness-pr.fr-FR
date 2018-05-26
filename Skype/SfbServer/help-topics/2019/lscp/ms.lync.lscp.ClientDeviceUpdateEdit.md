---
title: Modification de Configuration journal de périphérique
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
description: Vous pouvez ajouter une configuration de journal de périphérique à la page Modifier la configuration de journal qui détermine la taille maximale du cache du journal, la taille maximale du journal ou la durée pendant laquelle qu'un fichier journal sera conservé avant la purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
ms.openlocfilehash: f933d71016b626648e6fb142af91872da4ed04ff
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2018
---
# <a name="device-log-configuration-edit"></a>Configuration de fichier journal de périphérique : modifier
 
Vous pouvez ajouter une configuration de journal de périphérique à la page **Modifier le paramètre de journal** qui détermine la taille maximale du cache du journal, la taille maximale du journal ou la durée pendant laquelle qu'un fichier journal sera conservé avant la purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
  
> [!CAUTION]
> Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer. 
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Modifier le paramètre de journal** :
  
- Ajouter une configuration de journal de périphérique globalement ou pour un site particulier.
    
- Modification des options d’une configuration de fichier journal d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Étendue** Identifie l’étendue (globale ou Site) de la configuration de journal de périphérique.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de journal de périphérique.
    
- **Taille maximale du fichier (octets)** Vous pouvez spécifier la taille maximale, qu'un fichier journal peut devenir avant la purge. La valeur par défaut est de 1,024,000 octets (1 Mo).
    
- **Taille maximale du cache (octets)** Vous pouvez spécifier la quantité maximale d’informations qui peuvent être conservées dans le cache du fichier journal avant que cache doit être désactivé et les données sont écrites dans un fichier journal (en octets). La valeur par défaut est 512,000 octets (0,5 Mo).
    
- **Minutes pour vider le cache (1 à 60)** Vous pouvez spécifier la fréquence à laquelle les informations stockées dans le cache du fichier journal sont écrit dans le fichier journal actuel. Une fois que les données sont enregistrées, le cache est désactivé. La valeur par défaut est de cinq minutes.
    
- **Jours de conservation des fichiers journaux (1-365)** Vous pouvez spécifier le nombre de jours pendant lesquels que les fichiers journaux sont conservés avant leur suppression. La valeur par défaut est de 10 jours.
    
## <a name="see-also"></a>Voir aussi

#### 

[Configuration de fichier journal de périphérique](ms.lync.lscp.ClientDeviceCfgMain.md)

