---
title: Gérer l’application Approbations dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: how-to
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Découvrez comment gérer l’application Approbations pour votre organisation dans Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3cf50824119111d34668f4717eaf38f92de8bc64
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784329"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Gérer l’application Approbations dans Microsoft Teams

L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.
L’application Approbations offre un moyen simple d’apporter des audits, de la conformité, de la responsabilité et des flux de travail à des approbations structurées et non structurées dans Teams.

 ![affiche l’application approbations.](media/approvals-selection.png)

Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.

 ![affiche l’application approbations avec l’option épingler.](media/approvalApp-pin.png)

La première approbation créée à partir de l’application Approbations déclenche l’approvisionnement de la solution d’approbation dans l’environnement Microsoft Dataverse par défaut. Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement Microsoft Dataverse par défaut.

Cet article décrit la exigences et les rôles de l’application Approbations.

> [!NOTE]
> Cette fonctionnalité n’a pas encore été publiée pour les utilisateurs de Government Community Cloud High (GCCH) et du ministère de la Défense (DOD).

## <a name="required-permissions-and-licenses"></a>Autorisations et licences requises

Pour déployer l’application Approbations, vous avez besoin d’une autorisation pour les éléments suivants :

- Autorisations pour créer une base de données Microsoft Dataverse.

- Un compte sur [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)

- Rôle d’administrateur dans l’environnement cible.

- Licence pour [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.

- Une licence pour Microsoft Forms est requise pour permettre aux utilisateurs de configurer de nouveaux modèles d’approbation.

Pour utiliser l’application Approbations, vous avez besoin d’une licence pour Power Automate, et votre compte est automatiquement ajouté au rôle Utilisateur approbations dans l’environnement cible lors de votre première affectation d’approbation.

## <a name="storage-with-microsoft-dataverse"></a>Stockage avec Microsoft Dataverse

Le Modèle de données commun (CDM) est le langage de données partagé utilisé par les applications métier et analytiques dans Microsoft Dataverse. Il se compose d’un ensemble de schémas de données standardisés et extensibles publiés par Microsoft et nos partenaires qui permettent la cohérence des données et leur signification entre les applications et les processus métier. En savoir plus sur [Modèle de données courant de Microsoft Power Platform](/power-automate/get-started-approvals).

En savoir plus sur le [flux d’approbation](/power-automate/modern-approvals).

Les approbations créées à partir d’un modèle stockent toujours des données dans Microsoft Dataverse, telles que leur titre, leurs détails, leur ID de modèle, etc. Les réponses envoyées sur la demande d’approbation sont stockées dans formulaires. En savoir plus sur [le stockage de données pour Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Si vous supprimez le modèle de formulaire sur le site Microsoft Forms, votre modèle d’approbation est rompu et les utilisateurs ne peuvent pas démarrer la demande. Les utilisateurs obtiennent une erreur « CDB TableNotFound » lorsqu’ils tentent d’ouvrir un modèle d’approbation qui est supprimé sur Microsoft Forms.

Les modèles à l’échelle de l’organisation partagent la même durée de vie du locataire et les modèles d’étendue équipe partagent la même durée de vie de l’équipe. Ainsi, la suppression définitive de l’équipe supprime les modèles associés.

## <a name="approvals-teams-app-permissions"></a>Autorisations de l’application Autorisations Teams

L’application Approbations Teams vous permet d’accéder aux fonctionnalités suivantes :

- Recevoir les messages et les données que vous lui fournissez.

- Vous envoyer des messages et des notifications.

- Rendre les applications et les boîtes de dialogue personnelles sans en-tête fourni par Teams.

- Accéder à vos informations de profil telles que votre nom, adresse e-mail, nom de votre entreprise et la langue par défaut.

- Recevoir les messages et les données que les membres d’une équipe lui fournissent dans un canal.

- Envoyer des messages et des notifications dans un canal.

- Accédez aux informations de votre équipe :
  - nom de l'équipe
  - liste des canaux
  - liste de présence (noms et adresses de courrier des membres de l’équipe).

- Utilisez les informations de l'équipe pour les contacter.

Autorisations du modèle d’approbation

- Tous les propriétaires d’équipe peuvent créer un modèle d’approbation pour les équipes dont ils sont propriétaires.

- Lorsqu’un administrateur crée un modèle pour l’ensemble de son organisation pour la première fois, il crée automatiquement un groupe Azure Active Directory (AAD) pour tous les administrateurs du locataire, y compris les administrateurs de service global et Teams. Ces administrateurs sont ajoutés en tant que propriétaires du groupe, afin qu’ils puissent co-gérer les modèles d’organisation. Les administrateurs qui débutent dans l’organisation après la création de l’équipe doivent être ajoutés manuellement en tant que propriétaires de groupe afin qu’ils disposent des mêmes autorisations pour gérer les modèles à l’échelle de l’organisation.

> [!Note]
> Si un administrateur supprime le groupe, vous avez un mois pour le restaurer dans le portail Azure Active Directory (AAD) afin de restaurer toutes les données associées. Au bout d’un mois, ou si l’administrateur supprime ce groupe dans la Corbeille, vous perdrez toutes les données associées.

## <a name="disable-the-approvals-app"></a>Gérer l'application Approbations

L’application Approbations est disponible par défaut. Vous pouvez désactiver l’application dans le Centre d’administration Teams.

  1. Se connecter au Centre d’administration de Microsoft Teams.

  2. Allez à **Teams applications** > **AppsManage**.

  3. Recherchez l’application Approbations.

     ![affiche la navigation du centre Administration avec les applications Teams > Gérer les applications mises en évidence.](media/manage-approval-apps.png)

  4. Sélectionnez **Approbations**.

  5. Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.

     :::image type="content" alt-text="affiche les détails de l’application Approbations." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Épingler des approbations à Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>Utiliser l’expérience d’application de première ligne personnalisée pour épingler des approbations et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent approbations, talkie-walkie, tâches et shifts. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prête à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre de l’application(barre située sur le côté du client de bureau Teams et en bas des clients mobiles Teams), où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Personnaliser des applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>Utiliser une stratégie de configuration d’application pour épingler des approbations à Teams

Les stratégies de configuration des applications vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs.

Pour épingler l’application Approbations pour vos utilisateurs, vous pouvez modifier la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer une stratégie personnalisée dans la stratégie de configuration de l’application. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Stratégie de rétention

Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement Microsoft Dataverse par défaut, qui ne prend pas en charge les sauvegardes pour l’instant. En savoir plus sur la [Sauvegarde et restauration des environnements : Plateforme Power \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Les données stockées dans Forms ne seront pas supprimées tant que les propriétaires de l’équipe ne les nettoieront pas de l’onglet **Formulaires supprimés** dans l’application web Microsoft Forms.

## <a name="conditional-access-policies"></a>Stratégies d’accès conditionnel

Actuellement, l’application Approbations dans Teams ne prend pas en charge les stratégies d’accès conditionnel définies pour Microsoft Teams.

## <a name="data-limitations"></a>Limitations des données

Chaque équipe peut contenir au maximum 400 modèles d’approbation, et chaque modèle peut collecter un maximum de 50 000 demandes en fonction de la fonctionnalité actuelle dans Microsoft Forms.

## <a name="auditing"></a>Audit

L’application Approbations enregistre les événements d’audit dans le Centre de sécurité et conformité Microsoft 365. Vous pouvez afficher le journal d’audit.

1. Accédez au site de conformité Microsoft 365.

2. Sélectionnez la section **Audit**.

3. Recherchez des activités sous **Activités d’approbation de Microsoft Teams**.

Vous pouvez rechercher les activités suivantes :

- Créer une demande d’approbation

- Afficher les détails de la demande d’approbation

- Demande d’approbation approuvée

- Demande d’approbation rejetée

- Demande d’approbation annulée

- Demande d’approbation partagée

- Fichier joint à une demande d’approbation

- Demande d'approbation réaffectée

- Ajout d’une signature électronique à une demande d’approbation

- Afficher les détails de la demande de signature électronique

- Demande de signature électronique révisée

- Demande de signature électronique annulée

- Créer un modèle

- Modifier un modèle existant

- Activer/désactiver un modèle

- Modèle consulté

Pour accéder à davantage d’approbations d’audit dans Power Automate, activez et configurez l’audit dans l’environnement par défaut pour les entités d’approbation principales Approbation, Demande d’approbation et Réponse d’approbation. Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements d’approbation. En savoir plus sur [Audit des données et de l’activité des utilisateurs pour des raisons de sécurité et de conformité : Plateforme Power \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

L’audit peut être personnalisé davantage dans le [Centre de conformité et sécurité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Pour utiliser les rapports préconfigurés, connectez-vous à Conformité et sécurité Microsoft 365.

2. Sélectionnez **Recherche et enquête**.

3. Recherchez dans le journal d’audit et sélectionnez l’onglet **Activités Dynamics 365**.

En savoir plus sur [Journalisation des activités de Microsoft Dataverse et des applications pilotées par les modèles :Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sécurité

À partir de l’application Approbations Teams, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations envoyées et reçues. Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils répondent ou visualisent la demande.

>[!Note]
> Un utilisateur reçoit un rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal où l’approbation a été créée. Il ne peut pas agir sur la demande si ce rôle ne lui a pas été affecté lors de la création de l’approbation.

## <a name="approvals-e-signature-integration"></a>Intégration de la signature électronique des approbations

Pour utiliser la fonctionnalité de signature électronique d’application Approbations, vous avez besoin d’une licence pour le fournisseur de signature électronique spécifique que vous souhaitez utiliser. Pour obtenir une licence pour votre organisation, vous devez accéder au site du fournisseur.

### <a name="enable-or-disable-e-signature-providers"></a>Activer ou désactiver les fournisseurs de signature électronique

Vous pouvez utiliser le Centre d’administration Teams pour contrôler les fournisseurs de signatures électroniques tiers disponibles pour vos utilisateurs dans l’application Approbations. Par défaut, les fournisseurs de signatures électroniques sont activés dans l’application Approbations. Lorsque vous désactivez un fournisseur de signature électronique, vos utilisateurs n’ont pas accès à ce fournisseur lorsqu’ils créent des approbations. Vos utilisateurs ne pourront pas non plus afficher les demandes de signature électronique qui ont été créées à l’aide de ce fournisseur.

1. Dans le volet gauche du Centre d’administration Teams, accédez à **Applications** >  Teams **Gérer les applications**.
2. Recherchez l’application Approbations, puis sélectionnez-la.
3. Accédez à l’onglet **Paramètres** , puis effectuez une ou plusieurs des opérations suivantes :

    - Pour activer ou désactiver Adobe Sign, basculez sur **Activé** ou **Désactivé**.
    - Pour activer ou désactiver DocuSign, basculez le bouton bascule **sur Activé** ou **Désactivé**.
4. Sélectionnez **Envoyer**.

Les approbations de signature électronique créées à partir de l’application Approbations sont stockées dans l’environnement cloud du fournisseur sélectionné. Pour exporter des données sur les signatures électroniques, vous devez accéder au site du fournisseur. Pour plus d’informations sur le stockage, l’exportation et la rétention des contrats de signature électronique, consultez la documentation du fournisseur.
