---
title: Numéro de téléphone non attribués créer ou modifier une existant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 89990e7ec0de5f2f4423b4c2862518a8c46dae63
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835311"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numéro de téléphone non attribué : en créer un autre ou en modifier un existant

> [!NOTE]
> Messagerie unifiée Exchange reste disponible dans Skype pour Business Server 2019 lorsque vous intégrez Skype pour les entreprises 2019 avec Exchange 2013 ou 2016 Exchange. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est mis en évidence au profit des fonctionnalités de la messagerie vocale dans le nuage et de standard automatique de nuage.

Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.

> [!IMPORTANT]
> Lorsque vous avez terminé de créer une nouvelle plage de numéros non attribuée ou modifier un existant, cliquez sur **OK** pour revenir à la page **Numéro non attribué** qui répertorie toutes les plages de numéros. Les modifications effectuées sur la page **Nouveau Unassigned Number Range** ou la page **Modifier les Rage de numéro non attribué** ne sont pas validées dans la base de données jusqu'à ce que vous cliquez sur **valider tout** dans la page **Numéro non attribué** .

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Tapez un nom descriptif qui identifie la plage de numéros non attribuée. Une fois que vous enregistrez la plage, ce nom ne peut pas être modifié.

- **Numéro de plage** Dans le premier champ, tapez le numéro de début de la plage de numéros non attribué. Dans le deuxième champ, tapez le numéro de fin de la plage.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

  - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.

  - Le numéro doit correspondre à l’expression régulière (Tél. :) ? (\+) ? [1-9] \d{0,17}( ; ext = [1-9] \d{0,9}) ?. Cela signifie que le nombre peut commencer par la chaîne tel : (si vous ne spécifiez pas cette chaîne il est automatiquement ajouté pour vous), un signe plus (+) et un chiffre 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.

- **Service d’annonce** Sélectionnez **annonce** pour que l’application d’annonce à gérer l’appel entrant ou **Messagerie unifiée Exchange** pour utiliser un standard automatique Exchange UM pour gérer l’appel entrant.

- Si vous avez sélectionné **annonce** comme **service**d’annonce :

  - **Nom de domaine complet du serveur de destination** Sélectionnez l’ID de service du service d’Application qui exécute l’application d’annonce qui gèrera les appels entrants à cette plage de numéros non attribués.

  - **Annonce** Sélectionnez l’annonce à associer à cette plage de numéros non attribués.

- Si vous avez sélectionné **La messagerie unifiée Exchange** pour **le service d’annonce**:

  - **Numéro de téléphone de standard automatique** Sélectionnez le numéro de téléphone du standard automatique Exchange UM.

Pour plus d’informations sur les fonctionnalités d’annonce de, voir [planification de l’application d’annonce dans Skype pour les entreprises](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation de plages de numéros non attribués, reportez-vous à la rubrique [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) de la documentation des opérations.


