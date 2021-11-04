---
title: Affectations pour Teams
author: cichur
ms.author: v-mahoffman
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
ms.openlocfilehash: 1c2dbc67fdbc55c9ff2a7b2e16cb0957886de3dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758306"
---
# <a name="assignments-in-teams-for-education"></a>Devoirs dans Teams pour l’éducation

Les fonctionnalités Devoirs et Notes Teams pour l'éducation aux enseignants d’attribuer des tâches, du travail ou des questionnaires à leurs étudiants. Les enseignants peuvent gérer la chronologie des devoirs, les instructions, ajouter des ressources à rendre, notes avec des rubriques, etc. Ils peuvent également suivre la progression de la classe et de l’étudiant individuel dans l’onglet Notes.

[En savoir plus sur les devoirs et les notes dans Teams pour l'éducation.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Pour plus d’informations sur Teams devoirs sur différentes plateformes, voir Teams [fonctionnalités par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Intégrations des devoirs dans le centre Microsoft Teams’administration

En utilisant les paramètres d’administration du Microsoft Teams d’administration, vous pouvez activer ou désactiver des fonctionnalités pour les enseignants de votre organisation et leurs étudiants. Les paramètres suivants sont liés aux devoirs :

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>E-mail hebdomadaire des tuteurs


Les messages tuteurs sont envoyés chaque week-end à des parents ou tuteurs légaux. Le message électronique contient des informations sur les devoirs de la semaine précédente et de la semaine à venir. La synchronisation des parents et tuteurs peut être configurée à [l’aide de Synchronisation des données scolaires.](/schooldatasync/parent-contact-sync)

1. Importez les coordonnées des parents via la synchronisation des parents et tuteurs dans SDS. Pour obtenir des instructions sur l’activation de la synchronisation des parents et tuteurs, voir Activer la synchronisation des [parents et tuteurs.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Activer le paramètre tuteur dans le Microsoft Teams d’administration, car ce paramètre est désactivé par défaut. Cela permettra aux enseignants d’envoyer une résumé hebdomadaire.

   > [!NOTE]
   > Les enseignants peuvent refuser les e-mails du parent/tuteur en désélectionner le paramètre au sein de leur équipe de classe personnelle (e-mail de Paramètres >**du parent/tuteur).**

Pour vérifier que les parents vont recevoir le message électronique, les trois éléments suivants doivent être vérifiés :

 - Adresse e-mail jointe au profil d’étudiant dans SDS et marquée en tant que _parent_ ou _tuteur._ Pour plus d’informations, voir Format de fichier de synchronisation des parents et [tuteurs.](/schooldatasync/parent-contact-sync-file-format)

 - Les étudiants appartiennent à au moins une classe dans laquelle le courrier électronique n’est pas désactivé par l’enseignant dans les [paramètres de devoir.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Les messages électroniques contiennent des informations sur les devoirs dont la date d’échéance était la semaine précédente ou la semaine à venir.

Le paramètre par défaut de cette fonctionnalité est - **Non.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode est une plateforme de codage en blocs qui donne vie à l’informatique de tous les étudiants. 

MakeCode est un produit Microsoft soumis aux conditions d’utilisation et aux politiques [de confidentialité de](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft. [](https://go.microsoft.com/fwlink/?LinkID=206977)

Le paramètre par défaut de cette fonctionnalité est - **Non.**

Pour activer les affectations MakeCode dans Teams, accédez au Centre d’administration **Teams,** accédez à la section  **Devoirs,** puis activez l’option bascule MakeCode. Cliquez sur **Enregistrer**. Laissez quelques heures à ces paramètres pour qu’ils prennent effet.

Pour plus d’informations sur le fonctionnement de cette fonctionnalité, regardez [cette vidéo de démonstration.](https://makecode.com/blog/teams/teams-assignments)

[En savoir plus sur MakeCode.](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) est un service d’intégrité académique. Il s’agit d’un produit ou service tiers soumis à ses propres conditions et politique de confidentialité. Vous êtes responsable de l’utilisation des produits et services tiers.

Le paramètre par défaut pour cette fonctionnalité est - **Non.**

Pour activer Turnitin pour votre organisation, vous devez avoir un abonnement Turnitin. Vous pouvez ensuite entrer les informations suivantes, qui se trouvent dans votre console d’administration Turnitin :

  * **TurnitinApiKey**: GUID à 32 caractères trouvé dans la console d’administration sous Intégrations.
  * **TurnitinApiUrl**: URL HTTPS de votre console d’administration Turnitin.

Voici quelques instructions pour vous aider à obtenir ces informations.

**TurnitinApiUrl** est l’adresse hôte de votre console d’administration.
Exemple : `https://your-tenant-name.turnitin.com`

La console d’administration est l’endroit où vous pouvez créer une intégration et une clé d’API associées à l’intégration.

Sélectionnez **Intégrations** dans le menu latéral, puis **sélectionnez Ajouter** une intégration et donnez un nom à l’intégration.

![Capture d’écran montrant l’ajout d’une nouvelle intégration.](./educationImages/Assignments_mopo_turnitin2.png)

Une fois que vous aurez suivi les invites, la clé **TurnitinApiKey** vous sera donnée. Copiez la clé d’API et collez-la dans le Microsoft Teams’administration.  C’est la seule fois que vous pouvez afficher la clé.

![Capture d’écran montrant la copie de la clé API.](./educationImages/Assignments_mopo_turnitin3.png)

En cliquant sur **le bouton Enregistrer** dans le Centre d’administration pour ce paramètre, laissez quelques heures pour que ces paramètres prennent effet.

### <a name="removing-assignments-and-grades"></a>Suppression des devoirs et des notes
Vous pouvez utiliser des stratégies Teams pour supprimer les devoirs et notes pour un utilisateur spécifique ou pour l’ensemble de votre client. 

Pour supprimer devoirs et notes pour un utilisateur individuel, accédez au Centre d’administration **Teams,** puis accédez à Teams applications et > **d’autorisation** pour créer une définition de stratégie d’autorisation d’application.  Lorsque vous créez la définition de  stratégie, définissez la stratégie des applications **Microsoft** de façon à bloquer des applications **spécifiques,** à autoriser toutes les autres applications et à ajouter des affectations à la liste des applications bloquées. Une fois votre nouvelle définition de stratégie enregistrée, affectez-la aux utilisateurs appropriés.

Pour supprimer devoirs et notes pour l’ensemble de votre client, accédez au Centre d’administration **Teams,** accédez aux applications **Teams >** Gérer les applications, et recherchez et sélectionnez **Devoirs** dans la liste des applications. Modifiez le paramètre de statut dans la page des paramètres de l’application Devoir sur _Bloqué._ 
