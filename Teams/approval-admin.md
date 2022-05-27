---
title: Disponibilité des applications Approbations dans Teams
author: mkbond007
ms.author: mabond
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: En savoir plus sur la disponibilité des applications Approbations dans Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93b0a74feb2d9333d634b9a7858ff6136ca5b5ec
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676496"
---
# <a name="teams-approvals-app-availability"></a>Disponibilité de l’application Approbations Teams

L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.
L’application Approbations offre un moyen simple d’apporter des audits, de la conformité, de la responsabilité et des flux de travail à des approbations structurées et non structurées dans Teams.

 ![affiche l’application d’approbations.](media/approvals-selection.png)

Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.

 ![affiche l’application d’approbations avec l’option épingler.](media/approvalApp-pin.png)

La première approbation créée à partir de l’application Approbations déclenche l’approvisionnement de la solution d’approbation dans l’environnement Microsoft Dataverse par défaut. Approbations créé à partir de l’application Approbations est stocké dans l’environnement Microsoft Dataverse par défaut.

Cet article décrit la exigences et les rôles de l’application Approbations.

> [!NOTE]
> Cette fonctionnalité n’a pas encore été publiée pour les utilisateurs Cloud de la communauté du secteur public High (GCCH) et department of Defense (DOD).

## <a name="required-permissions-and-licenses"></a>Autorisations et licences requises

Pour déployer l’application Approbations, vous avez besoin d’une autorisation pour les éléments suivants :

- Autorisations pour créer une base de données Microsoft Dataverse.

- Un compte sur [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)

- Rôle d’administrateur dans l’environnement cible.

- Licence pour [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.

- Une licence pour Microsoft Forms est requise pour que les utilisateurs configurent de nouveaux modèles d’approbation.

Pour utiliser l’application Approbations, vous avez besoin d’une licence pour Power Automate et votre compte est automatiquement ajouté au rôle d’utilisateur Approbations dans l’environnement cible lors de votre première affectation d’approbation.

## <a name="storage-with-microsoft-dataverse"></a>Stockage avec Microsoft Dataverse

Common Data Model (CDM) est le langage de données partagé utilisé par les applications métier et analytiques dans Microsoft Dataverse. Il se compose d’un ensemble de schémas de données normalisés et extensibles publiés par Microsoft et nos partenaires, qui permet la cohérence des données et sa signification entre les applications et les processus métier. En savoir plus sur [Modèle de données courant de Microsoft Power Platform](/power-automate/get-started-approvals).

En savoir plus sur le [flux d’approbation](/power-automate/modern-approvals).

Approbations qui sont créées à partir d’un modèle stockent toujours des données dans Microsoft Dataverse, telles que leur titre, leurs détails, leur ID de modèle, etc. Les réponses envoyées lors de la demande d’approbation sont stockées dans les formulaires. En savoir plus sur le [stockage de données pour Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Si vous supprimez le modèle de formulaire sur le site Microsoft Forms, il interrompt votre modèle d’approbation et les utilisateurs ne peuvent pas démarrer la demande. Les utilisateurs reçoivent une erreur « CDB TableNotFound » lors de la tentative d’ouverture d’un modèle d’approbation supprimé le Microsoft Forms.

Les modèles d’organisation partagent la même durée de vie du locataire et les modèles d’équipe partagent la même durée de vie de l’équipe. Par conséquent, la suppression définitive de l’équipe supprime les modèles associés.

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

- Lorsqu’un administrateur crée un modèle pour l’ensemble de son organisation pour la première fois, il crée automatiquement un groupe Azure Active Directory (AAD) pour tous les administrateurs du locataire, y compris les administrateurs de service globaux et Teams. Ces administrateurs sont ajoutés en tant que propriétaires du groupe, afin qu’ils puissent co-gérer les modèles d’organisation. Les administrateurs qui débutent dans l’organisation après la création de l’équipe doivent être ajoutés manuellement en tant que propriétaires de groupe afin de disposer des mêmes autorisations pour gérer les modèles à l’échelle de l’organisation.

> [!Note]
> Si un administrateur supprime le groupe, vous avez un mois pour le restaurer dans le portail Azure Active Directory (AAD) pour restaurer toutes les données associées. Au bout d’un mois, ou si l’administrateur supprime ce groupe dans la corbeille, vous perdrez toutes les données associées.

## <a name="disable-the-approvals-app"></a>Gérer l'application Approbations

L’application Approbations est disponible par défaut. Vous pouvez désactiver l’application dans le Centre d’administration Teams.

  1. Se connecter au Centre d’administration de Microsoft Teams.

  2. Allez à **Teams applications** > **AppsManage**.

  3. Recherchez l’application Approbations.

     ![affiche la navigation au centre Administration avec Teams Apps > Manage Apps mis en surbrillance.](media/manage-approval-apps.png)

  4. Sélectionnez **Approbations**.

  5. Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.

     :::image type="content" alt-text="affiche les détails de l’application Approbations." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Épingler Approbations à Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>Utilisez l’expérience d’application de première ligne personnalisée pour épingler Approbations et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent Approbations, Walkie Talkie, Tasks et Shifts. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prêt à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre de l’application , la barre située sur le côté du client de bureau Teams et en bas de la Teams clients mobiles, où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Tailor Teams apps pour vos employés de première ligne](pin-teams-apps-based-on-license.md).

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>Utiliser une stratégie d’installation d’application pour épingler Approbations à Teams

Les stratégies d’installation d’application vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs dans vos utilisateurs.

Pour épingler l’application Approbations pour vos utilisateurs, vous pouvez modifier la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et affecter une stratégie d’installation d’application personnalisée. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Stratégie de rétention

Approbations créées à partir de l’application Approbations sont stockées dans l’environnement Microsoft Dataverse par défaut, qui ne prend pas en charge les sauvegardes pour l’instant. En savoir plus sur la [Sauvegarde et restauration des environnements : Plateforme Power \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Les données stockées dans forms ne seront pas supprimées tant que les propriétaires de l’équipe ne les auront pas nettoyées de l’onglet **Formulaires supprimés** de l’application web Microsoft Forms.

## <a name="conditional-access-policies"></a>Stratégies d’accès conditionnel

Actuellement, l’application Approbations dans Teams ne prend pas en charge les stratégies d’accès conditionnel définies pour Microsoft Teams.

## <a name="data-limitations"></a>Limitations des données

Chaque équipe peut contenir au plus 400 modèles d’approbation, et chaque modèle peut collecter un maximum de 50 000 demandes en fonction de la fonctionnalité actuelle dans Microsoft Forms.

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

- Demande de signature électronique examinée

- Demande de signature électronique annulée

- Créer un modèle

- Modifier un modèle existant

- Activer/désactiver un modèle

- Modèle affiché

Pour accéder à d’autres approbations d’audit dans Power Automate, activez et configurez l’audit dans l’environnement par défaut pour les entités d’approbation principales : approbation, demande d’approbation et réponse d’approbation. Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements d’approbation. En savoir plus sur [Audit des données et de l’activité des utilisateurs pour des raisons de sécurité et de conformité : Plateforme Power \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

L’audit peut être personnalisé davantage dans le [Centre de conformité et sécurité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Pour utiliser les rapports préconfigurés, connectez-vous à Conformité et sécurité Microsoft 365.

2. Sélectionnez **Recherche et enquête**.

3. Recherchez dans le journal d’audit et sélectionnez l’onglet **Activités Dynamics 365**.

En savoir plus sur [Journalisation des activités de Microsoft Dataverse et des applications pilotées par les modèles :Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sécurité

À partir de l’application Approbations Teams, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations envoyées et reçues. Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils répondent ou visualisent la demande.

> [!Note]
> Un utilisateur reçoit un rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal dans lequel l’approbation a été créée. Il ne peut pas agir sur la demande si ce rôle ne lui a pas été affecté lors de la création de l’approbation.

## <a name="approvals-e-signature-integration"></a>Approbations’intégration de signature électronique

Pour utiliser la fonctionnalité de signature électronique d’application Approbations, vous avez besoin d’une licence pour le fournisseur de signature électronique spécifique que vous souhaitez utiliser. Pour obtenir une licence pour votre organisation, vous devez accéder au site du fournisseur.

### <a name="enable-or-disable-e-signature-providers"></a>Activer ou désactiver les fournisseurs de signature électronique

Vous pouvez utiliser le centre d’administration Teams pour contrôler quels fournisseurs de signature électronique tiers sont disponibles pour vos utilisateurs dans l’application Approbations. Par défaut, les fournisseurs de signatures électroniques sont activés dans l’application Approbations. Lorsque vous désactivez un fournisseur de signature électronique, vos utilisateurs n’ont pas accès à ce fournisseur lorsqu’ils créent des approbations. Vos utilisateurs ne pourront pas non plus afficher les demandes de signature électronique qui ont été créées à l’aide de ce fournisseur.

1. Dans le volet gauche du centre d’administration Teams, accédez à **Teams applications** > **Gérer les applications**.
2. Recherchez l’application Approbations, puis sélectionnez-la.
3. Accédez à l’onglet **Paramètres**, puis effectuez une ou plusieurs des opérations suivantes :

    - Pour activer ou désactiver Adobe Sign, activez **ou** **désactivez** le bouton bascule.
    - Pour activer ou désactiver DocuSign, activez **ou** **désactivez** le bouton bascule.
4. Sélectionnez **Envoyer**.

Les approbations de signature électronique créées à partir de l’application Approbations sont stockées dans l’environnement cloud du fournisseur sélectionné. Pour exporter des données sur les signatures électroniques, vous devez accéder au site du fournisseur. Pour plus d’informations sur le stockage, l’exportation et la rétention des contrats de signature électronique, consultez la documentation du fournisseur.
