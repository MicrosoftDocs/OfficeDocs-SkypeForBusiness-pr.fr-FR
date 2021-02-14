---
title: Affectations pour Teams
author: cichur
ms.author: v-cichur
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
description: Découvrez comment gérer les devoirs dans le Centre d’administration Microsoft Teams dans Teams pour l’Éducation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616908"
---
# <a name="assignments-in-teams-for-education"></a>Devoirs dans Teams pour l’éducation

Les fonctionnalités Devoirs et Notes de Teams pour l’éducation permettent aux enseignants d’attribuer des tâches, du travail ou des questionnaires à leurs étudiants. Les enseignants peuvent gérer la chronologie des devoirs, les instructions, ajouter des ressources à rendre, notes avec des rubriques, etc. Ils peuvent également suivre la progression de la classe et de l’étudiant individuel dans l’onglet Notes.

[En savoir plus sur les devoirs et les notes dans Teams pour l’éducation.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Pour plus d’informations sur les affectations de Teams sur différentes plateformes, consultez [les fonctionnalités de Teams par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Intégrations des devoirs dans le Centre d’administration Microsoft Teams

En utilisant les paramètres d’administration du Centre d’administration Microsoft Teams, vous pouvez activer ou désactiver des fonctionnalités pour les enseignants de votre organisation et leurs étudiants. Les paramètres suivants sont liés aux devoirs :

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>E-mail hebdomadaire des tuteurs


Les messages tuteurs sont envoyés chaque week-end à des parents ou tuteurs légaux. Le message électronique contient des informations sur les devoirs de la semaine précédente et de la semaine à venir. La Synchronisation des parents et tuteurs peut être configurée à l’aide [de School Data Sync.](https://docs.microsoft.com/schooldatasync/parent-contact-sync)

1. Importez les coordonnées des parents via la synchronisation des parents et tuteurs dans SDS. Pour obtenir des instructions sur l’activation de la synchronisation des parents et tuteurs, voir Activer la synchronisation des [parents et tuteurs.](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Activer le paramètre tuteur dans le Centre d’administration Microsoft Teams, car ce paramètre est désactivé par défaut. Cela permettra aux enseignants d’envoyer une résumé hebdomadaire.

   > [!NOTE]
   > Les enseignants peuvent se désinsélectionner de la digestibilité en désélectionner le paramètre au sein de leur équipe de classe personnelle (Paramètres des devoirs >**e-mails du parent/tuteur).**

Pour vérifier que les parents vont recevoir le message électronique, les trois éléments suivants doivent être vérifiés :

 - Adresse e-mail jointe au profil d’étudiant dans SDS et marquée en tant que _parent_ ou _tuteur._ Pour plus d’informations, voir Format de fichier de synchronisation des parents et [tuteurs.](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)

 - Les étudiants appartiennent à au moins une classe dans laquelle le courrier électronique n’est pas désactivé par l’enseignant dans les [paramètres de devoir.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Les messages électroniques contiennent des informations sur les devoirs dont la date d’échéance était la semaine précédente ou la semaine à venir.

Le paramètre par défaut pour cette fonctionnalité est - **Non.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode est une plateforme de codage en blocs qui donne vie à tous les étudiants en informatique. 

MakeCode est un produit Microsoft qui est soumis aux conditions d’utilisation et aux politiques [de confidentialité de](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft. [](https://go.microsoft.com/fwlink/?LinkID=206977)

Le paramètre par défaut pour cette fonctionnalité est - **Non.**

Pour activer les affectations MakeCode dans Teams, accédez au Centre d’administration **Teams,** accédez à la section **Devoirs,** puis activez l’option de bascule MakeCode. Cliquez sur **Enregistrer**. Laissez quelques heures à ces paramètres pour qu’ils prennent effet.

Pour plus d’informations sur le fonctionnement de cette fonctionnalité, voir cette [vidéo de démonstration.](https://makecode.com/blog/teams/teams-assignments)

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

![Capture d’écran montrant l’ajout d’une nouvelle intégration](./educationImages/Assignments_mopo_turnitin2.png)

Une fois que vous aurez suivi les invites, la clé **TurnitinApiKey** vous sera donnée. Copiez la clé d’API et collez-la dans le Centre d’administration Microsoft Teams.  C’est la seule fois que vous pouvez afficher la clé.

![Capture d’écran montrant la copie de la clé API](./educationImages/Assignments_mopo_turnitin3.png)

En cliquant sur **le bouton Enregistrer** dans le Centre d’administration pour ce paramètre, laissez quelques heures pour que ces paramètres prennent effet.

