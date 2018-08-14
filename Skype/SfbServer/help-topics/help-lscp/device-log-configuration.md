---
title: Configuration du fichier journal du périphérique
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils. Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille de cache de données, taille du fichier journal ou la durée pendant laquelle qu'un fichier journal sera conservé avant la purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin. Les paramètres des journaux peuvent être modifiés au niveau global ou par site.
ms.openlocfilehash: 7fcd2ff0ff09daec267bbc80e70c2cb0e374c5ee
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503444"
---
# <a name="device-log-configuration"></a>Configuration du fichier journal du périphérique
 
Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils. Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille de cache de données, taille du fichier journal ou la durée pendant laquelle qu'un fichier journal sera conservé avant la purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin. Les paramètres des journaux peuvent être modifiés au niveau global ou par site.
  
> [!NOTE]
> Vous pouvez également configurer une heure à laquelle vous souhaitez que le service web de mise à jour des appareils supprime automatiquement les fichiers journaux dont l’ancienneté dépasse le nombre de jours de conservation configuré (par défaut, les fichiers journaux datant de plus de 10 jours sont supprimés). Ce paramètre ne peut pas être modifié à l’aide de Skype pour le panneau de configuration serveur Business. Au lieu de cela, vous devez utiliser Skype pour Business Server Management Shell. Pour spécifier l’heure du jour pour supprimer les fichiers journaux arrivés à expiration, utilisez l’applet de commande **New-CsDeviceUpdateConfiguration** avec le paramètre – LogCleanUpTimeOfDay. Pour plus d’informations, voir [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps). 
  
> [!CAUTION]
> Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer. 
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Configuration du fichier journal de l'appareil**, vous pouvez effectuer les tâches suivantes :
  
- Ajout d’une configuration de fichier journal d'appareil au niveau global ou pour un site ou un pool spécifique
    
- Modification des options d’une configuration de fichier journal d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Nouveau** Vous pouvez ajouter une nouvelle configuration de journal de périphérique avec l’étendue suivante :
    
  - Globale
    
  - Site
    
- **Modifier** Vous pouvez modifier les options de configuration d’un journal de périphérique dans la liste. Utilisez cette option, vous pouvez procédez comme suit :
    
  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options de configuration d’un journal de périphérique.
    
  - **Sélectionner tout** Cette option sélectionne toutes les configurations de fichier journal de périphérique dans la liste.
    
  - **Supprimer** Cette option supprime toutes les configurations de fichier journal de périphérique sélectionné.
    
- **Actualiser** Vous pouvez actualiser la liste de configuration de journal de périphérique pour vérifier le statut des options de configuration du fichier journal tous les périphériques.
    
## <a name="see-also"></a>Voir aussi

[Modifier les paramètres pour les fichiers journaux d’activité de mise à jour de périphérique](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)