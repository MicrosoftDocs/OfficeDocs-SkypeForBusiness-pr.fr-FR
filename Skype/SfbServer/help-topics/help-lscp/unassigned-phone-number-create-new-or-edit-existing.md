---
title: Numéro de téléphone non attribués créer ou modifier une existant
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 5e8648b94950750e6f750044ba4033fdf637c6f4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373669"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numéro de téléphone non attribués : Créer une nouvelle ou en modifier une existant

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

Pour plus d’informations sur les fonctionnalités d’annonce de, voir [planification de l’application d’annonce dans Skype pour Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des plages de numéros non attribués, voir [Configurer le routage des numéros non attribués téléphone](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) dans la documentation des opérations.


