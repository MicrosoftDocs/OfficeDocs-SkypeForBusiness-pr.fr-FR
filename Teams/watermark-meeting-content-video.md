---
title: Exiger un filigrane pour les réunions Teams sensibles
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Découvrez comment activer ou exiger des filigranes sur la vidéo des participants et le contenu partagé dans les réunions Teams sensibles.
ms.openlocfilehash: 6037bc6e9dbe79d9ecee10666f4c34e4e778216a
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950501"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>Exiger un filigrane pour les réunions Teams sensibles

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Vous pouvez activer l’affichage d’un filigrane dans les réunions Teams pour le contenu partagé à l’écran et pour la vidéo des participants. Le filigrane affiche l’adresse e-mail du participant à la réunion. Les participants à la réunion ne peuvent pas désactiver le filigrane.

Les filigranes sont pris en charge sur les ordinateurs de bureau et les appareils mobiles Teams. Personnes participer à des réunions à partir de plateformes non prises en charge aura une expérience audio uniquement.

Les participants qui rejoignent à partir de [Cloud Video Interop (CVI)](cloud-video-interop.md) pourront voir du contenu sans filigranes.

Les participants suivants ont une expérience audio uniquement lorsqu’un filigrane est utilisé :

- Participants utilisant le client web Teams
- Participants à l’infrastructure VDI (Virtual Desktop Infrastructure)
- Participants anonymes
- Participants de dépassement de capacité
- Salles Microsoft Teams sur Windows et Salles Microsoft Teams sur Surface Hub
- Salles Microsoft Teams sur Android
- Clients Teams plus anciens
- [Direct Guest Join sur les appareils Salles Microsoft Teams](/microsoftteams/rooms/third-party-join)

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité, les modèles de réunion personnalisés et les filigranes nécessitent Teams Premium.

Les filigranes de réunion sont activés dans le Centre d’administration Teams. Elles peuvent ensuite être ajoutées par l’organisateur de la réunion ou appliquées par un modèle ou une étiquette de confidentialité.

Le tableau suivant indique où les filigranes sont configurés :

|Paramètres|Administration stratégie|Étiquette de confidentialité|Modèle|Organisateur de la réunion|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Appliquer un filigrane au contenu partagé|Oui|Oui|Oui|Oui|
|Appliquer un filigrane au flux vidéo de tout le monde|Oui|Oui|Oui|Oui|

Lorsqu’un filigrane est utilisé dans une réunion, les fonctionnalités suivantes sont désactivées :

- Enregistrement de réunion, y compris l’enregistrement automatique

- Grande galerie

- Mode Ensemble

- PowerPoint Live

- Tableau blanc

- Contenu de l’appareil photo

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>Filigranes pour les réunions sensibles et hautement sensibles

Les filigranes peuvent être utiles pour protéger les informations confidentielles partagées dans les réunions. Cela est particulièrement utile lors du partage d’informations avec des personnes qui n’ont normalement pas accès à l’information. Par exemple, un membre de l’organisation financière peut utiliser des filigranes pour partager des estimations trimestrielles avec des responsables de différentes divisions.

Étant donné que les filigranes sont conçus pour réduire les risques que des informations confidentielles soient exfiltrées, leur utilisation dans des réunions où tous les participants ont un accès direct au contenu partagé peut ne pas contribuer à la sécurité.

Pour plus d’informations sur l’utilisation de filigranes avec d’autres fonctionnalités de réunion afin de protéger les informations confidentielles dans les réunions, consultez [Configurer des réunions Teams avec la protection des données hautement sensibles](/microsoftteams/configure-meetings-highly-sensitive-protection).

## <a name="enable-watermarks"></a>Activer les filigranes

Pour que les filigranes soient disponibles dans les modèles et les étiquettes de confidentialité, et pour l’organisateur de la réunion, ils doivent être activés dans le Centre d’administration Teams.

Pour activer le filigrane pour les réunions

1. Dans le Centre d’administration Teams, développez **Réunions** et sélectionnez **Stratégies de réunion**.

1. Sélectionnez la stratégie que vous souhaitez mettre à jour.

1. Pour activer le filigrane sur la vidéo du participant, définissez **Vidéos en filigrane** **sur Activé**.

1. Pour activer le filigrane sur le contenu partagé à l’écran dans une réunion, définissez **Contenu partagé** filigrane sur **Activé**.

    ![Capture d’écran de la stratégie d’administration Teams pour les filigranes](media/watermark-admin-policy.png)

1. Pour voir à quoi ressemblera le filigrane sur les appareils de bureau et mobiles, sélectionnez **Préversion**.

1. Sélectionnez **Enregistrer**.

Vous pouvez également activer ou désactiver les filigranes à l’aide de PowerShell. Utilisez l’applet de [commande Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) avec les `-AllowWatermarkForCameraVideo` paramètres et `-AllowWatermarkForScreenSharing` .

Par exemple :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles](meeting-templates-sensitivity-labels-policies.md)
