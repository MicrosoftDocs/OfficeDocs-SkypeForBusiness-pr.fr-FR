---
title: Utiliser l’outil de récupération de Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021722"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utiliser l’outil de récupération de Microsoft Teams Rooms

Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge. Cet outil doit être appliqué lorsque le message d’erreur « configuration système obsolète » est affiché sur la console de Microsoft Teams, ou avant de procéder à la réinitialisation de la [restauration en usine](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Conditions préalables

Téléchargez le dernier [package d’installation de Microsoft teams](https://go.microsoft.com/fwlink/?linkid=851168) , puis récupérez-le sur une clé USB ou un partage réseau accessible à partir de l’appareil Microsoft Teams.

> [!NOTE]
> L’extraction des fichiers à partir du MSI peut être effectuée de diverses manières. Tout mécanisme qui extrait tous les fichiers et conserve leur structure d’annuaire est acceptable. Par exemple, vous pouvez utiliser la commande `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` où `PathToMsi` correspond au chemin d’accès complet au package d’installation de Microsoft Teams, puis `PathToTarget` correspond au chemin d’accès complet au dossier dans lequel vous voulez extraire les fichiers.

## <a name="running-the-tool"></a>Exécution de l’outil

1) Connectez-vous au compte d’administrateur sur votre appareil Microsoft Teams, puis lancez une invite de commandes avec élévation de privilèges.
2) Vérifiez à partir de l’appareil Microsoft teams qui vous permet d’accéder à la version `RecoveryTool.ps1 file` incluse dans les fichiers extraits du programme d’installation de Microsoft Teams. Le kit est disponible sur le partage réseau ou sur le lecteur USB utilisé pour préparer les éléments requis.
3) Exécuter `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Pour effectuer une restauration en usine :
   1. Lorsque vous y êtes invité par le script, sélectionnez l’option 2 : **Reset**.
   2. Si BitLocker est activé, suivez les instructions fournies à la fin de la sortie du script pour le désactiver.
   3. Effectuez la restauration en usine.
      1. Ouvrez l’application **paramètres** , puis sélectionnez **mettre à jour les & sécurité**
      2. Accédez à l’onglet **récupération** .
      3. Sous **réinitialiser ce PC**, sélectionnez **commencer** .
      4. Sélectionnez **Supprimer tout**, puis **suivant** et **Réinitialiser**
        > [!WARNING]
        > L’appareil de salle Microsoft teams peut devenir inutilisable si l’option **conserver mes fichiers-supprime des applications et des paramètres, mais conserve vos fichiers personnels** est sélectionnée lors du processus de réinitialisation de Windows. Ne sélectionnez pas cette option.
      5. Le système redémarre à plusieurs reprises. Lorsque la réinitialisation est terminée, le système se trouve sur l’écran de l’interface OOBE (out-of-Box Experience) de Windows.



## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)
