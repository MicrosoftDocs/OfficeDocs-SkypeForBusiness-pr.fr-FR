---
title: Masquer les numéros de téléphone dans les réunions Microsoft Teams
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment masquer des numéros de téléphone dans les réunions Microsoft Teams
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270819"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Masquer les numéros de téléphone dans les réunions Microsoft Teams

Pour plus de confidentialité, les numéros de téléphone des participants qui composent une réunion Teams à l’aide de l’audioconférence sont entièrement affichés aux participants internes. Les numéros sont masqués des participants en dehors de votre organisation. Ce paramètre est la valeur par défaut pour toutes les organisations. Le numéro masqué s’affiche comme illustré dans l’image suivante :

![exemple de numéro de téléphone masqué.](media/hiddenPhoneNum.png)

Pour des cas d’utilisation spécifiques du secteur, les administrateurs peuvent choisir comment les numéros de téléphone des participants à l’audioconférence apparaissent dans les réunions organisées dans leur locataire. Les administrateurs peuvent choisir parmi trois options :

- Les numéros de téléphone sont masqués uniquement par les participants externes. Les participants qui appartiennent au locataire de l’organisateur de la réunion voient toujours le numéro de téléphone complet.
- Les numéros de téléphone sont masqués par tous les participants à la réunion, à l’exception de l’organisateur.
- Les numéros de téléphone sont masqués, ce qui les rend visibles par tous les participants à la réunion.

Ce paramètre est appliqué à toutes les surfaces de la réunion où les numéros de téléphone sont exposés.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Utiliser Microsoft PowerShell pour définir le masquage des numéros de téléphone

Pour modifier le paramètre de masquage du réseau téléphonique commuté (RTC), définissez le **`MaskPstnNumbersType`** paramètre de l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur l’une des options disponibles.

Pour masquer les numéros de téléphone uniquement des participants externes, exécutez la commande suivante :

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
