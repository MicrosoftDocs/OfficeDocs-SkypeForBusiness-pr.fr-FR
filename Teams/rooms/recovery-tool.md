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
description: Cet article décrit l’utilisation de l’outil de récupération pour les salles Microsoft Teams, que vous utiliseriez pour mettre un système hors limites à l’état pris en charge.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117492"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utiliser l’outil de récupération de Microsoft Teams Rooms

Cet article décrit l’utilisation de l’outil de récupération pour les salles Microsoft Teams, que vous utiliseriez pour mettre un système hors limites à l’état pris en charge. Cet outil doit être appliqué lorsque la console de salles Microsoft Teams affiche une erreur « la config système est à jour » ou avant d’effectuer une restauration d’usine du bouton [de commande.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Conditions préalables

Téléchargez le [package d’installation de Salles Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) le plus récent et extrayez-le sur une clé USB ou un partage réseau accessible à l’appareil Salles Microsoft Teams.

> [!NOTE]
> L’extraction des fichiers du fichier MSI peut être réalisée par plusieurs moyens. Tout mécanisme qui extrait tous les fichiers et préserve leur structure d’annuaire est acceptable. Une de ces manières consiste à utiliser la commande qui représente le chemin d’accès complet au package d’installation de Microsoft Teams Room et représente le chemin d’accès complet au dossier dans lequel vous souhaitez extraire les `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` fichiers.

## <a name="running-the-tool"></a>Exécution de l’outil

1) Connectez-vous au compte d’administrateur sur votre appareil Salles Microsoft Teams et lancez une invite de commandes avec élévation de privilèges.
2) Vérifiez à partir de l’appareil Salles Microsoft Teams que vous pouvez accéder au fichier inclus dans les fichiers extraits du package d’installation de `RecoveryTool.ps1 file` Salles Microsoft Teams. Le kit est possible sur le partage réseau ou le lecteur USB utilisé lors de la préparation des conditions préalables.
3) `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`Exécuter.
4) Pour effectuer une restauration d’usine :
   1. Lorsque le script vous y invite, sélectionnez l’option 2 : **Réinitialiser.**
   2. Si BitLocker est sous, suivez les instructions fournies à la fin de la sortie du script pour la désactiver.
   3. Effectuez la restauration d’usine.
      1. Ouvrez **l’application Paramètres,** puis sélectionnez **Mettre à jour & sécurité**
      2. Accédez à **l’onglet** Récupération.
      3. Sous **Réinitialiser ce PC,** **sélectionnez Commencer**
      4. Sélectionnez **Supprimer tout,** puis **Suivant et** **Réinitialiser**
        > [!WARNING]
        > L’appareil Salles Microsoft Teams peut devenir inutilisable si l’option Conserver mes fichiers - Supprime les applications et les **paramètres,** mais conserve vos fichiers personnels est sélectionnée pendant le processus de réinitialisation de Windows. Ne sélectionnez pas cette option.
      5. Le système redémarre plusieurs fois. Une fois la réinitialisation terminée, le système sera sur l’écran « Out-out box experience » (OOBE) de Windows.



## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)