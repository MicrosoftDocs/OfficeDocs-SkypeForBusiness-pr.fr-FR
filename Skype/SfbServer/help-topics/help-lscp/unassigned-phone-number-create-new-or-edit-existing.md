---
title: Numéro de téléphone non affecté, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: b4cdd3d4efad5299b855c546edf2359698ef6a47
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numéro de téléphone non affecté : Créer ou modifier une existante
 
Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
  
> [!IMPORTANT]
> Lorsque vous avez terminé la création d’une nouvelle plage de numéros non attribuée ou modifier une existante, cliquez sur **OK** pour revenir à la page **Numéro non assigné** qui répertorie toutes les plages de numéros. Les modifications effectuées sur la page de la **Nouvelle plage de nombre non affecté** ou de la page **Modifier les Rage de numéro non affecté** ne sont pas validées dans la base de données jusqu'à ce que vous cliquez sur **valider toutes** sur la page **Numéro non assigné** .
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Nom** Tapez un nom descriptif qui identifie la plage de numéros non attribuée. Après avoir enregistré la plage, ce nom ne peut pas être modifié.
    
- **Numéro de gamme** Dans le premier champ, tapez le numéro de début de la plage de numéros non attribué. Dans le second champ, tapez le numéro de fin de la plage.
    
  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.
    
  - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.
    
  - Le numéro doit correspondre à l’expression régulière (Tél :) ? (\+) ? [1-9], \d {0,17} ( ; ext = [1-9], \d {0,9}) ?. Cela signifie que le nombre peut commencer par la chaîne Tél. : (si vous ne spécifiez pas cette chaîne qu’il sera automatiquement ajouté pour vous), un signe plus (+) et un chiffre de 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.
    
- **Service d’annonce** Sélectionnez l' **annonce** à utiliser l’application de l’annonce pour gérer l’appel entrant ou **Messagerie unifiée d’Exchange** pour utiliser un Standard automatique de de messagerie unifiée Exchange pour gérer l’appel entrant.
    
- Si vous avez sélectionné **l’annonce** pour **service d’annonce**:
    
  - **Nom de domaine complet du serveur de destination** Sélectionnez l’ID de service du service d’Application qui exécute l’application de l’annonce qui doit gérer les appels entrants sur cette plage de numéros non attribués.
    
  - **Annonce** Sélectionnez l’annonce à être lu pour cette plage de numéros non attribués.
    
-  Si vous avez sélectionné de **Messagerie unifiée Exchange** pour le **service d’annonce**:
    
  - **Numéro de téléphone de Standard automatique** Sélectionnez le numéro de téléphone pour le Standard automatique de de messagerie unifiée Exchange.
    
Pour plus d’informations sur les fonctionnalités de l’annonce de, afficher un [Plan pour l’application de l’annonce dans Skype pour entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des plages de numéros non attribués, voir [Configurer le routage de non affecté numéros de téléphone dans la documentation sur les opérations.](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)
  

