---
title: Activez le prélèvement d’appel de groupe pour les utilisateurs et attribuez un numéro de groupe dans Skype entreprise.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Autorisez les utilisateurs à obtenir des appels de groupe dans Skype entreprise Server Voice et attribuez un numéro de groupe.
ms.openlocfilehash: 78bdd78bf7e5bb3a9438a60b54a89664d22666ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240347"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Activez le prélèvement d’appel de groupe pour les utilisateurs et attribuez un numéro de groupe dans Skype entreprise.

Autorisez les utilisateurs à obtenir des appels de groupe dans Skype entreprise Server Voice et attribuez un numéro de groupe.

Dès lors que vous ajoutez des numéros de groupe de cueillette d’appel à la table d’orbite du parc d’appels, vous utilisez l’outil SEFAUtil pour attribuer les numéros de groupe aux utilisateurs et activer le prélèvement d’appels de groupe.

> [!NOTE]
> Dans un déploiement hybride, n’affectez pas de groupe de collecte d’appels de groupe aux utilisateurs hébergés en ligne. Les utilisateurs hébergés en ligne ne peuvent pas participer à la cueillette du groupe. Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Pour attribuer un numéro de groupe et activer le prélèvement d’appels de groupe pour un utilisateur

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

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

