---
title: Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Résumé : Découvrez comment configurer des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires de communication vocale dans Skype Entreprise Server.'
ms.openlocfilehash: 586aad64ae7585a275b0cce0e91497e0dea183d200693bbbf84e95e123bb392d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279332"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des Skype Entreprise
 
**Résumé :** Découvrez comment configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des Skype Entreprise Server.
  
Les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter des enregistrements d’utilisation PSTN à la stratégie, qui spécifient les droits qui sont accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation PSTN, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs peuvent uniquement effectuer des appels qui utilisent des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation PSTN correspondants.
  
La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer à configurer une stratégie de voix qui comprend les enregistrements d’utilisation PSTN appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation PSTN. 
  
> [!NOTE]
> Vous pouvez également créer des stratégies de voix avec  *une étendue*  utilisateur et les affecter à des utilisateurs ou des groupes individuels.
  
Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, voir les procédures dans cette section.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise](voice-policy-and-pstn-usage-records.md)
    
- [Configurer l’échappatoire de messagerie vocale dans Skype Entreprise](configure-voice-mail-escape.md)
    
- [Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise](view-pstn-usage-records.md)
    
- [Créer ou modifier un itinéraire de voix dans Skype Entreprise](create-or-modify-a-voice-route.md)
    
- [Exporter ou importer un fichier de configuration d’itinéraire des Skype Entreprise](voice-route-configuration-import-export.md)
    
- [Publier les modifications en attente de la configuration du routage des Skype Entreprise](voice-route-config-changes.md)
    

