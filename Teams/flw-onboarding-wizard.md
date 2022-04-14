---
title: Utilisez l’Assistant Intégration des employés de première ligne pour votre personnel de première ligne soit opérationnel
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant Intégration du Worker de première ligne pour déployer rapidement une expérience dans Teams adaptée aux employés et aux gestionnaires de première ligne de votre organisation.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac4db418927c34920614c65d6f94a400ff116a91
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703680"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Utilisez l’Assistant Intégration des employés de première ligne pour votre personnel de première ligne soit opérationnel

## <a name="overview"></a>Présentation

L’Assistant Intégration du Worker de première ligne dans le Centre d'administration Microsoft 365 simplifie l’intégration de workers de première ligne à votre organisation. L’Assistant vous permet de déployer rapidement une expérience dans Microsoft Teams adaptée à votre personnel de première ligne. À l’aide de l’Assistant, vous pouvez facilement lancer votre déploiement pilote de Teams pour les employés de première ligne de votre organisation.

L’Assistant configure une équipe pour vos employés de première ligne et attribue des licences et [des packages de stratégie](manage-policy-packages.md) à chaque membre de l’équipe. Vous pouvez créer votre équipe à partir de zéro ou à partir d’un [modèle d’équipe](get-started-with-teams-templates-in-the-admin-console.md), puis ajouter des utilisateurs et attribuer des rôles. Le rôle détermine le package de stratégie que l’Assistant affecte à chaque utilisateur.

Actuellement, l’Assistant prend en charge l’ajout de 100 utilisateurs chaque fois que vous l’exécutez. Nous travaillons sur l’augmentation prochaine du nombre d’utilisateurs par exécution. Revenez ici pour obtenir les dernières mises à jour.

L’Assistant est disponible pour toutes les organisations qui disposent d’au moins une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline). Vous pouvez exécuter l’Assistant autant de fois que vous avez besoin de déployer Teams à votre personnel de première ligne dans différents emplacements ou sites au sein de votre organisation.

Regardez cette courte vidéo pour obtenir une vue d’ensemble de l’exécution de l’Assistant pour intégrer votre personnel de première ligne.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> Cet Assistant vous permet d’intégrer rapidement votre personnel de première ligne pour Teams via le Centre d'administration Microsoft 365. Pour plus d’informations sur le déploiement de Teams sur votre personnel de première ligne à l’aide de scripts, consultez [Comment approvisionner des Teams à grande échelle pour les employés de première ligne](flw-scripted-deployment.md).

> [!NOTE]
> L’Assistant ne prend pas encore en charge [les étiquettes de confidentialité](sensitivity-labels.md) . Si votre organisation a besoin d’étiquettes de confidentialité pour créer une équipe, l’Assistant ne s’affiche pas dans le Centre d'administration Microsoft 365.

## <a name="run-the-wizard"></a>Exécuter l’Assistant

1. Dans le volet de navigation gauche de [l’Centre d'administration Microsoft 365](https://admin.microsoft.com/), choisissez **Configurer**. Accédez à la section **Applications et e-mail** , puis sous **Obtenir votre personnel de première ligne opérationnel**, sélectionnez **Affichage**. Ici, vous pouvez en savoir plus sur les fonctionnalités que Microsoft 365 for frontline workers offre.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Capture d’écran de la page de détails de l’expérience d’intégration de Frontline Worker dans le Centre d'administration Microsoft 365" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. Lorsque vous êtes prêt, sélectionnez **Démarrage** pour exécuter l’Assistant.

3. Entrez un nom pour votre équipe, ajoutez un ou plusieurs propriétaires d’équipe, puis sélectionnez un paramètre de confidentialité. Ensuite, choisissez de créer votre équipe à partir de zéro ou à partir d’un modèle d’équipe. Les modèles d’équipe sont fournis avec des canaux et des onglets prédéfinis, qui optimisent l’équipe pour un projet ou un besoin métier particulier.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Capture d’écran de la page Configurer une équipe de l’Assistant" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. Ajoutez des utilisateurs à l’équipe. Vous pouvez également ajouter des groupes. Si vous ajoutez des groupes, gardez à l’esprit que les licences et les packages de stratégie sont directement attribués à chaque utilisateur du groupe, et non au groupe lui-même.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Capture d’écran de la page Ajouter des utilisateurs de l’Assistant où vous ajoutez des utilisateurs et des groupes à votre équipe" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. Attribuez l’un des rôles suivants à chaque membre de l’équipe : Travail de première ligne, Gestionnaire de première ligne, Aucun. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Capture d’écran de la page Attribuer des rôles de travail de l’Assistant où vous attribuez des rôles, des emplacements et des licences aux membres de l’équipe" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    En attribuant un rôle De travail de première ligne ou Gestionnaire de première ligne, cet utilisateur reçoit un package de stratégie. Le package de stratégie crée une expérience dans Teams qui est adaptée à leur rôle. Cette expérience inclut des applications et des stratégies pré-épinglées pour une communication et une collaboration de travail et de gestionnaires de première ligne saines.

    Ensuite, sélectionnez un emplacement et attribuez une licence Microsoft 365 F à chaque membre de l’équipe. Si vous n’avez pas suffisamment de licences, vous pouvez sélectionner **Acheter plus de licences** pour acheter d’autres licences.  

6. Choisissez qui reçoit l’e-mail d’état une fois l’Assistant terminé. L’e-mail contient des informations sur la réussite et l’échec sur les actions effectuées par l’Assistant&mdash; lors de la création de l’équipe, de l’ajout de membres de l’équipe et de l’attribution d’une licence et d’un package de stratégie à chaque membre de l’équipe. Utilisez ces informations pour résoudre les erreurs susceptibles de se produire.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Capture d’écran de la page Ajouter des destinataires d’e-mail d’état de l’Assistant" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. Passez en revue vos sélections, puis sélectionnez **Confirmer**.

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Capture d’écran de la page Examiner l’équipe de l’Assistant où vous passez en revue les paramètres de votre équipe" lightbox="media/flw-onboarding-wizard-review-team.png":::

    L’Assistant crée votre équipe et affecte des licences et des packages de stratégie aux membres de l’équipe. L’exécution peut prendre quelques minutes, après quoi les destinataires que vous avez choisis reçoivent un e-mail d’état.

8. Vous êtes sur votre chemin, mais vous n’avez pas encore terminé! Ensuite, découvrez [ce qu’il faut faire après avoir exécuté la section Assistant](#what-to-do-after-running-the-wizard) de cet article.

## <a name="what-to-do-after-running-the-wizard"></a>Procédure à suivre après l’exécution de l’Assistant

Après avoir exécuté l’Assistant, il est important de :

- Informez vos employés et responsables de première ligne qu’ils se voient attribuer des licences Teams.
- Si votre organisation utilise des appareils partagés, assurez-vous que Teams est installé sur ces appareils. Les utilisateurs que vous avez ajoutés à l’équipe recevront un e-mail de bienvenue qui les invite à ouvrir Teams.
- Si votre organisation utilise un modèle BYOD (Apportez votre propre appareil), informez chaque utilisateur que vous avez ajouté à l’équipe qu’il doit télécharger et installer Teams sur ses appareils. Ils recevront également un e-mail de bienvenue qui les invite à télécharger Teams.

    > [!NOTE]
    > N’oubliez pas que les utilisateurs disposant de licences F1 ne recevront pas d’e-mail de bienvenue, car la licence F1 n’inclut pas l’accès aux e-mails.  

Lorsque l’employé de première ligne ouvre Teams pour la première fois, il reçoit une expérience de première exécution personnalisée, qui inclut les conversations et les canaux, les appels et la gestion des tâches dans Teams.

## <a name="related-articles"></a>Articles connexes

- [Gérer les packages de stratégie dans Teams](manage-policy-packages.md)
- [Utiliser des modèles d’équipe dans le centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
