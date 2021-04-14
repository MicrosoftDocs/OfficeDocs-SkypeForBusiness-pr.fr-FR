---
title: Gérer les stratégies de mise en application dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies de configuration d'application dans Microsoft Teams pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ee50af6dec780480b8efdbf39dabb8e52ff03f3a
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697709"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gérer les stratégies de mise en application dans Microsoft Teams

En tant qu'administrateur, vous pouvez utiliser des stratégies de configuration d'application pour effectuer les tâches suivantes :

- Personnaliser Teams afin de mettre en évidence les applications les plus importantes pour vos utilisateurs. Vous choisissez les applications à épingler et définissez l'ordre dans celui-là. L'épinglage d'applications vous permet de présenter les applications dont les utilisateurs de votre organisation ont besoin, y compris les applications conçues par des tiers ou par des développeurs de votre organisation.
- Déterminer si les utilisateurs peuvent épingler des applications à Teams.
- Installer des applications pour le compte des utilisateurs. Vous choisissez les applications installées par défaut pour les utilisateurs lorsqu'ils démarrent Teams. Gardez à l'esprit que les [](teams-app-permission-policies.md) utilisateurs peuvent toujours installer les applications elles-mêmes si la stratégie d'autorisation d'application qui leur est attribuée le permet.

> [!Note]
> Pour les applications installées par les administrateurs, les utilisateurs ne peuvent pas les désinstaller.

Les applications sont épinglées à la barre de l'application, qui est la barre sur le côté du client de bureau Teams et en bas des clients mobiles Teams (iOS et Android).

|Client de bureau Teams  |Client mobile Teams |
|---------|---------|
|![Client de bureau Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Client mobile Teams](media/mobile-app-ui.png)      |

Pour voir les applications installées par les administrateurs, dans la barre d'application, les utilisateurs **sélectionnent... Plus d'applications** dans les clients de bureau et Web Teams et balayez vers le haut dans les clients mobiles.

Vous gérez les stratégies de configuration d'application dans le Centre d'administration Microsoft Teams. Utilisez la stratégie globale (à l'échelle de l'organisation par défaut) ou créez et attribuez des stratégies personnalisées.  Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

Vous devez modifier les paramètres de la stratégie globale pour inclure les applications que vous souhaitez. Pour personnaliser Teams pour différents groupes d'utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies personnalisées.

![Page Stratégies de configuration des applications](media/app-setup-policies.png)

> [!NOTE]
> Si vous disposez de Teams pour l'Éducation, il est important de savoir que l'application Devoirs est épinglée par défaut dans la stratégie globale, même si actuellement elle n'est pas répertoriée dans la stratégie globale. Il s'agit de la quatrième application dans la liste des applications épinglées sur les clients Teams.

## <a name="create-a-custom-app-setup-policy"></a>Créer une stratégie de configuration d'application personnalisée

Vous pouvez utiliser le Centre d'administration Microsoft Teams pour créer une stratégie personnalisée.

1. Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, voir Stratégies **d'installation des**  >  **applications** Teams.

2. Sélectionnez **Ajouter**.

   ![Page Ajouter des stratégies de configuration d'application](media/app-setup-policies-add.png)

3. Entrez un nom pour votre stratégie, ainsi qu’une description.

4. Activer ou désactiver **l'application personnalisée** Télécharger, selon que vous souhaitez ou non que les utilisateurs téléchargent des applications personnalisées dans Teams. Vous ne pouvez pas modifier ce paramètre **si** l'application autoriser des applications tierces est désactivée dans les paramètres de l'application à l'échelle [de l'organisation.](manage-apps.md#manage-org-wide-app-settings)

5. Activer ou désactiver l'épinglage d'utilisateurs, selon que vous voulez ou non permettre aux utilisateurs de personnaliser leur barre d'application en épinglage d'applications.

   > [!NOTE]
   > Le  paramètre Autoriser l'épinglage d'utilisateur est disponible dans le Centre d'administration Teams dans les environnements Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High et DoD), mais il n'a actuellement aucun effet.

6. Pour installer des applications pour les utilisateurs, effectuer les tâches suivantes :

    1. Sous **Applications installées,** **sélectionnez Ajouter des applications.**

    2. Dans le **volet Ajouter des applications installées,** recherchez les applications que vous voulez installer automatiquement pour les utilisateurs lorsqu'ils démarrent Teams. Vous pouvez également filtrer les applications par stratégie d'autorisation d'application. Une fois que vous avez choisi votre liste d'applications, sélectionnez **Ajouter.**

       ![Volet Ajouter des applications installées](media/app-setup-policies-add-installed-apps.png)

7. Pour épingler des applications, vous pouvez suivre les étapes suivantes :

    1. Sous **Applications épinglées,** **sélectionnez Ajouter des applications.**

    2. Dans le **volet Ajouter des applications épinglées,** recherchez les applications que vous voulez ajouter, puis sélectionnez **Ajouter.** Vous pouvez également filtrer les applications par stratégie d'autorisation d'application. Lorsque vous avez choisi votre liste d'applications à épingler, sélectionnez **Ajouter.**

       ![Volet Ajouter des applications épinglées](media/app-setup-policies-add-apps.png)

    3. Organisez les applications dans l'ordre dans qui vous voulez qu'elles apparaissent dans Teams, puis sélectionnez **Enregistrer.**

       ![Section Applications épinglées](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Modifier une stratégie de configuration d'application

Vous pouvez utiliser le Centre d'administration Microsoft Teams pour modifier une stratégie, notamment la stratégie globale (à l'échelle de l'organisation par défaut) et les stratégies personnalisées que vous créez.

1. Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, voir Stratégies **d'installation des**  >  **applications** Teams.

2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.

3. À partir de là, apportez les modifications souhaitées.

4. Sélectionnez **Enregistrer**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Affecter une stratégie de configuration d'application personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>Fonctionnement des stratégies de configuration d'application

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quelles stratégies de configuration d'application intégrées sont incluses dans le Centre d'administration Microsoft Teams

- **Global (par défaut à l'échelle** de l'organisation) : cette stratégie par défaut s'applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie. Modifiez la stratégie globale pour épingler les applications les plus importantes pour vos utilisateurs.

- **FrontlineWorker**: cette stratégie s'agit pour les employés en ligne. Vous pouvez l'affecter à des employés en ligne de votre organisation. Il est important de savoir que, comme les stratégies personnalisées que vous créez, vous devez affecter la stratégie aux utilisateurs pour que les paramètres soient actifs. Pour plus d'informations, voir la section Affecter une stratégie de configuration d'application personnalisée aux [utilisateurs](#assign-a-custom-app-setup-policy-to-users) de cet article.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas trouver une application dans le volet Ajouter des applications épinglées ?

Toutes les applications ne peuvent pas être épinglées à Teams via une stratégie de configuration d'application. Certaines applications peuvent ne pas prendre en charge cette fonctionnalité. Pour rechercher des applications qui peuvent être épinglées, recherchez l'application dans le volet Ajouter des applications épinglées.  Les onglets qui ont une étendue personnelle (onglets statiques) et bots peuvent être  épinglés au client de bureau Teams. Ces applications sont disponibles dans le volet Ajouter des applications épinglées.

N'oubliez pas que le magasin d'applications Teams répertorie toutes les applications Teams. Le **volet Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées à Teams via une stratégie.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Je suis administrateur de Teams pour l'éducation. Que dois-je savoir sur les stratégies de configuration d'application dans Teams pour l'Éducation ?

L'application Appel n'est pas disponible dans Teams pour l'éducation. Lorsque vous créez une stratégie de configuration d'application personnalisée, l'application Appels s'affiche dans la liste des applications. Toutefois, l'application n'est pas épinglée aux clients Teams et les utilisateurs de Teams pour l'Éducation ne voient pas l'application Appels dans Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Combien d'applications épinglées peuvent être ajoutées à une stratégie

Au moins deux applications doivent être épinglées aux clients mobiles Teams (iOS et Android). Si une stratégie possède moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continueront à utiliser la configuration existante.

Le nombre d'applications épinglées que vous pouvez ajouter à une stratégie n'est pas limité.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Combien de temps faut-il pour que les modifications de stratégie prennent effet

Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Comment les utilisateurs peuvent-ils voir toutes leurs applications épinglées dans Teams ?

Pour afficher toutes les applications épinglées pour un utilisateur, les utilisateurs doivent peut-être faire les choses suivantes en fonction du nombre d'applications installées et de la taille de la fenêtre de leur client Teams.

|Client de bureau Teams |Client mobile Teams |
|---------|---------|
|Dans la barre de l'application sur le côté de Teams, sélectionnez **... Autres applications.**| Dans la barre de l'application en bas de Teams, balayez vers le haut.|
|![Plus d'applications dans le client de bureau Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![plus d'applications dans le client mobile Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Que dois-je savoir sur l'expérience mobile dans Teams ?

Les clients mobiles Teams (iOS et Android) ne peuvent actuellement pas prise en charge les applications personnelles avec les onglets statiques. Selon les applications définies dans la stratégie, les applications épinglées au client de bureau Teams peuvent ne pas apparaître dans les clients mobiles Teams. Les robots personnels apparaissent toujours dans Conversation sur les clients mobiles.

Avec les clients mobiles Teams, les utilisateurs voient les principales applications Teams telles que Activité, Conversation et Teams, et vous pouvez épingler certaines applications tierces de Microsoft, telles que Shifts.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Les utilisateurs peuvent-ils modifier l'ordre des applications épinglées via une stratégie ?

Les utilisateurs peuvent modifier l'ordre de leurs applications épinglées sur les clients de bureau et mobiles Teams si l'option Autoriser **l'épinglage** utilisateur est désactivée. Les utilisateurs ne peuvent pas modifier l'ordre de leurs applications épinglées sur les clients web Teams.

#### <a name="does-user-pinning-take-precedence"></a>L'épinglage des utilisateurs a-t-il la priorité ?

Les épingles administrateur sont toujours prioritaire. Si **l'option Autoriser l'épinglage** d'utilisateur est désactivée, les utilisateurs conservent leurs applications épinglées sous les applications épinglées par l'administrateur. Si **l'option** Autoriser l'épinglage d'utilisateur est désactivée, les utilisateurs perdent leurs épingles existantes et seules les applications épinglées par l'administrateur sont présentes dans la barre d'application.

### <a name="custom-teams-apps"></a>Applications Teams personnalisées

Mon organisation a créé une application Teams personnalisée et l'a publiée sur AppSource ou le catalogue des applications client, mais l'icône d'application ne s'affiche pas comme prévu lorsque l'application est épinglée à la barre d'application dans Teams. Comment puis-je résoudre le problème ?

Veillez à respecter les instructions relatives au logo avant de soumettre l'application. Pour en savoir plus, consultez [la liste de contrôle de l'envoi du tableau de bord du vendeur.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>Sujets associés

[Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)
