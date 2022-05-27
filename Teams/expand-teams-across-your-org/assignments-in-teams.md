---
title: Affectations pour Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Découvrez comment gérer les affectations dans le centre d’administration Microsoft Teams dans Teams pour l'éducation.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed8b01b683d201bc26dec3d220c94fbc12e76f1c
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674666"
---
# <a name="assignments-in-teams-for-education"></a>Devoirs dans Teams pour l’éducation

Les fonctionnalités Devoirs et notes de Teams pour l'éducation permettent aux enseignants d’attribuer des tâches, du travail ou des questionnaires à leurs étudiants. Les enseignants peuvent gérer les chronologies des affectations, les instructions, ajouter des ressources à remettre, évaluer avec des rubriques, etc. Ils peuvent également suivre la progression des cours et des étudiants individuels sous l’onglet Notes.

[En savoir plus sur les devoirs et les notes dans Teams pour l'éducation](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Pour plus d’informations sur Teams affectations sur différentes plateformes, consultez [Teams fonctionnalités par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Intégrations d’affectations dans le centre d’administration Microsoft Teams

À l’aide des paramètres d’administration du centre d’administration Microsoft Teams, vous pouvez activer ou désactiver les fonctionnalités pour les enseignants au sein de votre organisation et leurs étudiants. Voici les paramètres liés aux affectations :

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Synthèse hebdomadaire des e-mails du tuteur

Les e-mails des tuteurs sont envoyés chaque week-end aux parents ou aux tuteurs. L’e-mail contient des informations sur les affectations de la semaine précédente et pour la semaine à venir. La synchronisation Parent et Guardian peut être configurée à l’aide [de Synchronisation des données scolaires](/schooldatasync/parent-contact-sync).

1. Importez les informations de contact parent via Parent et Guardian Sync dans SDS. Pour obtenir des instructions sur l’activation de la synchronisation parent et guardian, consultez [l’activation de la synchronisation parent et guardian](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Activez le paramètre Guardian dans le centre d’administration Microsoft Teams, car le paramètre est désactivé par défaut. Cela permettra aux enseignants d’envoyer un résumé hebdomadaire.

   > [!NOTE]
   > Les enseignants peuvent refuser le résumé en désélectionnant le paramètre au sein de leur propre équipe de classe personnelle (**affectation Paramètres > e-mails parent/guardian**).

Pour vérifier que les parents recevront l’e-mail, les trois éléments suivants doivent être vrais :

- Adresse e-mail jointe au profil d’étudiant dans SDS et marquée en tant que _parent_ ou _tuteur_. Pour plus d’informations, consultez [le format de fichier de synchronisation parent et guardian](/schooldatasync/parent-contact-sync-file-format).

- Les étudiants appartiennent à au moins une classe dans laquelle le courrier électronique n’est pas désactivé par l’enseignant dans [les paramètres d’affectation](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- Les e-mails contiennent des informations sur les affectations dont la date d’échéance est la semaine précédente ou la semaine à venir.

Le paramètre par défaut de cette fonctionnalité est **: Désactivé**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode est une plateforme de codage basée sur des blocs qui donne vie à l’informatique pour tous les étudiants.

MakeCode est un produit Microsoft qui est soumis aux [conditions d’utilisation](https://go.microsoft.com/fwlink/?LinkID=206977) et aux politiques de [confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839) de Microsoft.

Le paramètre par défaut de cette fonctionnalité est **: Désactivé**.

Pour activer les affectations MakeCode dans Teams, accédez au **centre Teams Administration**, accédez à la section **Affectations** et activez l’option de bascule MakeCode **.** Sélectionnez **Enregistrer**. Prévoyez quelques heures pour que ces paramètres prennent effet.

Pour plus d’informations sur le fonctionnement de cette fonctionnalité, regardez cette [démonstration vidéo](https://makecode.com/blog/teams/teams-assignments).

[En savoir plus sur MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) est un service d’intégrité académique. Il s’agit d’un service tiers qui est soumis à ses propres conditions générales et à sa politique de confidentialité. Vous êtes responsable de l’utilisation de tous les produits et services tiers.

Le paramètre par défaut de cette fonctionnalité est **: Désactivé**.

Pour activer Turnitin pour votre organisation, vous avez besoin d’un abonnement Turnitin. Vous pouvez ensuite entrer les informations suivantes, qui se trouvent dans votre console d’administration Turnitin :

- **TurnitinApiKey** : il s’agit d’un GUID de 32 caractères trouvé dans la console d’administration sous Integrations.
- **TurnitinApiUrl** : il s’agit de l’URL HTTPS de votre console d’administration Turnitin.

Voici quelques instructions pour vous aider à obtenir ces informations.

**TurnitinApiUrl** est l’adresse hôte de votre console d’administration.
Exemple : `https://your-tenant-name.turnitin.com`

La console d’administration vous permet de créer une intégration et une clé API associée à l’intégration.

Sélectionnez **Intégrations** dans le menu latéral, puis **sélectionnez Ajouter une intégration** et donnez un nom à l’intégration.

![Capture d’écran montrant l’ajout d’une nouvelle intégration.](./educationImages/Assignments_mopo_turnitin2.png)

**TurnitinApiKey** vous sera remis après avoir suivi les invites.
Copiez la clé API et collez-la dans le centre d’administration Microsoft Teams.  Il s’agit de la seule fois où vous pouvez afficher la clé.

![Capture d’écran montrant la copie de la clé API.](./educationImages/Assignments_mopo_turnitin3.png)

En cliquant sur le bouton **Enregistrer** dans le centre d’administration pour ce paramètre, autorisez quelques heures pour que ces paramètres prennent effet.

## <a name="assignments-data"></a>Données d’affectations

Les devoirs stockent les informations générées à la fois par les enseignants et les étudiants. Toutes les données sont partagées entre l’enseignant et l’étudiant spécifique pour lequel les informations sont destinées en classe. Il existe deux magasins de ces données, SharePoint et en dehors de SharePoint.

>[!NOTE]
>Les mêmes règles s’appliquent également aux intégrations internes telles que Reading Progress.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Données d’affectation dans SharePoint bibliothèques de documents

Les fichiers des étudiants associés à une soumission pour devoir sont stockés dans une bibliothèque de documents (nommée : *Travail étudiant*). Les fichiers associés aux devoirs créés par les enseignants et accessibles par les étudiants sont stockés dans une autre bibliothèque de documents (nommée : *Class Files*) dans le site SharePoint de l’équipe de classe correspondant. Les intégrations internes peuvent également stocker des données d’affectation dans le même site SharePoint d’équipe de classes correspondant (nommé : *Titre des affectations + horodatage*).

#### <a name="files-associated-with-the-student"></a>Fichiers associés à l’étudiant

Les administrateurs informatiques peuvent utiliser l’outil De recherche de contenu pour rechercher des fichiers étudiants (*travail des* étudiants, *fichiers de classe* ou autres fichiers d’intégration tiers) liés aux soumissions d’affectations et aux fichiers liés aux devoirs. Par exemple, un administrateur peut rechercher tous les sites SharePoint de l’organisation et utiliser le nom de l’étudiant et le nom de classe ou d’affectation dans la requête de recherche pour rechercher des données pertinentes pour une demande de sujet de données (DSR).

#### <a name="files-associated-with-the-teacher"></a>Fichiers associés à l’enseignant

Les administrateurs informatiques peuvent utiliser l’outil De recherche de contenu pour rechercher des fichiers d’enseignants (*travail étudiant*, *fichiers de classe* ou autres fichiers d’intégration internes) qui sont liés aux devoirs et aux fichiers distribués aux étudiants par les enseignants d’une classe sur les devoirs. Par exemple, un administrateur peut rechercher tous les sites SharePoint de l’organisation et utiliser le nom de l’enseignant et le nom de classe ou d’affectation dans la requête de recherche pour rechercher des données pertinentes pour une DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Affectations de données en dehors des bibliothèques de documents SharePoint

Certaines données relatives aux affectations ne sont pas stockées dans l’équipe de classe SharePoint site, ce qui signifie qu’elles ne sont pas détectables avec la recherche de contenu. Cela inclut :

- Notes des étudiants et commentaires de l’enseignant
- Liste des documents soumis pour un devoir par chaque étudiant
- Détails de l’affectation, tels que la date d’échéance, etc.
- Données d’intégration internes telles que les passages de progression de lecture ou les données de prononciation des étudiants

Pour ce type de données, un administrateur informatique ou un propriétaire de données, tel qu’un enseignant, peut être amené à entrer dans l’affectation dans l’équipe de classe pour rechercher des données pertinentes pour une DSR. L’administrateur peut s’ajouter en tant que propriétaire à la classe et afficher toutes les affectations de cette équipe de classe.

>[!NOTE]
>Si un étudiant ne fait plus partie de la classe, ses données peuvent toujours être présentes dans la classe comme *n’étant plus inscrites*. L’étudiant devra fournir à l’administrateur client la liste de ces classes dont il faisait partie.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Exporter en bloc les données d’affectation en dehors des bibliothèques de documents SharePoint

#### <a name="for-a-student"></a>Pour un étudiant

Pour exporter en bloc les données d’un seul étudiant, avant de supprimer l’étudiant des classes dont il fait partie, [exécutez le script](/microsoft-365/education/deploy/configure-assignments-for-teams) et fournissez le ``userId``. Si l’étudiant a été supprimé du site, soit l’administrateur peut l’ajouter à la classe avant d’exécuter le script, soit l’administrateur peut fournir le ``userId`` et le ``classId`` dont l’étudiant faisait partie.

Les données relatives aux soumissions des étudiants seront exportées.

#### <a name="for-a-teacher"></a>Pour un enseignant

Les données d’affectation d’exportation en bloc fonctionnent de la même façon pour un étudiant, mais toutes les soumissions auxquelles l’enseignant a accès seront exportées.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Supprimer en bloc les données d’affectation en dehors des bibliothèques de documents SharePoint

#### <a name="for-a-student"></a>Pour un étudiant

Pour supprimer en bloc les données d’un seul étudiant, avant de supprimer l’étudiant des classes dont il fait partie, [exécutez le script](/microsoft-365/education/deploy/configure-assignments-for-teams) et fournissez le ``userId``. Si l’étudiant a été supprimé du site, soit l’administrateur peut l’ajouter à la classe avant d’exécuter le script, soit l’administrateur peut fournir le ``userId`` et le ``classId`` dont l’étudiant faisait partie.

La fourniture d’une ``ClassId`` autorisation permet à l’administrateur de supprimer uniquement des informations sur l’étudiant d’une classe spécifique.

#### <a name="for-a-teacher"></a>Pour un enseignant

Étant donné que les données d’une affectation pour un enseignant sont partagées dans la classe, il n’existe aucune option de suppression en bloc. Au lieu de cela, l’administrateur peut s’ajouter à la classe, accéder à l’application et supprimer l’affectation.

Pour plus d’informations, consultez [Configurer les affectations pour Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Suppression des devoirs et des notes

Vous pouvez également utiliser Teams stratégies pour supprimer les affectations et les notes pour un utilisateur spécifique ou pour l’ensemble de votre locataire.

Pour supprimer les affectations et les notes pour un utilisateur individuel, accédez à **Teams Administration Center** et accédez à **Teams applications > stratégies d’autorisation** pour créer une définition de stratégie d’autorisation d’application.  Lors de la création de la nouvelle définition de stratégie, définissez la stratégie **d’applications Microsoft** sur _Bloquer des applications spécifiques, autorisez toutes les autres_ et ajoutez **affectations** à la liste des applications bloquées. Une fois votre nouvelle définition de stratégie enregistrée, affectez-la aux utilisateurs appropriés.

Pour supprimer les affectations et les notes pour l’ensemble de votre locataire, accédez à **Teams Administration Center**, accédez à **Teams applications > Gérer les applications**, puis recherchez et sélectionnez **Affectations** dans la liste des applications. Remplacez le paramètre d’état de la page Paramètres de l’application Affectation par _Bloqué_.

## <a name="assignments-diagnostic-tool-for-users"></a>Outil de diagnostic des affectations pour les utilisateurs

Support Microsoft a créé un outil permettant de collecter des données de diagnostic pour l’équipe d’ingénierie Microsoft afin d’examiner les problèmes liés à la fonctionnalité Affectations.

Cet outil est accessible à l’intérieur des affectations sur n’importe quel écran où les utilisateurs rencontrent un problème.

Pour extraire l’outil de diagnostic dans Teams, les utilisateurs peuvent :

- **Sur le bureau et sur le web :**
  - Sélectionnez Ctrl+/
- **Sur les appareils mobiles :**
  - Appuyez sur l’écran avec deux doigts et faites pivoter les doigts de 45 degrés, ou
  - Appuyez sur l’écran avec trois doigts pendant 15 secondes

Une fois que l’outil de diagnostic s’affiche, les utilisateurs voient une liste de données qui peuvent être nécessaires par le support technique de Microsoft.

Les données extraites peuvent inclure :

- ID de groupe
- ID du locataire
- Session ID
- ID d’affectation
- ID de soumission
- ID de l’utilisateur

Ces données ne sont pas automatiquement envoyées à Microsoft. Les utilisateurs doivent copier et coller les données dans un agent de support Microsoft concernant un ticket de support.

Si un utilisateur extrait l’outil de diagnostic puis le ferme, aucune donnée n’est envoyée.

Lorsque les données sont envoyées à un agent de support Microsoft, elles sont gérées en tant que données de support dans le cadre des contrats de service Microsoft 365 de votre organisation.

Pour obtenir des instructions sur l’utilisation de cet outil de diagnostic que vous pouvez partager avec les enseignants et les étudiants, consultez [Obtenir des données de diagnostic pour résoudre les problèmes liés aux devoirs](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
