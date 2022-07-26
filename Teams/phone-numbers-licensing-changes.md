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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: Découvrez comment les modifications apportées aux licences peuvent affecter la gestion des numéros de téléphone.
ms.openlocfilehash: 58821f950baf68474a637a8d76acaab9a088f31e
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005461"
---
# <a name="how-licensing-affects-phone-number-management"></a>Comment la gestion des licences affecte la gestion des numéros de téléphone

La façon dont vous supprimez et attribuez des licences aux utilisateurs peut avoir un impact sur la capacité d’un utilisateur à passer et à recevoir des appels rtc (RTC) publics dans Microsoft Teams. Cet article explique comment gérer les modifications apportées aux licences pour garantir que la capacité de vos utilisateurs à effectuer et recevoir des appels RTC n’est pas affectée.

Pour obtenir des informations générales sur la gestion des numéros de téléphone, consultez [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md). Pour obtenir des informations générales sur les licences de module complémentaire Teams, consultez [les licences de module complémentaire Microsoft Teams](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>Supprimer une licence

Si vous avez un utilisateur avec un numéro de téléphone affecté et que vous supprimez une ou plusieurs des licences prérequises, la suppression de la licence supprime également le numéro de téléphone de l’utilisateur. Sans numéro de téléphone attribué, la capacité de l’utilisateur à effectuer et recevoir des appels RTC dans Microsoft Teams est affectée.

Selon [l’option de connectivité RTC](pstn-connectivity.md) de l’utilisateur, la suppression d’une licence a l’impact suivant sur les paramètres de téléphonie :

- **La suppression d’une licence de plan d’appel Microsoft 365 d’un utilisateur disposant d’un numéro de téléphone forfait d’appels** :
  - Copier n’importe quelle valeur dans OnPremLineUri vers LineUri
  - Définir EnterpriseVoiceEnabled sur False
  - Définir l’état d’affectation du numéro de téléphone sur Non affecté dans la base de données des numéros de téléphone


- **La suppression d’une licence Microsoft 365 Phone System d’un utilisateur disposant d’un numéro de téléphone Operator Connect** entraîne les opérations suivantes :
  - Effacer l’uri de ligne
  - Définir EnterpriseVoiceEnabled sur False
  - Définir l’état d’affectation du numéro de téléphone sur Non affecté dans la base de données des numéros de téléphone


- **La suppression d’une licence Microsoft 365 Phone System d’un utilisateur disposant d’un numéro de téléphone de routage direct** entraîne les opérations suivantes :
  - Effacer l’uri de ligne
  - Définir EnterpriseVoiceEnabled sur False
  - Supprimer le numéro de téléphone de la base de données du numéro de téléphone


## <a name="change-a-license"></a>Modifier une licence

Si vous devez modifier une licence pour un utilisateur qui implique l’une des licences prérequises, vous devez vous assurer que les modifications apportées aux licences sont apportées et enregistrées en même temps. Cette méthode garantit que l’utilisateur conserve son numéro de téléphone affecté et peut continuer à passer et à recevoir des appels RTC dans Microsoft Teams. 

Par exemple, supposons que vous souhaitez attribuer une licence Microsoft 365 E5 à un utilisateur qui dispose actuellement d’une licence Microsoft 365 E3. 

- Si vous utilisez le Centre d’administration Teams, sous l’onglet **Licences et applications** de l’utilisateur, vérifiez que l’ancienne licence est supprimée et que la nouvelle licence est ajoutée avant de cliquer sur **Enregistrer les modifications**. 

- Si vous utilisez les applets de commande PowerShell, [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) ou [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense), exécutez l’applet de commande une seule fois et utilisez les paramètres -AddLicenses et -RemoveLicenses.

(Si vous supprimez l’ancienne licence et enregistrez la modification, puis ajoutez la nouvelle licence et enregistrez la modification, le numéro de téléphone sera non attribué et l’utilisateur risque de perdre la possibilité d’effectuer et de recevoir des appels RTC dans Microsoft Teams. Après avoir attribué la nouvelle licence, vous devez réaffecter le numéro de téléphone à l’utilisateur.)










