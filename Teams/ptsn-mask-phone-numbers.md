---
title: Masquez les numéros de téléphone dans les réunions Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrir comment masquage des numéros de téléphone dans les réunions Microsoft Teams
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117712"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Masquez les numéros de téléphone dans les réunions Microsoft Teams

Pour une confidentialité supplémentaire, les numéros de téléphone des participants qui se appellent à une réunion Teams à l’aide de l’audioconférence sont entièrement affichés aux participants internes. Les numéros sont masqués des participants extérieurs à votre organisation. Ce paramètre est le paramètre par défaut pour toutes les organisations. Le nombre masqué s’affiche comme illustré dans l’image suivante :

![Exemple de numéro de téléphone masqué](media/hiddenPhoneNum.png)

Pour des cas d’utilisation spécifiques dans le secteur, les administrateurs ont la possibilité de choisir l’organisation des numéros de téléphone des participants à l’audioconférence dans les réunions organisées dans leur client. Les administrateurs ont le choix entre trois options :

- Les numéros de téléphone ne sont masqués que pour les participants externes. Les participants qui appartiennent au client de l’organisateur de la réunion voient toujours le numéro de téléphone complet.
- Les numéros de téléphone sont masqués pour toutes les personnes de la réunion à l’exception de l’organisateur.
- Les numéros de téléphone ne sont pas tâches, ce qui les rend visibles à tous les autres personnes de la réunion.

Ce paramètre s’applique à toutes les surfaces de la réunion où les numéros de téléphone sont exposés.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Utiliser Microsoft PowerShell pour définir le masquage des numéros de téléphone

Pour modifier le paramètre de masquage du réseau téléphonique commuté (PSTN), définissez le paramètre de **`MaskPstnNumbersType`** l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur l’une des options disponibles.

Pour masquer les numéros de téléphone des participants externes uniquement, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Pour masquer les numéros de téléphone de tous les participants à la réunion (à l’exception de l’organisateur), exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Pour désactiver le masquage des numéros de téléphone, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```