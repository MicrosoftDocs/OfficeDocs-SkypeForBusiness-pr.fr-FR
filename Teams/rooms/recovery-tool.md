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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cet article explique comment utiliser l’outil de récupération pour Salles Microsoft Teams, que vous utiliseriez pour mettre un système obsolète dans un état pris en charge.
ms.openlocfilehash: 70b2d199c4fe13138e2f46fd0b49e95efbd18e9c
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706163"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utiliser l’outil de récupération de Microsoft Teams Rooms

Cet article explique comment utiliser l’outil de récupération pour Salles Microsoft Teams, que vous utiliseriez pour mettre un système obsolète dans un état pris en charge. Cet outil doit être appliqué lorsque la console Salles Microsoft Teams affiche une erreur « configuration système obsolète » ou avant d’effectuer une [restauration d’usine](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore) de réinitialisation du bouton Push.

## <a name="prerequisites"></a>Conditions préalables

Téléchargez le [dernier package d’installation Salles Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) et extrayez-le dans une clé mémoire USB ou un partage réseau accessible à Salles Microsoft Teams.

> [!NOTE]
> L’extraction des fichiers à partir du MSI peut être effectuée par de nombreux moyens. Tout mécanisme qui extrait tous les fichiers et conserve leur structure de répertoires est acceptable. L’une de ces méthodes consiste à utiliser la commande `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` où `PathToMsi` représente le chemin d’accès complet au package d’installation Salles Microsoft Teams et `PathToTarget` représente le chemin d’accès complet au dossier dans lequel vous souhaitez extraire les fichiers.

## <a name="running-the-tool"></a>Exécution de l’outil

1) Connectez-vous au compte d’administrateur sur votre appareil Salles Microsoft Teams et lancez une invite de commandes avec élévation de privilèges.
2) Vérifiez à partir de l’appareil Salles Microsoft Teams que vous êtes en mesure d’accéder au `RecoveryTool.ps1` fichier, qui est inclus dans les fichiers extraits du package d’installation Salles Microsoft Teams. Le kit se trouve sur le partage réseau ou le lecteur USB utilisé lors de la préparation des prérequis.
3) Exécuter `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Pour effectuer une restauration d’usine :
   1. Lorsque vous y êtes invité par le script, sélectionnez l’option 2 : **Réinitialiser**.
   2. Si BitLocker est activé, suivez les instructions fournies à la fin de la sortie du script pour la désactiver.
   3. Effectuez la restauration d’usine.
      1. Ouvrez l’application **Paramètres** , puis sélectionnez **Mettre à jour & Sécurité**
      2. Accédez à l’onglet **Récupération** .
      3. Sous **Réinitialiser ce PC**, **sélectionnez Prise en main**
      4. Sélectionnez **Tout supprimer**, puis **Suivant** et **Réinitialiser**
        > [!WARNING]
        > L’appareil Salles Microsoft Teams peut devenir inutilisable si l’option **Conserver mes fichiers - Supprime les applications et les paramètres, mais conserve votre option fichiers personnels** est sélectionnée pendant le processus de réinitialisation de Windows. Ne sélectionnez pas cette option.
      5. Le système redémarre plusieurs fois. Une fois la réinitialisation terminée, le système se trouve sur l’écran OOBE (Out of Box Experience) de Windows.



## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)
