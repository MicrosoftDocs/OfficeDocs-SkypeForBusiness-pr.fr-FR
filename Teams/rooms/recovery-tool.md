---
title: Utiliser l’outil de récupération de Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge.
ms.openlocfilehash: 3a62256a5e39d93033588ca2be779e9c3b76a4f5
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268897"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utiliser l’outil de récupération de Microsoft Teams Rooms

Cet article explique comment utiliser l’outil de récupération pour les salles de Microsoft Teams, que vous utiliseriez pour mettre à jour un système obsolète dans un État pris en charge. Cet outil doit être appliqué lorsque le message d’erreur « configuration système obsolète » est affiché sur la console de Microsoft Teams, ou avant de procéder à la réinitialisation de la [restauration en usine](https://docs.microsoft.com/microsoftteams/room-systems/rooms-operations#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Conditions requises

Téléchargez le dernier [package d’installation de Microsoft teams](https://go.microsoft.com/fwlink/?linkid=851168) , puis récupérez-le sur une clé USB ou un partage réseau accessible à partir de l’appareil Microsoft Teams.

> [!NOTE]
> L’extraction des fichiers à partir du MSI peut être effectuée de diverses manières. Tout mécanisme qui extrait tous les fichiers et conserve leur structure d’annuaire est acceptable. Par exemple, vous pouvez utiliser la commande `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` où `PathToMsi` correspond au chemin d’accès complet au package d’installation de Microsoft Teams, puis `PathToTarget` correspond au chemin d’accès complet au dossier dans lequel vous voulez extraire les fichiers.

## <a name="running-the-tool"></a>Exécution de l’outil

1) Connectez-vous au compte d’administrateur sur votre appareil Microsoft Teams, puis lancez une invite de commandes avec élévation de privilèges.
2) Vérifiez à partir de l’appareil Microsoft teams qui vous permet d’accéder `RecoveryTool.ps1 file`à la version incluse dans les fichiers extraits du programme d’installation de Microsoft Teams. Le kit est disponible sur le partage réseau ou sur le lecteur USB utilisé pour préparer les éléments requis.
3) Exécuter `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Si vous effectuez une restauration en usine :
   - Lorsque vous y êtes invité par le script, sélectionnez l’option 2 : **Reset**.
   - Si BitLocker est activé, suivez les instructions fournies à la fin de la sortie du script pour le désactiver.
   - Effectuez la restauration en usine.
      - Ouvrez l’application **paramètres** , puis sélectionnez **mettre à jour les & sécurité**
      - Accédez à l’onglet **récupération** .
      - Sous **réinitialiser ce PC**, sélectionnez **commencer** .
      - Sélectionnez **Supprimer tout**, puis **suivant** et **Réinitialiser**
      - Le système redémarre à plusieurs reprises. Lorsque le rétablissement est terminé, le système se trouve sur l’écran OOBE Windows.
5) Si vous réparez un système à jour :
    - Lorsque vous y êtes invité par le script, sélectionnez option 1 : **réparer**.
    - Lorsque vous avez terminé, redémarrez l’appareil Microsoft Teams. Elle redémarrera automatiquement et sera entièrement récupérée la deuxième fois.

> [!NOTE]
> Il existe un problème connu pour lequel les salles de Microsoft teams peuvent être désactivées si l’option **conserver mes fichiers-supprime des applications et des paramètres, mais** que vous avez sélectionné l’option conservation de vos fichiers personnels lors du processus de réinitialisation de Windows. N’utilisez *pas* cette option.

## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)
