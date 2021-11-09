---
title: Masquage des numéros de téléphone Microsoft Teams réunions
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrir comment masquer des numéros de téléphone dans Microsoft Teams réunions
ms.openlocfilehash: afdbaa4f2f437728aad14e3731ab3e26ba90f36d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828427"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Masquage des numéros de téléphone Microsoft Teams réunions

Pour une confidentialité supplémentaire, les numéros de téléphone des participants qui appellent une réunion Teams à l’aide de l’audioconférence sont entièrement affichés aux participants internes. Les numéros sont masqués des participants extérieurs à votre organisation. Ce paramètre est le paramètre par défaut pour toutes les organisations. Le nombre masqué s’affiche comme illustré dans l’image suivante :

![Exemple de numéro de téléphone masqué.](media/hiddenPhoneNum.png)

Pour des cas d’utilisation spécifiques dans le secteur, les administrateurs ont la possibilité de choisir l’organisation des numéros de téléphone des participants à l’audioconférence dans les réunions organisées dans leur client. Les administrateurs ont le choix entre trois options :

- Téléphone de participants externes sont masqués uniquement. Les participants qui appartiennent au client de l’organisateur de la réunion voient toujours le numéro de téléphone complet.
- Téléphone numéros sont masqués pour toutes les personnes de la réunion à l’exception de l’organisateur.
- Téléphone de réunion ne sont pas tâches, ce qui les rend visibles à tous les autres personnes de la réunion.

Ce paramètre est appliqué à toutes les surfaces de la réunion où les numéros de téléphone sont exposés.

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