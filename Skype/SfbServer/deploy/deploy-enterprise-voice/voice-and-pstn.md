---
title: Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour les entreprises
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Résumé : Découvrez comment configurer des stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour Business Server.'
ms.openlocfilehash: 37cc90e76a4ebf93ebd1ab1d61595b7fb8f6db38
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222532"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour les entreprises
 
**Résumé :** Découvrez comment configurer des stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour Business Server.
  
Les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter à la stratégie des enregistrements d’utilisation RTC, qui spécifient les droits accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation RTC, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs ne peuvent effectuer que des appels utilisant des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation RTC correspondants.
  
La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer par configurer une stratégie de voix qui comprend les enregistrements d’utilisation RTC appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation RTC. 
  
> [!NOTE]
> Vous pouvez également créer des stratégies de voix avec l’étendue *utilisateur* et les affecter à des utilisateurs individuels ou des groupes.
  
Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, reportez-vous aux procédures de cette section.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises](voice-policy-and-pstn-usage-records.md)
    
- [Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises](configure-voice-mail-escape.md)
    
- [Afficher les enregistrements d’utilisation PSTN dans Skype pour les entreprises](view-pstn-usage-records.md)
    
- [Créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md)
    
- [Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype pour les entreprises](voice-route-configuration-import-export.md)
    
- [Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md)
    

