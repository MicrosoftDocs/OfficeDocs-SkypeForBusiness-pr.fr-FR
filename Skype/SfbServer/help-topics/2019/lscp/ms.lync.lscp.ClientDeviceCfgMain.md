---
title: Configuration du fichier journal du périphérique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils. Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille du cache des données journal, la taille du fichier journal ou la durée de conservation du fichier journal avant sa suppression définitive. Vous pouvez modifier ces paramètres en fonction de la configuration requise de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin. Les paramètres des journaux peuvent être modifiés au niveau global ou par site.
ms.openlocfilehash: 7c4f532af6e74f8ef13b3b2de17017b66afc0b59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300471"
---
# <a name="device-log-configuration"></a>Configuration du fichier journal du périphérique

Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils. Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille du cache des données journal, la taille du fichier journal ou la durée de conservation du fichier journal avant sa suppression définitive. Vous pouvez modifier ces paramètres en fonction de la configuration requise de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin. Les paramètres des journaux peuvent être modifiés au niveau global ou par site.

> [!NOTE]
> Vous pouvez également configurer une heure à laquelle vous souhaitez que le service web de mise à jour des appareils supprime automatiquement les fichiers journaux dont l’ancienneté dépasse le nombre de jours de conservation configuré (par défaut, les fichiers journaux datant de plus de 10 jours sont supprimés). Ce paramètre ne peut pas être modifié dans le panneau de configuration Skype entreprise Server. À la place, vous devez utiliser Skype entreprise Server Management Shell. Pour spécifier l’heure du jour pour supprimer les fichiers journaux expirés, utilisez l’applet **de nouvelle applet de nouveau-CsDeviceUpdateConfiguration** avec le paramètre-LogCleanUpTimeOfDay. Pour plus d’informations, consultez la rubrique [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Configuration du fichier journal de l'appareil**, vous pouvez effectuer les tâches suivantes :

- Ajout d’une configuration de fichier journal d'appareil au niveau global ou pour un site ou un pool spécifique

- Modification des options d’une configuration de fichier journal d’appareil existante

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Nouvelle** Vous pouvez ajouter une nouvelle configuration du journal d’appareils avec l’étendue suivante:

  - Globale

  - Site

- **Modifier** Vous pouvez modifier les options de configuration du journal des appareils dans la liste. Cette option vous permet d’effectuer les opérations suivantes:

  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options de configuration du journal du périphérique.

  - **Tout sélectionner** Cette option sélectionne toutes les configurations du journal des appareils dans la liste.

  - **Supprimer** Cette option permet de supprimer l’ensemble de la configuration du journal de périphériques sélectionnée.

- **Actualiser** Vous pouvez actualiser la liste de configuration du journal des appareils pour vérifier le statut des options de toutes les configurations du journal des périphériques.

## <a name="see-also"></a>Voir aussi

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
