---
title: Exiger un chiffrement de bout en bout pour les réunions Teams sensibles
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
description: Découvrez comment activer le chiffrement de bout en bout pour les réunions Teams.
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800146"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>Exiger un chiffrement de bout en bout pour les réunions Teams sensibles

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Le chiffrement de bout en bout est le chiffrement des informations à leur origine et le déchiffrement à leur destination prévue sans la possibilité pour les nœuds intermédiaires de déchiffrer. Lorsque les réunions dans Teams sont chiffrées de bout en bout, personne, à l’exception des participants à la réunion, ne peut entendre ou voir la communication. Aucun tiers, y compris Microsoft, n’a accès à la conversation déchiffrée.

Les réunions chiffrées de bout en bout peuvent être organisées entre deux parties : les parties utilisent la dernière version du client de bureau Teams pour Windows ou Mac, elles se trouvent sur un appareil mobile avec la dernière mise à jour pour iOS et Android, ou sur un salles Teams sur un appareil Windows à l’aide de la dernière mise à jour. Le chiffrement de bout en bout pour les réunions suivies via le navigateur n’est pas pris en charge.

> [!Note]
> Le chiffrement de réunion de bout en bout nécessite Teams Premium.

Si vous n’activez pas le chiffrement de bout en bout, Teams sécurise toujours les réunions à l’aide du chiffrement en fonction des normes du secteur. Les données échangées pendant les réunions sont toujours sécurisées pendant le transit et au repos. Pour plus d’informations, voir [Chiffrement des médias pour Teams](teams-security-guide.md#media-encryption).

Au cours d’une réunion chiffrée de bout en bout, Teams sécurise les fonctionnalités suivantes :

- Audio

- Vidéo

- Partage d’écran

[Le chiffrement dans Microsoft 365](/microsoft-365/compliance/encryption) protège la conversation, le partage de fichiers, la présence et tout autre contenu dans la réunion. Les applications, avatars, réactions, conversation et Q&A ne sont pas chiffrés de bout en bout.

Les fonctionnalités suivantes ne sont pas disponibles pendant une réunion chiffrée de bout en bout :

- Sous-titres en direct et transcription

- Enregistrement

- Mode Ensemble, mode compagnon, grande galerie

- Salles de réunion

Si votre organisation utilise l’enregistrement de conformité, le chiffrement de bout en bout n’est pas disponible. Pour plus d’informations sur la façon dont Teams prend en charge l’enregistrement de conformité, voir [Présentation de l’enregistrement basé sur une stratégie Teams pour les appels et les réunions](teams-recording-policy.md).

## <a name="enable-end-to-end-encryption-for-meetings"></a>Activer le chiffrement de bout en bout pour les réunions

Par défaut, le chiffrement de bout en bout pour les réunions n’est pas activé. Vous pouvez l’activer à l’aide d’une stratégie de chiffrement améliorée de l’administrateur Teams.

Une fois le chiffrement de bout en bout activé, les organisateurs de réunion ont la possibilité de choisir le chiffrement de bout en bout, puis de créer une réunion. Vous pouvez également appliquer un chiffrement de bout en bout à l’aide d’un modèle de réunion ou d’une étiquette de confidentialité.

Pour activer le chiffrement de bout en bout pour les réunions

1. Dans le Centre d’administration Teams, sélectionnez **Stratégie de chiffrement améliorée**.

1. Sélectionnez la stratégie que vous souhaitez mettre à jour.

1. Définissez **Chiffrement de réunion de** bout en bout sur **Non activé, mais les utilisateurs peuvent remplacer**.

1. Sélectionnez **Enregistrer**.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Utilisez le cryptage de bout en bout pour les appels Microsoft Teams entre particuliers.](teams-end-to-end-encryption.md)
