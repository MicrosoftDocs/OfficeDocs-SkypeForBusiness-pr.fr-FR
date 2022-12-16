---
title: Numéros de téléphone et modifications des licences
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: Découvrez comment les modifications de licence peuvent affecter la gestion des numéros de téléphone.
ms.openlocfilehash: f75c5aeea577163e9f3ee6d1d4302836de0d1e7e
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414671"
---
# <a name="how-licensing-affects-phone-number-management"></a>Impact des licences sur la gestion des numéros de téléphone

La façon dont vous supprimez et attribuez des licences aux utilisateurs peut avoir un impact sur la capacité d’un utilisateur à passer et à recevoir des appels RTC (Public Switched Telephone Network) dans Microsoft Teams. Cet article explique comment gérer les modifications de licences pour vous assurer que la capacité de vos utilisateurs à passer et à recevoir des appels RTC n’est pas impactée.

Pour obtenir des informations générales sur la gestion des numéros de téléphone, consultez [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md). Pour obtenir des informations générales sur les licences des modules complémentaires Teams, consultez [Microsoft licences de module complémentaire Teams](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>Supprimer une licence

Si vous avez un utilisateur avec un numéro de téléphone attribué et que vous supprimez une ou plusieurs des licences requises, la suppression de la licence annule également l’affectation du numéro de téléphone de l’utilisateur. Sans numéro de téléphone attribué, la capacité de l’utilisateur à passer et à recevoir des appels RTC dans Microsoft Teams est impactée.

Selon [l’option de connectivité RTC](pstn-connectivity.md) de l’utilisateur, la suppression d’une licence a l’impact suivant sur les paramètres de téléphonie :

- **La suppression d’une licence de forfait d’appels Microsoft 365 d’un utilisateur disposant d’un numéro de téléphone de forfait d’appels** :
  - Copier n’importe quelle valeur dans OnPremLineUri dans LineUri
  - Définissez EnterpriseVoiceEnabled sur False
  - Définissez l’état d’attribution de numéro de téléphone sur Non affecté dans la base de données de numéros de téléphone


- **La suppression d’une licence de système téléphonique Microsoft 365 d’un utilisateur disposant d’un numéro de téléphone Operator Connect** permet de :
  - Effacer LineUri
  - Définissez EnterpriseVoiceEnabled sur False
  - Définissez l’état d’affectation du numéro de téléphone sur Non affecté dans la base de données de numéros de téléphone


- **La suppression d’une licence de système téléphonique Microsoft 365 d’un utilisateur avec un numéro de téléphone de routage direct** :
  - Effacer LineUri
  - Définissez EnterpriseVoiceEnabled sur False
  - Supprimer le numéro de téléphone de la base de données de numéros de téléphone


## <a name="change-a-license"></a>Modifier une licence

Si vous devez modifier une licence pour un utilisateur qui implique l’une des licences requises, vous devez vous assurer que les modifications de licence sont apportées et enregistrées en même temps. Cette méthode garantit que l’utilisateur conserve le numéro de téléphone qui lui a été attribué et peut continuer à passer et à recevoir des appels RTC dans Microsoft Teams. 

Par exemple, supposons que vous souhaitiez attribuer une licence Microsoft 365 E5 à un utilisateur qui dispose actuellement d’une licence Microsoft 365 E3. 

- Si vous utilisez le Centre d’administration Teams, sous l’onglet **Licences et applications** des détails de l’utilisateur, vérifiez que l’ancienne licence est supprimée et que la nouvelle licence est ajoutée avant de cliquer sur **Enregistrer les modifications**. 

- Si vous utilisez les applets de commande PowerShell, [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) ou [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense), exécutez l’applet de commande une seule fois et utilisez les paramètres -AddLicenses et -RemoveLicenses.

(Si vous supprimez l’ancienne licence et enregistrez la modification, puis ajoutez la nouvelle licence et enregistrez la modification, le numéro de téléphone n’est pas attribué et l’utilisateur risque de perdre la possibilité d’effectuer et de recevoir des appels RTC dans Microsoft Teams. Après avoir attribué la nouvelle licence, vous devrez ré-attribuer le numéro de téléphone à l’utilisateur.)

Pour plus d’informations sur la façon de modifier la licence simultanément avec les [licences basées sur un groupe, consultez Modifier les attributions de licences pour un utilisateur ou un groupe dans Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-change-licenses).
