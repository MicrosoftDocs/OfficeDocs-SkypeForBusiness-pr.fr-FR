---
title: Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Résumé : Apprenez à configurer les stratégies de voix, les enregistrements d’utilisation de TLS et les itinéraires de voix dans Skype pour Business Server 2015.'
ms.openlocfilehash: d238703b98ebe532b2370456212760620c30ebf4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business-2015"></a>Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Skype Entreprise 2015
 
**Résumé :** Apprenez à configurer les stratégies de voix, les enregistrements d’utilisation de TLS et les itinéraires de voix dans Skype pour Business Server 2015.
  
Les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter à la stratégie des enregistrements d’utilisation RTC, qui spécifient les droits accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation RTC, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs ne peuvent effectuer que des appels utilisant des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation RTC correspondants.
  
La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer par configurer une stratégie de voix qui comprend les enregistrements d’utilisation RTC appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation RTC. 
  
> [!NOTE]
> Vous pouvez également créer des stratégies de voix avec la portée de *l’utilisateur* et les affecter à des utilisateurs individuels ou des groupes.
  
Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, reportez-vous aux procédures de cette section.
  
## <a name="in-this-section"></a>Contenu de cette section

- [Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](voice-policy-and-pstn-usage-records.md)
    
- [Configuration d’échappement de messagerie vocale dans Skype pour entreprise 2015](configure-voice-mail-escape.md)
    
- [Afficher les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](view-pstn-usage-records.md)
    
- [Créer ou modifier un itinéraire de voix dans Skype pour entreprise 2015](create-or-modify-a-voice-route.md)
    
- [Exporter ou importer un fichier de configuration de routage voix dans Skype pour entreprise 2015](voice-route-configuration-import-export.md)
    
- [Publier des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md)
    

