---
title: Mise à jour du périphérique
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: 'NOINDEX, NOFOLLOW'
description: "Microsoft publie régulièrement un nouvel ensemble de mises à jour de microprogramme d’appareil pour Skype Entreprise Téléphone Edition, que vous pouvez importer sur vos serveurs et distribuer aux utilisateurs. Vous pouvez obtenir le dernier ensemble de règles de mise à jour des périphériques en allant sur la page Aide et support sur le site web Microsoft et en recherchantPhone Edition.Téléchargez le dernier package de mise à jour et extrayez les fichiers dans un dossier sur l’ordinateur sur lequel les mises à jour doivent être téléchargées. Une fois les fichiers extraits, vous pouvez utiliser l’applet de commande Import-CsDeviceUpdate pour importer les règles de mise à jour des périphériques présentes dans le fichier\_.CAB extrait (nommé UCUpdates.cab). Pour plus d’informations, voir Import-CsDeviceUpdate."
---

# <a name="device-update"></a>Mise à jour de l’appareil

Microsoft publie régulièrement un nouvel ensemble de mises à jour de microprogramme d’appareil pour Skype Entreprise Téléphone Edition, que vous pouvez importer sur vos serveurs et distribuer aux utilisateurs. Vous pouvez obtenir le dernier jeu de règles de mise à jour des périphériques en accédant à la page Aide et support du site web Microsoft et en recherchant « Phone Edition ». Téléchargez le dernier package de mise à jour et extrayez les fichiers vers un dossier sur l’ordinateur destiné à contenir les mises à jours. Une fois les fichiers extraits, vous pouvez utiliser l’applet de commande **Import-CsDeviceUpdate** pour importer les règles de mise à jour des périphériques présentes dans le fichier .CAB extrait (nommé UCUpdates.cab). Pour plus d’informations, [voir Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Une fois les règles de mise à jour des périphériques importées, vous pouvez utiliser **la page Mise** à jour des périphériques pour afficher et gérer ces règles pour les appareils de votre organisation.

> [!TIP]
> Vous pouvez tester les mises à jour de microprogramme, puis, si le test est réussi, appliquer les mises à jour disponibles à tous les périphériques appropriés utilisés dans l’organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Mise à jour du périphérique** :

- Approuver les mises à jour de périphérique répertoriées.

- Annuler ou restaurer les mises à jour de périphérique en attente.

- Supprimer des mises à jour de périphérique de la liste.

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Modifier** Vous pouvez utiliser cette option pour :

  - **Sélectionner tout** Cette option sélectionne toutes les mises à jour de périphériques dans la liste.

  - **Supprimer** Cette option supprime toutes les mises à jour de périphérique sélectionnées.

- **Action** Vous pouvez sélectionner une ou plusieurs mises à jour dans la liste et prendre les mesures suivantes :

  - **Annuler les mises à jour en attente** Cette option empêche le déploiement de la mise à jour sélectionnée sur les appareils de votre organisation.

  - **Approuver** Cette option permet de déployer la mise à jour sélectionnée sur les appareils de votre organisation.

  - **Restaurer** Cette option permet le déploiement d’une mise à jour précédemment approuvée sur les appareils de votre organisation

- **Actualiser** Vous pouvez actualiser la liste pour vérifier l’état de toutes les mises à jour de périphériques.

Pour plus d’informations sur le service web de mise à jour des appareils, voir [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) dans la documentation de planification.
## <a name="see-also"></a>Voir aussi

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)