---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593645"
---
Avant de commencer, assurez-vous que vous avez les conditions préalables suivantes :

- Blue Yonder WFM version 2020.3, 2021.1 ou 2021.2.

    > [!NOTE]
    > Si vous avez Blue Yonder WFM 2020.3 ou 2021.1, appliquez le correctif 2020.3.0.4 ou 2021.1.0.3. Ce correctif corrige un problème dans lequel les utilisateurs obtiennent un message d’erreur permanente dans Shifts. Elle résout également un problème qui empêche les utilisateurs de mettre à jour leur disponibilité dans Shifts.

- Le nom et le mot de passe de votre compte de service Blue Yonder WFM et les URL de service :

    - URL d’authentification fédérée
    - URL d’authentification par cookies
    - URL du libre-service de l’employé
    - URL de l’API web De vente au détail
    - URL de l’API gestionnaire de site
    - URL de l’API Administration

    Si vous n’avez pas ces informations, contactez le support technique de Blue Yonder. Le compte est créé au niveau de l’entreprise racine par un administrateur d’entreprise Blue Yonder. Elle doit avoir accès à l’API, à l’administrateur client et au Gestionnaire de magasin. Le compte et le mot de passe sont requis pour créer une connexion.
- L’authentification SSO fédérée est activée dans votre environnement Blue Yonder WFM. Contactez le support Blue Yonder pour vous assurer que l’utilité SSO fédérée est activée. Ils auront besoin des informations suivantes :

    - federatedSSOValidationService : `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` où {tenantId} est votre tenantId
     - proxyHeader : X-MS-AuthToken

- Au moins une équipe est Teams.
- Vous avez ajouté votre Microsoft 365 système en tant que propriétaire d’équipe à toutes les équipes que vous souhaitez ma carte.</br> [Créez ce compte dans Microsoft 365](/microsoft-365/admin/add-users/add-users) et affectez-lui une Microsoft 365 licence. Ensuite, ajoutez le compte en tant que propriétaire d’équipe à toutes les équipes que vous voulez ma carte. Le connecteur Shifts utilise ce compte lors de la synchronisation des modifications de Shifts de Blue Yonder WFM.

    Nous vous recommandons de créer un compte spécifique à cet effet et de ne pas utiliser votre compte d’utilisateur.