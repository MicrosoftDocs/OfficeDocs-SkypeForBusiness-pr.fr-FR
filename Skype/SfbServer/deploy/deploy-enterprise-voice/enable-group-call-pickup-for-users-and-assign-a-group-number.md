---
title: Activer la prise d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Activez les utilisateurs pour la prise d’appel de Skype Entreprise Server Voix Entreprise et attribuez un numéro de groupe.
ms.openlocfilehash: ab98244c570acbd7354abb7b7f6bed2fd85cf407
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864351"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Activer la prise d’appel de groupe pour les utilisateurs et affecter un numéro de groupe dans Skype Entreprise

Activez les utilisateurs pour la prise d’appel de Skype Entreprise Server Voix Entreprise et attribuez un numéro de groupe.

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

[Désactiver la prise de groupe pour les utilisateurs](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)