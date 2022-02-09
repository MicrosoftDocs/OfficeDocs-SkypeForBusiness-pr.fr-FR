---
title: Configuration du fichier journal du périphérique
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des périphériques. Dans le cadre de la stratégie de gestion des données de votre organisation, vous pouvez définir des seuils sur la taille du cache de données du journal, la taille des fichiers journaux ou la durée de la durée de la mise à jour d’un fichier journal avant sa purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, le cas échéant. Les paramètres des journaux peuvent être modifiés globalement ou par site.
ms.openlocfilehash: d62265e382d87b3d20f0c9ac0fe2a5dca869bfef
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401488"
---
# <a name="device-log-configuration"></a>Configuration du fichier journal de l’appareil

Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des périphériques. Dans le cadre de la stratégie de gestion des données de votre organisation, vous pouvez définir des seuils sur la taille du cache de données du journal, la taille des fichiers journaux ou la durée de la durée de la mise à jour d’un fichier journal avant sa purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, le cas échéant. Les paramètres des journaux peuvent être modifiés globalement ou par site.

> [!NOTE]
> Vous pouvez également configurer une heure à laquelle vous souhaitez que le service web de mise à jour des appareils supprime automatiquement les fichiers journaux dont l’ancienneté dépasse le nombre de jours de conservation que vous avez configuré (par défaut, les fichiers journaux de plus de 10 jours sont supprimés). Ce paramètre ne peut pas être modifié à l’Skype Entreprise Server panneau de configuration. À la place, vous devez utiliser Skype Entreprise Server Management Shell. Pour spécifier l’heure de suppression des fichiers journaux expirés, utilisez **l’cmdlet New-CsDeviceUpdateConfiguration** avec le paramètre -LogCleanUpTimeOfDay. Pour plus d’informations, [voir New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Cette suppression les élimine définitivement du système de fichiers. Après avoir supprimé définitivement un fichier, vous ne pouvez pas le récupérer.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Configuration du fichier journal du périphérique** :

- Ajouter une configuration de fichier journal de périphérique globalement ou pour un site ou un pool particulier

- Modifier les options d’une configuration existante de fichier journal de périphérique

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Nouveau** Vous pouvez ajouter une nouvelle configuration de fichier journal d’appareil avec l’étendue suivante :

  - Global

  - Site

- **Modifier** Vous pouvez modifier les options d’une configuration de journal d’appareil dans la liste. À l’aide de cette option, vous pouvez effectuer les opérations suivantes :

  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une configuration de journal d’appareil.

  - **Sélectionner tout** Cette option sélectionne toute la configuration du journal d’appareil dans la liste.

  - **Supprimer** Cette option supprime toutes les configurations de journal d’appareil sélectionnées.

- **Actualiser** Vous pouvez actualiser la liste de configuration des journaux de périphériques pour vérifier l’état des options de toutes les configurations du journal d’appareil.

## <a name="see-also"></a>Voir aussi

[Modifier les Paramètres fichiers journaux de l’activité de mise à jour des périphériques](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)