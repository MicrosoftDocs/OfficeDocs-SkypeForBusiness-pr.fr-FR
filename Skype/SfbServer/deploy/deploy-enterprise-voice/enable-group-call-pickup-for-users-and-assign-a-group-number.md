---
title: Activer la collecte d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype pour les entreprises
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activer les utilisateurs pour le groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, puis d’affecter un numéro de groupe.
ms.openlocfilehash: e182919023aab7757f975cbdccc509a0b62a77b9
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260005"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Activer la collecte d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype pour les entreprises

Activer les utilisateurs pour le groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, puis d’affecter un numéro de groupe.

Après avoir ajouté le groupe collecte d’appeler des numéros à la table d’orbite de parcage d’appel, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et activer la collecte d’appel de groupe pour qu’ils.

> [!NOTE]
> Dans un déploiement hybride, n’attribuez pas un groupe de collecte d’appel de groupe pour les utilisateurs hébergés en ligne. Les utilisateurs hébergés en ligne ne peuvent pas participer à la collecte d’appel de groupe. Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Pour affecter un numéro de groupe et activer la collecte d’appel de groupe pour un utilisateur

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

[Collecte de groupe désactiver pour les utilisateurs](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

