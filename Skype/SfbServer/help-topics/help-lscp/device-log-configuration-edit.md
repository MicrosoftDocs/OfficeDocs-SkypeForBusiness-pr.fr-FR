---
title: Modification de la configuration du journal des appareils
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
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Vous pouvez ajouter une configuration du journal de périphériques à la page modifier le paramètre du journal qui détermine la taille maximale du cache, la taille maximale du fichier journal ou la durée de conservation du fichier journal avant sa suppression définitive. Vous pouvez modifier ces paramètres en fonction de la configuration requise de votre organisation.
ms.openlocfilehash: 3ea368c0f3bccd7655d1bca3cb93a98a86b99c47
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822907"
---
# <a name="device-log-configuration-edit"></a>Configuration du fichier journal du périphérique : modifier
 
Vous pouvez ajouter une configuration du journal de périphériques à la page **modifier le paramètre du journal** qui détermine la taille maximale du cache, la taille maximale du fichier journal ou la durée de conservation du fichier journal avant sa suppression définitive. Vous pouvez modifier ces paramètres en fonction de la configuration requise de votre organisation.
  
> [!CAUTION]
> Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer. 
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **modifier le paramètre journal** , vous pouvez effectuer les tâches suivantes :
  
- Ajoutez une configuration du journal de périphériques globalement ou pour un site particulier.
    
- Modification des options d’une configuration de fichier journal d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Scope** Identifie l’étendue (globale ou site) de la configuration du journal des appareils.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration du journal de périphériques.
    
- **Taille de fichier maximale (octets)** Vous pouvez spécifier la taille maximale d’un fichier journal avant sa suppression définitive. La valeur par défaut est 1 024 000 octets (1 Mo).
    
- **Taille maximale du cache (octets)** Vous pouvez spécifier la quantité maximale d’informations (en octets) qui peut être stockée dans le cache du fichier journal avant que ce cache ne doit être vidé et que les données soient écrites dans un fichier journal. La valeur par défaut est 512 000 octets (0,5 Mo).
    
- **Minutes pour vider le cache (1-60)** Vous pouvez spécifier la fréquence à laquelle les informations stockées dans le cache du fichier journal sont écrites dans le fichier journal réel. Lorsque les données sont enregistrées, le cache est vidé. La valeur par défaut est 5 minutes.
    
- **Jours de conservation des fichiers journaux (1-365)** Vous pouvez spécifier le nombre de jours pendant lequel les fichiers journaux sont conservés avant d’être supprimés. La valeur par défaut est 10 jours.
    
## <a name="see-also"></a>Voir aussi

[Configuration du fichier journal du périphérique](device-log-configuration.md)
