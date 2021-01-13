---
title: Activer la prise d’appel de groupe pour les utilisateurs et attribuer un numéro de groupe dans Skype Entreprise
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
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activez les utilisateurs pour la prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise et attribuez un numéro de groupe.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830964"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Activer la prise d’appel de groupe pour les utilisateurs et attribuer un numéro de groupe dans Skype Entreprise

Activez les utilisateurs pour la prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise et attribuez un numéro de groupe.

Après avoir ajouté des numéros de groupe de prise d’appel à la table des orbites de parcage d’appel, vous utilisez l’outil SEFAUtil pour affecter les numéros de groupe aux utilisateurs et activer la prise d’appel de groupe pour eux.

> [!NOTE]
> Dans un déploiement hybride, n’affectez pas de groupe de prise d’appel de groupe aux utilisateurs qui sont dos à dos en ligne. Les utilisateurs qui sont en ligne ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, leurs appels ne peuvent pas être répondus par d’autres utilisateurs et ils ne peuvent pas répondre aux appels à d’autres utilisateurs.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Pour affecter un numéro de groupe et activer la prise d’appel de groupe pour un utilisateur

1. Connectez-vous à l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2. À partir de la ligne de commande, exécutez la commande suivante :

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Par exemple, pour affecter le numéro de groupe 199 à un utilisateur :

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Voir aussi

[Désactiver la prise de groupe pour les utilisateurs](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

