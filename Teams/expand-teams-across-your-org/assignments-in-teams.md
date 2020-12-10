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
description: Apprenez à gérer les devoirs dans le centre d’administration Microsoft teams dans teams éducation.
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

Les fonctionnalités de devoirs et de notes dans teams éducation permettent aux enseignants d’affecter des tâches, des travaux ou des questionnaires aux étudiants. Les enseignants peuvent gérer les chronologies de devoirs, les instructions, ajouter des ressources pour les rendre plus adaptées aux rubriques, etc. Ils peuvent également suivre la progression de la classe et des étudiants individuels dans l’onglet notes.

[Pour en savoir plus, voir devoirs et notes dans teams pour l’éducation](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Pour plus d’informations sur les affectations d’équipe sur différentes plateformes, voir [fonctionnalités d’équipes par plate-forme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Intégrations des devoirs dans le centre d’administration Microsoft teams

À l’aide des paramètres d’administration dans le centre d’administration de Microsoft Teams, vous pouvez activer ou désactiver des fonctionnalités pour les enseignants au sein de votre organisation et leurs étudiants. Vous trouverez ci-dessous des paramètres relatifs aux devoirs :

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Résumé du message électronique du tuteur de chaque semaine


Les messages électroniques de tuteur sont envoyés chaque semaine à des parents ou tuteurs. Le message contient des informations sur les affectations de la semaine précédente et la semaine à venir. La synchronisation parent et tuteur peut être configurée à l’aide de [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).

1. Importez des informations de contact parent via une synchronisation parent et tuteur dans SDS. Pour obtenir des instructions sur l’activation de la synchronisation parent et tuteur, voir activation de la [synchronisation parent et tuteur](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Activez le paramètre Guardian dans le centre d’administration de Microsoft Teams, car ce paramètre est désactivé par défaut. Cela permettra aux enseignants d’envoyer un résumé hebdomadaire.

   > [!NOTE]
   > Les enseignants peuvent annuler le résumé en désélectionnant le paramètre au sein de leur équipe de classe personnelle (**paramètres d’affectation > messages parent/tuteur**).

Pour vérifier que les parents obtiennent le message électronique, les trois éléments suivants doivent être vrais :

 - Adresse de messagerie liée au profil d’étudiant dans SDS et balisée comme _parent_ ou _tuteur_. Pour plus d’informations, consultez [format de fichier de synchronisation parent et Guardian](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).

 - Les étudiants appartiennent à au moins une classe dans laquelle les messages ne sont pas désactivés par l’enseignant dans les [paramètres d’affectation](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

 - Le message électronique contient des informations sur les affectations ayant une date d’échéance au cours de la semaine précédente ou de la semaine prochaine.

Le paramètre par défaut de cette fonctionnalité est **désactivé**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode est une plate-forme de codage basée sur blocs qui donne vie aux sciences de l’ordinateur pour tous les étudiants. 

MakeCode est un produit Microsoft soumis aux [conditions d’utilisation](https://go.microsoft.com/fwlink/?LinkID=206977) et aux politiques de [confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839) de Microsoft.

Le paramètre par défaut de cette fonctionnalité est **désactivé**.

Pour activer les affectations MakeCode dans Teams, accédez au **Centre d’administration teams**, accédez à la section **affectations** , puis activez l’option bascule **MakeCode.** Cliquez sur **Enregistrer**. Autorisez quelques heures pour que les paramètres soient pris en compte.

Pour plus d’informations sur le fonctionnement de cette fonctionnalité, consultez cette [démonstration vidéo](https://makecode.com/blog/teams/teams-assignments).

[En savoir plus sur MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) est un service d’intégrité éducation. Il s’agit d’un produit ou service tiers soumis à ses propres modalités et politique de confidentialité. Vous êtes responsable de l’utilisation des produits et services tiers.

Le paramètre par défaut de cette fonctionnalité est **désactivé**.

Pour activer Turnitin pour votre organisation, vous aurez besoin d’un abonnement Turnitin. Vous pouvez ensuite entrer les informations suivantes, qui se trouvent dans votre console d’administration Turnitin :

  * **TurnitinApiKey**: il s’agit d’un GUID de 32 caractères qui se trouve dans la console d’administration sous intégrations.
  * **TurnitinApiUrl**: il s’agit de l’URL HTTPS de votre console d’administration Turnitin.

Voici quelques instructions pour vous aider à obtenir ces informations.

**TurnitinApiUrl** est l’adresse d’hôte de votre console d’administration.
Example `https://your-tenant-name.turnitin.com`

La console d’administration est l’endroit où vous pouvez créer une intégration et une clé d’API associée à l’intégration.

Sélectionnez **intégrations** dans le menu latéral, sélectionnez **Ajouter une intégration** et attribuez un nom à l’intégration.

![Capture d’écran montrant l’ajout d’une nouvelle intégration](./educationImages/Assignments_mopo_turnitin2.png)

Le **TurnitinApiKey** vous sera fourni une fois que vous aurez suivi les invites. Copiez la clé de l’API et collez-la dans le centre d’administration Microsoft Teams.  C’est la seule fois où vous pouvez afficher la clé.

![Capture d’écran montrant la copie de la clé de l’API](./educationImages/Assignments_mopo_turnitin3.png)

Lorsque vous cliquez sur le bouton **Enregistrer** dans le centre d’administration pour ce paramètre, autorisez quelques heures pour que les paramètres soient pris en compte.

