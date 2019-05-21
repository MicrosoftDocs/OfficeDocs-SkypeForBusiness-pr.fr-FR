---
title: Numéro de téléphone non affecté création d’un nouveau ou modification existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 05b0d3efe383f2056ed49be7d8ebb811643cd02d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290047"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numéro de téléphone non attribué : en créer un autre ou en modifier un existant

> [!NOTE]
> La messagerie unifiée Exchange reste disponible dans Skype entreprise Server 2019 lorsque vous intégrez Skype entreprise 2019 avec Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est mise en évidence dans les fonctionnalités de messagerie vocale et de standard automatique Cloud.

Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.

> [!IMPORTANT]
> Lorsque vous avez terminé de créer une nouvelle plage de numéros non attribués ou d’en modifier une, cliquez sur **OK** pour revenir à la page **numéro non affecté** qui recense toutes les plages de nombres. Les modifications que vous avez effectuées dans la page **nouvelle plage de numéros non attribués** ou la page **modifier le numéro non affecté** ne sont pas validées dans la base de données tant que vous n’avez pas cliqué sur **valider tout** dans la page **numéro non attribué** .

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Tapez un nom descriptif identifiant la plage de nombres non attribués. Ce nom ne peut pas être modifié après enregistrement de la plage.

- **Plage de nombres** Dans le premier champ, tapez le numéro de début de la plage de nombres non attribués. Dans le deuxième champ, tapez le nombre de fin de la plage.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

  - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.

  - Le numéro doit correspondre à l’expression régulière (tel que ?\+() ? [1-9]{0,17}\d (; ext = [1-9]{0,9}\d) ?. Cela signifie que le numéro peut commencer par la chaîne «tel:» (si vous ne spécifiez pas cette chaîne, il sera automatiquement ajouté pour vous), un signe plus (+) et un chiffre 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.

- **Service d’annonce** Sélectionner **annonce** pour que l’application d’annonce gère l’appel entrant ou la **messagerie unifiée Exchange** pour qu’un standard automatique de messagerie unifiée Exchange gère l’appel entrant.

- Si vous avez sélectionné **annonce** pour le **service d’annonce**:

  - **Nom de domaine complet du serveur de destination** Sélectionnez l’ID du service d’application qui exécute l’application d’annonce qui traitera les appels entrants de cette plage de numéros non attribués.

  - **Annonce** Sélectionnez l’annonce à lire pour cette série de numéros non attribués.

- Si vous avez sélectionné **Exchange um** pour le **service d’annonce**:

  - **Numéro de téléphone du standard automatique** Sélectionnez le numéro de téléphone du standard automatique de messagerie unifiée Exchange.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités d’annonce, voir [planifier l’application d’annonce dans Skype entreprise](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation de plages de numéros non attribués, reportez-vous à la rubrique [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) de la documentation des opérations.


