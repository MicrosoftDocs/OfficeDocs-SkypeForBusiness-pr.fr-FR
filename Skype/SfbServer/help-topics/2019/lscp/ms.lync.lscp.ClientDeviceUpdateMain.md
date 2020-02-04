---
title: Mise à jour du périphérique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft publie régulièrement un nouvel ensemble de mises à jour du microprogramme de l’appareil pour Skype entreprise Phone Edition, que vous pouvez importer sur vos serveurs et distribuer à des utilisateurs. Vous pouvez obtenir les dernières mises à jour de l’appareil en accédant à la page aide et support sur le site Web de Microsoft et en recherchant forPhone Edition. Téléchargez le package de mise à jour le plus récent et extrayez les fichiers dans un dossier sur l’ordinateur sur lequel les mises à jour doivent être téléchargées. Une fois les fichiers extraits, vous pouvez utiliser l’applet de commande Import-CsDeviceUpdate pour importer les règles de mise à jour des périphériques présentes dans le fichier CAB extrait (nommé UCUpdates.cab). Pour plus d’informations, voir Import-CsDeviceUpdate.
ms.openlocfilehash: d82010d45ae550c49529720496fc202abb2f6e4c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705139"
---
# <a name="device-update"></a>Mise à jour de l'appareil

Microsoft publie régulièrement un nouvel ensemble de mises à jour du microprogramme de l’appareil pour Skype entreprise Phone Edition, que vous pouvez importer sur vos serveurs et distribuer à des utilisateurs. Vous pouvez obtenir le dernier jeu de règles de mise à jour des périphériques en accédant à la page Aide et support du site web Microsoft et en recherchant « Phone Edition ». Téléchargez le dernier package de mise à jour et extrayez les fichiers vers un dossier sur l’ordinateur destiné à contenir les mises à jours. Une fois les fichiers extraits, vous pouvez utiliser l’applet de commande **Import-CsDeviceUpdate** pour importer les règles de mise à jour des périphériques présentes dans le fichier CAB extrait (nommé UCUpdates.cab). Pour plus d’informations, voir [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Une fois les règles de mise à jour de l’appareil importées, vous pouvez utiliser la page de **mise à jour** de l’appareil pour afficher et gérer ces règles pour les appareils de votre organisation.

> [!TIP]
> Vous pouvez tester les mises à jour de microprogramme, puis, si le test réussit, appliquer les mises à jour disponibles à tous les périphériques appropriés utilisés dans l’organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Mise à jour du périphérique**, vous pouvez effectuer les tâches suivantes :

- Approbation des mises à jour de périphérique répertoriées

- Annulation ou restauration des mises à jour de périphérique en attente

- Suppression des mises à jour de périphérique de la liste

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Modifier** Vous pouvez utiliser cette option pour effectuer les opérations suivantes :

  - **Tout sélectionner** Cette option sélectionne toutes les mises à jour de périphériques dans la liste.

  - **Supprimer** Cette option supprime toutes les mises à jour de périphériques sélectionnées.

- **Action** Vous pouvez sélectionner une ou plusieurs mises à jour dans la liste et effectuer les opérations suivantes :

  - **Annuler les mises à jour en attente** Cette option empêche le déploiement de la mise à jour sélectionnée sur les appareils de votre organisation.

  - **Approuver** Cette option permet de déployer la mise à jour sélectionnée sur les appareils de votre organisation.

  - **Restaurer** Cette option permet de déployer une mise à jour précédemment approuvée sur les appareils de votre organisation.

- **Actualiser** Vous pouvez actualiser la liste pour vérifier l’état de toutes les mises à jour de périphériques.

Pour plus d’informations sur le service web de mise à jour des appareils, reportez-vous à la rubrique [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) de la documentation de planification.
## <a name="see-also"></a>Voir aussi

[Importation-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
