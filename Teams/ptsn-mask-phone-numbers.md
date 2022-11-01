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
description: Découvrez comment masquer les numéros de téléphone dans les réunions Microsoft Teams
ms.openlocfilehash: cad28ad446c39a45b865fd24767347fdf11bb9c8
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801765"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Masquer les numéros de téléphone dans les réunions Microsoft Teams

Pour plus de confidentialité, les numéros de téléphone des participants qui se connectent à une réunion Teams à l’aide de l’audioconférence sont entièrement affichés aux participants internes. Les numéros sont masqués pour les participants en dehors de votre organisation. Ce paramètre est la valeur par défaut pour toutes les organisations. Le nombre masqué s’affiche comme illustré dans l’image suivante :

![exemple de numéro de téléphone masqué.](media/hiddenPhoneNum.png)

Pour des cas d’usage spécifiques du secteur, les administrateurs ont la possibilité de choisir la façon dont les numéros de téléphone des participants à l’audioconférence apparaissent dans les réunions organisées dans leur locataire. Les administrateurs peuvent choisir parmi trois options :

- Les numéros de téléphone sont masqués uniquement pour les participants externes. Les participants qui appartiennent au locataire de l’organisateur de la réunion voient toujours le numéro de téléphone complet.
- Les numéros de téléphone sont masqués pour tous les participants à la réunion, à l’exception de l’organisateur.
- Les numéros de téléphone sont démasqués, ce qui les rend visibles par tous les participants à la réunion.

Ce paramètre est appliqué à toutes les surfaces de la réunion où les numéros de téléphone sont exposés.

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>Utiliser le Centre d’administration Teams pour définir le masquage des numéros de téléphone

Pour modifier le paramètre de masquage du réseau téléphonique commuté (RTC) dans le Centre d’administration Teams, connectez-vous au centre d’administration Teams en tant qu’administrateur, sélectionnez **Ponts de conférence** **réunions** >  dans le panneau de navigation de gauche, puis sélectionnez **Paramètres du pont**. **Afficher les ID d’appelant masqués** est une liste déroulante en bas du volet Paramètres du pont, qui vous permet de choisir les éléments suivants :

- Aux participants en dehors de votre organisation
- À tous les participants à la réunion
- Désactivé

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Utiliser Microsoft PowerShell pour définir le masquage des numéros de téléphone

Pour modifier le paramètre de masquage RTC dans PowerShell, définissez le **`MaskPstnNumbersType`** paramètre de l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur l’une des options disponibles.

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
