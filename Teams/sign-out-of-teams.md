---
title: Déconnexion de Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Découvrez comment vous déconnecter de Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fb1048f0db6166dbbcd7f43c317db2603b57dd7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750083"
---
# <a name="sign-out-of-microsoft-teams"></a>Déconnexion de Microsoft Teams

Nous recommandons aux utilisateurs de rester connectés à l’application Microsoft Teams pour continuer à recevoir des conversations, des appels entrants et d’autres activités. Nous comprenons que, parfois, les utilisateurs peuvent vouloir se déconnecter de l’application Teams pour plusieurs raisons :

- Ils n’ont plus besoin d’utiliser Teams pour la journée
- Ils veulent utiliser un autre compte
- Ils sont sur un appareil qu’ils partagent avec une autre personne

Pour ces raisons ou d’autres, Teams vous permet de vous déconnecter de l’application et de mettre fin à votre session.

## <a name="account-sharing-between-apps"></a>Partage de compte entre des applications

Les systèmes d’exploitation modernes autorisent le partage de comptes entre différentes applications sur un appareil. Cette conception d'authentification unique (SSO) permet aux utilisateurs d’utiliser plusieurs applications sur leur appareil sans exiger qu’ils se connectent à chaque application. Teams ne contrôle pas ce comportement, mais il profite de la commodité de cette conception pour l’expérience de l’utilisateur final.

L’authentification unique a un impact important sur la déconnexion. Lorsque les utilisateurs se déconnectent de Teams, les données associées à leur compte sont supprimées de l’application Teams, mais les autres applications de l’appareil peuvent continuer à avoir accès à leur compte. Cela signifie également que les utilisateurs ne seront peut-être pas invités à ressaisir leurs informations d’identification s’ils choisissent de se reconnecter à Teams avec le même compte.

## <a name="sign-out-of-teams-on-desktop"></a>Déconnexion de Teams sur un ordinateur de bureau

Pour vous déconnecter du client de bureau Teams ou à partir du navigateur, sélectionnez votre image de profil dans la partie supérieure de l’application, puis sélectionnez **Se déconnecter**.

Pour l’application de bureau, vous pouvez également cliquer avec le bouton droit sur l’icône de l’application dans la barre des tâches, puis sélectionner **Se déconnecter**.

Si vous avez ajouté plusieurs comptes, vous devrez vous déconnecter de chaque compte de manière individuelle. Une fois que vous êtes déconnecté des comptes dans Teams, vous devrez peut-être ressaisir vos informations d’identification lors du prochain lancement de l’application pour accéder à votre compte.

## <a name="sign-out-of-teams-on-mobile-devices"></a>Déconnexion de Teams sur les appareils mobiles

Sur un appareil mobile, vous pouvez vous déconnecter de Teams en accédant au menu, de sélectionner le menu **Plus**, puis **Se déconnecter**. Une fois déconnecté, vous devrez ressaisir vos informations d’identification lors de votre prochain lancement de l’application.

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>Connexion et déconnexion générale des employés de terrain

L’application Android Teams prend désormais en charge la connexion et la déconnexion générale pour offrir une expérience de connexion et de déconnexion aisée pour les employés de terrain. Les employés peuvent choisir un appareil dans le pool d’appareils partagés et effectuer une connexion unique pour la « rendre personnelle » pendant la durée de leur shift. À la fin de leur shift, ils doivent pouvoir effectuer une déconnexion globale de l’appareil. Cette opération permet de supprimer toutes les informations personnelles et professionnelles de l’appareil afin de pouvoir rétablir l’appareil sur le pool d’appareils. Pour obtenir cette fonctionnalité, l’appareil doit être en mode partagé. Pour plus d’informations sur la configuration d’un appareil partagé, voir [Comment utiliser un mode d’appareil partagé dans Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

## <a name="manual-cleanup"></a>Nettoyage manuel

Bien que ce soit rare, il est possible que Teams ne puisse pas être en mesure d’effectuer un nettoyage complet lors de la déconnexion. Selon les rapports d’utilisateur, les causes courantes incluent le verrouillage des fichiers par un service s’exécutant sur le système, mais il peut exister d’autres raisons en fonction des configurations ou des stratégies d’appareil de l’individu et des autorisations utilisateur appliquées à l’appareil.

L’une des manifestations les plus courantes de ce problème est que Teams essaye de sélectionner automatiquement un compte existant pour connecter l’utilisateur. Dans ce cas, l’utilisateur peut vouloir nettoyer manuellement le cache local de Teams. Pour plus d’informations, voir [Se connecter ou supprimer un compte dans Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US).

## <a name="related-topics"></a>Rubriques connexes

[Se connecter ou supprimer un compte dans Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)