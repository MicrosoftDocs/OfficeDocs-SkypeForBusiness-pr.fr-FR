---
title: Utilisez l’Assistant Intégration des employés en avant-première pour rendre votre personnel en avant-première opérationnel
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant d’intégration des employés en ligne pour déployer rapidement une expérience de Teams adaptée aux employés et responsables en ligne de votre organisation.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97f8994ecc5c7aef610e040f30b43803f03c6844
ms.sourcegitcommit: efea3b3b9dceb1a1d82eb7a09a5104dcd6df8abf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61993190"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Utilisez l’Assistant Intégration des employés en avant-première pour rendre votre personnel en avant-première opérationnel

## <a name="overview"></a>Présentation

L’Assistant d’intégration des employés en ligne Centre d'administration Microsoft 365 l’intégration des employés en avant-première à votre organisation. L’Assistant vous permet de déployer rapidement une expérience de Microsoft Teams adaptée à votre personnel en première ligne. L’Assistant vous permet de lancer facilement votre déploiement pilote d’Teams pour les employés en ligne de votre organisation.

L’Assistant met en place une équipe pour vos employés en ligne et attribue des licences et [des packages](manage-policy-packages.md) de stratégie à chaque membre de l’équipe. Vous pouvez créer votre équipe [](get-started-with-teams-templates-in-the-admin-console.md)de toutes pièces ou à partir d’un modèle d’équipe, puis ajouter des utilisateurs et attribuer des rôles. Le rôle détermine le package de stratégie que l’Assistant affecte à chaque utilisateur.

Actuellement, l’Assistant prend en charge l’ajout de 100 utilisateurs à chaque fois que vous l’exécutez. Nous travaillons prochainement à l’augmentation du nombre d’utilisateurs par run. Consultez à nouveau cette liste pour obtenir les dernières mises à jour.

L’Assistant est disponible pour toutes les organisations qui ont au moins une [licence F.](https://www.microsoft.com/microsoft-365/enterprise/frontline) Vous pouvez exécuter l’Assistant autant de fois que nécessaire pour déployer Teams employés en avant-première dans différents emplacements ou sites de votre organisation.

Regardez cette courte vidéo pour avoir un aperçu de la façon d’exécuter l’Assistant pour intégrer votre personnel en ligne.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> Cet Assistant vous permet d’intégrer rapidement votre personnel en avant-première Teams les employés de Centre d'administration Microsoft 365. Pour plus d’informations sur la manière dont vous Teams employés de première ligne à l’aide de scripts, voir Comment mettre en service des Teams à l’échelle des employés [en](flw-scripted-deployment.md)première ligne.

> [!NOTE]
> L’Assistant ne prend pas encore en charge [les étiquettes de](sensitivity-labels.md) sensibilité. Si votre organisation a besoin d’étiquettes de sensibilité pour créer une équipe, l’Assistant n’est pas Centre d'administration Microsoft 365.

## <a name="run-the-wizard"></a>Exécuter l’Assistant

1. Dans le navigation gauche du [Centre d'administration Microsoft 365,](https://admin.microsoft.com/)sélectionnez **Configuration.** Allez à la section **Applications et courrier,** puis, sous Obtenir votre personnel en **avant-première** opérationnel, sélectionnez **Afficher.** Ici, vous pouvez en savoir plus sur les fonctionnalités qui s’offrent Microsoft 365 en avant-première pour les employés en ligne.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Capture d’écran de la page de détails sur l’intégration des travailleurs en avant-première dans le Centre d'administration Microsoft 365" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. Lorsque vous êtes prêt, sélectionnez Commencer **à** exécuter l’Assistant.

3. Entrez le nom de votre équipe, ajoutez un ou plusieurs propriétaires d’équipe et sélectionnez un paramètre de confidentialité. Ensuite, choisissez si vous souhaitez créer votre équipe de toutes pièces ou à partir d’un modèle d’équipe. Les modèles d’équipe sont disponibles avec des onglets et des canaux prédéfinés, qui optimisent l’équipe pour des besoins ou projets spécifiques à l’entreprise.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Capture d’écran de la page Configurer une équipe de l’Assistant" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. Ajoutez des utilisateurs à l’équipe. Vous pouvez également ajouter des groupes. Si vous ajoutez des groupes, n’oubliez pas que les licences et packages de stratégie sont directement attribués à chaque utilisateur du groupe, et non au groupe proprement dit.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Capture d’écran de la page Ajouter des utilisateurs de l’Assistant dans laquelle vous ajoutez des utilisateurs et des groupes à votre équipe" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. Attribuez l’un des rôles suivants à chaque membre de l’équipe : Collègue en ligne, Responsable en ligne en ligne, Personne. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Capture d’écran de la page Attribuer des rôles de poste de l’Assistant dans laquelle vous attribuez des rôles, des emplacements et des licences aux membres de l’équipe" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    En attribuant un rôle de collègue en avant-première ou de gestionnaire en ligne, cet utilisateur recevra un package de stratégie. Le package de stratégie crée une expérience Teams adaptée à leur rôle. Cette expérience inclut des applications et stratégies pré-épinglées pour communiquer et collaborer avec les employés en contact direct avec les responsables.

    Ensuite, sélectionnez un emplacement et attribuez une licence Microsoft 365 F à chaque membre de l’équipe. Si vous n’avez pas assez de licences, vous pouvez sélectionner Acheter plus de **licences** pour acheter d’autres licences.  

6. Choisissez qui reçoit l’e-mail de statut une fois l’Assistant terminé. Le message contient des informations sur les actions de réussite et d’échec effectuées par l’Assistant lors de la création de l’équipe, de l’ajout de membres de l’équipe et de l’attribution d’une licence et d’un package de stratégie à chaque membre de &mdash; l’équipe. Utilisez ces informations pour résoudre les erreurs qui peuvent se produire.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Capture d’écran de la page Ajouter des destinataires du message d’état de l’Assistant" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. Examinez vos sélections, puis sélectionnez **Confirmer.**

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Capture d’écran de la page De révision de l’équipe de l’Assistant dans laquelle vous examinez les paramètres de votre équipe" lightbox="media/flw-onboarding-wizard-review-team.png":::

    L’Assistant crée votre équipe et attribue des licences et packages de stratégies aux membres de l’équipe. L’envoi de cette liste peut prendre quelques minutes, après quoi les destinataires que vous avez choisis reçoivent un message d’état.

8. Vous êtes en route, mais ce n’est pas encore fait ! Consultez ensuite la section Que faire après avoir [exécutez la](#what-to-do-after-running-the-wizard) section Assistant de cet article.

## <a name="what-to-do-after-running-the-wizard"></a>Que faire après avoir exécutez l’Assistant

Après avoir exécuté l’Assistant, il est important de :

- Faites savoir à vos employés et responsables en ligne qu’ils ne Teams licences.
- Si vous utilisez des appareils partagés, assurez-vous Teams’installer sur ces appareils. Si votre organisation utilise un modèle « apportez votre propre appareil », indiquez à vos employés et responsables qu’ils doivent télécharger et installer des Teams sur leurs appareils.

Lorsque l’employé en première ligne ouvre Teams pour la première fois, il recevra une expérience de première exécuter personnalisée, qui comprend des conversations, des canaux, des appels et une gestion des tâches au sein Teams.

## <a name="related-articles"></a>Articles connexes

- [Gérer les packages de stratégie dans Teams](manage-policy-packages.md)
- [Utiliser des modèles d’équipe dans le Centre Teams’administration](get-started-with-teams-templates-in-the-admin-console.md)
