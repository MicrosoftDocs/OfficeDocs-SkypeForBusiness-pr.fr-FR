---
title: Activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activer les utilisateurs pour la collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise et affecter un numéro de groupe.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a>Activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe dans Skype Entreprise 2015
 
Activer les utilisateurs pour la collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise et affecter un numéro de groupe.
  
Après avoir ajouté des numéros de groupe collecte d’appel à la table des appels park orbite, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et l’activer pour ceux-ci la collecte d’appeler de groupe.
  
> [!NOTE]
> Dans un déploiement hybride, n’affectez pas un groupe de prise d’appel de groupe pour les utilisateurs qui sont hébergés en ligne. Les utilisateurs qui sont hébergées en ligne ne peuvent pas participer à la collecte d’appeler de groupe. Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs. 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Pour affecter un numéro de groupe et activer la collecte d’appeler de groupe pour un utilisateur

1. Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.
    
2. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Par exemple, pour assigner le numéro de groupe 199 à un utilisateur, procédez comme suit :
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a>Voir aussi

#### 

[Remise en mains propres groupe de désactivation pour les utilisateurs](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

