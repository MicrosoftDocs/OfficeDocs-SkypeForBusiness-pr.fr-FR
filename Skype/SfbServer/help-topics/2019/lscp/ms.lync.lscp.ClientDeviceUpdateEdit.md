---
title: Modification de la configuration du journal des périphériques
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Vous pouvez ajouter une nouvelle configuration de fichier journal de périphérique dans la page Modifier les paramètres de journalisation qui détermine la taille maximale du cache des journaux, la taille maximale des fichiers journaux ou la durée de conservation d’un fichier journal avant sa suppression. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.'
---

# <a name="device-log-configuration-edit"></a>Configuration du fichier journal de l’appareil : Modifier
 
Vous pouvez ajouter une nouvelle configuration de fichier journal de périphérique dans la page **Modifier les paramètres de journalisation** qui détermine la taille maximale du cache des journaux, la taille maximale des fichiers journaux ou la durée de conservation d’un fichier journal avant sa suppression. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
  
> [!CAUTION]
> Cette suppression les élimine définitivement du système de fichiers. Après avoir supprimé définitivement un fichier, vous ne pouvez pas le récupérer. 
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Modifier les paramètres de journalisation** :
  
- Ajouter une configuration de fichier journal de périphérique globalement ou pour un site particulier
    
- Modifier les options d’une configuration de fichier journal de périphérique existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.
  
- **Étendue** Identifie l’étendue (globale ou site) de la configuration du journal de périphérique.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration du journal de périphérique.
    
- **Taille maximale du fichier (octets)** Vous pouvez spécifier la taille maximale qu’un fichier journal peut atteindre avant d’être purgé. La valeur par défaut est 1 024 000 octets (1 Mo).
    
- **Taille maximale du cache (octets)** Vous pouvez spécifier la quantité maximale d’informations (en octets) qui peut être détenue dans le cache des fichiers journaux avant que ce cache ne soit effacé et que les données soient écrites dans un fichier journal. La valeur par défaut est 512 000 octets (0,5 Mo).
    
- **Minutes de purge du cache (1-60)** Vous pouvez spécifier la fréquence à quelle fréquence les informations stockées dans le cache des fichiers journaux sont écrites dans le fichier journal réel. Une fois les données enregistrées, le cache est effacé. La valeur par défaut est cinq minutes.
    
- **Jours de conserver les fichiers journaux (1-365)** Vous pouvez spécifier le nombre de jours pendant combien de jours les fichiers journaux sont conservés avant leur purge. La valeur par défaut est 10 jours.
    
## <a name="see-also"></a>Voir aussi

[Configuration du fichier journal du périphérique](ms.lync.lscp.ClientDeviceCfgMain.md)
