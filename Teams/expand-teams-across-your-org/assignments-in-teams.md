---
title: Affectations pour Teams
author: danieasmith
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
description: Découvrez comment gérer les devoirs dans le Centre d’administration Microsoft Teams dans Teams pour l'éducation.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59fb8e0b81195c696b7bd6142ecf031688207917
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909595"
---
# <a name="assignments-in-teams-for-education"></a>Devoirs dans Teams pour l’éducation

Les fonctionnalités Devoirs et Notes Teams pour l'éducation aux enseignants d’attribuer des tâches, du travail ou des questionnaires à leurs étudiants. Les enseignants peuvent gérer la chronologie des devoirs, les instructions, ajouter des ressources à rendre, ajouter des notes avec des rubriques, etc. Ils peuvent également suivre la progression de la classe et de l’étudiant individuel dans l’onglet Notes.

[En savoir plus sur les devoirs et les notes dans Teams pour l'éducation.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Pour plus d’informations sur Teams devoirs sur différentes plateformes, voir Teams [fonctionnalités par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Intégrations des devoirs dans le Centre Microsoft Teams’administration

En utilisant les paramètres d’administration du Microsoft Teams d’administration, vous pouvez activer ou désactiver des fonctionnalités pour les enseignants de votre organisation et leurs étudiants. Les paramètres suivants sont liés aux devoirs :

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>E-mail hebdomadaire des tuteurs

Les messages tuteurs sont envoyés chaque week-end à des parents ou tuteurs légaux. Le message électronique contient des informations sur les devoirs de la semaine précédente et de la semaine à venir. La synchronisation des parents et tuteurs peut être configurée à [l’aide de Synchronisation des données scolaires.](/schooldatasync/parent-contact-sync)

1. Importez les coordonnées des parents via la Synchronisation parent/tuteur dans SDS. Pour obtenir des instructions sur l’activation de la synchronisation des parents et tuteurs, voir Activer la synchronisation des [parents et tuteurs.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Activer le paramètre tuteur dans le Microsoft Teams d’administration, car ce paramètre est désactivé par défaut. Cela permettra aux enseignants d’envoyer une résumé hebdomadaire.

   > [!NOTE]
   > Les enseignants peuvent se désinsélectionner de la digestibilité en désélectionner le paramètre au sein de leur équipe de classe personnelle (Courriers électroniques du Paramètres >**parent/tuteur).**

Pour vérifier que les parents vont recevoir le message électronique, les trois éléments suivants doivent être vérifiés :

- Adresse e-mail jointe au profil d’étudiant dans SDS et marquée en tant que _parent_ ou _tuteur._ Pour plus d’informations, voir Format de fichier de synchronisation des parents et [tuteurs.](/schooldatasync/parent-contact-sync-file-format)

- Les étudiants appartiennent à au moins une classe dans laquelle le courrier électronique n’est pas désactivé par l’enseignant dans les [paramètres de devoir.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

- Les messages électroniques contiennent des informations sur les devoirs dont la date d’échéance est de la semaine précédente ou de la semaine à venir.

Le paramètre par défaut de cette fonctionnalité est - **Non.**

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode est une plateforme de codage en blocs qui donne vie à tous les étudiants en informatique.

MakeCode est un produit Microsoft qui est soumis aux conditions d’utilisation et aux politiques [de confidentialité de](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft. [](https://go.microsoft.com/fwlink/?LinkID=206977)

Le paramètre par défaut de cette fonctionnalité est - **Non.**

Pour activer les affectations MakeCode dans Teams, accédez au Centre d’administration **Teams,** accédez à la section  **Devoirs,** puis activez l’option bascule MakeCode. Cliquez sur **Enregistrer**. Laissez quelques heures à ces paramètres pour qu’ils prennent effet.

Pour plus d’informations sur le fonctionnement de cette fonctionnalité, regardez [cette vidéo de démonstration.](https://makecode.com/blog/teams/teams-assignments)

[En savoir plus sur MakeCode.](https://aka.ms/makecode)

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) est un service d’intégrité académique. Il s’agit d’un service tiers soumis à ses propres conditions et politique de confidentialité. Vous êtes responsable de l’utilisation des produits et services tiers.

Le paramètre par défaut pour cette fonctionnalité est - **Non.**

Pour activer Turnitin pour votre organisation, vous devez avoir un abonnement Turnitin. Vous pouvez ensuite entrer les informations suivantes, qui se trouvent dans votre console d’administration Turnitin :

- **TurnitinApiKey**: GUID à 32 caractères trouvé dans la console d’administration sous Intégrations.
- **TurnitinApiUrl**: URL HTTPS de votre console d’administration Turnitin.

Voici quelques instructions pour vous aider à obtenir ces informations.

**TurnitinApiUrl** est l’adresse hôte de votre console d’administration.
Exemple : `https://your-tenant-name.turnitin.com`

La console d’administration vous permet de créer une intégration et une clé d’API associées à l’intégration.

Sélectionnez **Intégrations** dans le menu latéral, puis **sélectionnez Ajouter** une intégration et donnez un nom à l’intégration.

![Capture d’écran montrant l’ajout d’une nouvelle intégration.](./educationImages/Assignments_mopo_turnitin2.png)

Une fois que vous aurez suivi les invites, la clé **TurnitinApiKey** vous sera donnée.
Copiez la clé d’API et collez-la dans le Microsoft Teams’administration.  C’est la seule fois que vous pouvez afficher la clé.

![Capture d’écran montrant la copie de la clé API.](./educationImages/Assignments_mopo_turnitin3.png)

En cliquant sur **le bouton Enregistrer** dans le Centre d’administration pour ce paramètre, laissez quelques heures pour que ces paramètres prennent effet.

## <a name="assignments-data"></a>Données sur les affectations

Les devoirs stockent les informations générées par les enseignants et les étudiants. Toutes les données sont partagées en collaboration entre l’enseignant et l’étudiant spécifique pour lequel les informations sont destinées à la classe. Il existe deux magasins de ce stock, SharePoint et en dehors de SharePoint.

>[!NOTE]
>Les mêmes règles s’appliquent également aux intégrations tierces telles que la progression de la lecture.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Données sur les affectations SharePoint des documents

Les fichiers des étudiants associés à une soumission pour affectation sont stockés dans une bibliothèque de documents (nommée : *Travail des étudiants).* Les fichiers associés aux devoirs créés par les enseignants et accessibles par les étudiants sont stockés dans une autre bibliothèque de documents (nommée : Fichiers de *classe)* dans le site d’équipe SharePoint de classe correspondant. Les intégrations tierces peuvent également stocker les données des devoirs sur le même site d’équipe de classe SharePoint site correspondant (nommé : Titre des *devoirs + Horodaté).*

#### <a name="files-associated-with-the-student"></a>Fichiers associés à l’étudiant

Les administrateurs informatiques peuvent utiliser l’outil de recherche de contenu pour rechercher des fichiers d’étudiants *(Travail* des *étudiants,* Fichiers de classe ou autres fichiers d’intégration 1er partie) liés aux envois de devoirs et aux fichiers liés aux devoirs. Par exemple, un administrateur peut effectuer une recherche sur tous les sites SharePoint de l’organisation et utiliser le nom et la classe ou le devoir de l’étudiant dans la requête de recherche pour trouver les données pertinentes pour une demande de sujet de données.

#### <a name="files-associated-with-the-teacher"></a>Fichiers associés à l’enseignant

Les administrateurs informatiques peuvent utiliser l’outilde recherche de contenu pour rechercher des fichiers d’enseignants (travail des *étudiants,* fichiers de classe ou autres fichiers d’intégration 1er partie) qui sont liés à des devoirs, ainsi que des fichiers distribués aux étudiants par les enseignants au sein d’une classe sur les devoirs. Par exemple, un administrateur peut effectuer une recherche sur tous les sites SharePoint de l’organisation et utiliser le nom de l’enseignant ainsi que le nom de la classe ou du devoir dans la requête de recherche pour trouver les données pertinentes pour une recherche de données.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Données sur les affectations en dehors SharePoint de documents

Certaines données liées aux devoirs ne sont pas stockées dans le site d’équipe de SharePoint de classe, ce qui signifie qu’elles ne sont pas accessibles avec la recherche de contenu. Cela inclut :

- Notes et commentaires de l’enseignant
- Liste des documents soumis à un devoir par chaque étudiant
- Les détails du devoir tels que l’échéance, etc.
- Données d’intégration tierces telles que les passages de progression de lecture ou les données de prononciation des étudiants

Pour ce type de données, un administrateur informatique ou propriétaire de données, tel qu’un enseignant, peut avoir à entrer dans le devoir dans l’équipe de classe pour trouver les données pertinentes pour une DSR. L’administrateur peut s’ajouter en tant que propriétaire à la classe et afficher toutes les affectations pour cette équipe de classe.

>[!NOTE]
>Si un étudiant ne fait plus partie de la classe, ses données sont peut-être toujours présentes dans la classe comme *n’étant plus inscrits.* L’étudiant devra fournir à l’administrateur du client la liste des classes dont il a pu faire partie.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Exporter en bloc des données d’affectation en dehors SharePoint de documents

#### <a name="for-a-student"></a>Pour un étudiant

Pour exporter en bloc les données d’un seul étudiant, avant de le supprimer des classes dont il fait partie, exécutez le [script](/microsoft-365/education/deploy/configure-assignments-for-teams) et fournissez ``userId`` le . Si l’étudiant a été supprimé du site, l’administrateur peut l’ajouter de nouveau à la classe avant d’utiliser le script, ou il peut fournir les informations et les informations dont il a pu faire ``userId`` ``classId`` partie.

Les données relatives aux soumissions d’étudiants seront exportées.

#### <a name="for-a-teacher"></a>Pour un enseignant

L’exportation en bloc des données d’affectation fonctionne de la même manière pour un étudiant, mais toutes les soumissions que l’enseignant a accès seront exportées.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Supprimer en bloc les données d’affectation en dehors SharePoint des bibliothèques de documents

#### <a name="for-a-student"></a>Pour un étudiant

Pour supprimer en bloc les données d’un seul étudiant, avant de le supprimer des classes dont il fait partie, exécutez le [script](/microsoft-365/education/deploy/configure-assignments-for-teams) et fournissez ``userId`` le . Si l’étudiant a été supprimé du site, l’administrateur peut l’ajouter de nouveau à la classe avant d’utiliser le script, ou il peut fournir les informations et les informations dont il a pu faire ``userId`` ``classId`` partie.

La fourniture d’un compte permet à l’administrateur de supprimer uniquement les informations sur ``ClassId`` l’étudiant d’une classe spécifique.

#### <a name="for-a-teacher"></a>Pour un enseignant

Étant donné que les données d’un devoir pour un enseignant sont partagées au sein de la classe, il n’existe pas d’option de suppression en bloc. Au lieu de cela, l’administrateur peut s’ajouter à la classe, aller à l’application et supprimer le devoir.

Pour plus d’informations, voir [Configurer les affectations pour Teams.](/microsoft-365/education/deploy/configure-assignments-for-teams)

## <a name="removing-assignments-and-grades"></a>Suppression des devoirs et des notes

Vous pouvez également utiliser des stratégies Teams pour supprimer les devoirs et notes pour un utilisateur spécifique ou pour l’ensemble de votre client.

Pour supprimer devoirs et notes pour un utilisateur individuel, accédez au Centre d’administration **Teams,** puis accédez à Teams applications et > **d’autorisation** pour créer une définition de stratégie d’autorisation d’application.  Lorsque vous créez la définition de  stratégie, définissez la stratégie des applications **Microsoft** de façon à bloquer des applications spécifiques, à autoriser toutes les autres applications et à ajouter des affectations à la liste des applications **bloquées.** Une fois votre nouvelle définition de stratégie enregistrée, affectez-la aux utilisateurs appropriés.

Pour supprimer devoirs et notes pour l’ensemble de votre client, accédez au Centre d’administration **Teams,** accédez aux applications **Teams >** Gérer les applications, et recherchez et sélectionnez **Devoirs** dans la liste des applications. Modifiez le paramètre de statut dans la page des paramètres de l’application Devoir sur _Bloqué._
