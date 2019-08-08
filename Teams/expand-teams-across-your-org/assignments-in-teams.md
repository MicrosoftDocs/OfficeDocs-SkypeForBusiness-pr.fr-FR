---
title: Affectations pour Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Apprenez à gérer les devoirs dans le centre d’administration Microsoft teams dans teams éducation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71417ccfc3387f030433a6b923e7fd21f32cd854
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232324"
---
# <a name="assignments-in-teams-for-education"></a>Devoirs dans Teams pour l’éducation

Les affectations sont des tâches ou des unités de travail attribuées à un étudiant ou à un membre d’équipe dans une classe dans le cadre de leur étude. Vous pouvez créer des devoirs au sein de votre classe Teams.

[En savoir plus sur les devoirs](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Devoirs dans le centre d’administration Microsoft teams

Les paramètres d’administration du centre d’administration Microsoft teams vous permettent d’activer ou de désactiver les fonctionnalités suivantes pour être disponibles pour les étudiants et enseignants au sein de votre organisation. Vous trouverez ci-dessous des paramètres relatifs aux devoirs:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Résumé du message électronique du tuteur de chaque semaine
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Les messages électroniques de tuteur sont des messages électroniques hebdomadaires envoyés aux parents ou tuteurs des étudiants. Les courriers électroniques contiennent des informations sur les affectations de la semaine précédente et de la semaine à venir, et seront envoyées pendant le week-end. Les messages électroniques doivent être mis à jour par les administrateurs à l’aide de la fonctionnalité School Data Sync.

Ce paramètre est désactivé par défaut.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode est une plate-forme de codage basée sur blocs qui donne vie à l’informatique à tous les étudiants. 

Il s’agit d’un produit ou service tiers soumis à ses propres conditions et politique de confidentialité. Vous êtes responsable de l’utilisation de produits et services tiers.

Ce paramètre est désactivé par défaut.

[En savoir plus sur MakeCode](https://www.microsoft.com/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Turnitin est un service de détection Plagiarism. Il s’agit d’un produit ou service tiers soumis à ses propres conditions et politique de confidentialité. Vous êtes responsable de l’utilisation de produits et services tiers.

Ce paramètre est désactivé par défaut.

Pour pouvoir activer Turnitin pour votre organisation, vous devez déjà disposer d’un abonnement Turnitin. Vous devrez entrer les informations supplémentaires suivantes qui se trouvent dans votre console d’administration Turnitin:

  * _TurnitinApiKey_: il s’agit d’un GUID de 32 caractères qui se trouve dans la console d’administration sous intégrations.
  * _TurnitinApiUrl_: il s’agit de l’URL HTTPS de votre console d’administration Turnitin.

Voici quelques instructions pour vous aider à obtenir ces informations.

TurnitinApiUrl est l’adresse d’hôte de votre console d’administration.
Example. `https://your-tenant-name.turnitin.com`

La console d’administration est l’endroit où vous pouvez créer une intégration et une clé d’API associée à l’intégration.

Sélectionnez **intégrations** dans le menu latéral, sélectionnez **Ajouter une intégration** et attribuez un nom à l’intégration.
![Capture d’écran montrant l’ajout d’une nouvelle intégration](./educationImages/Assignments_mopo_turnitin2.png)

Le TurnitinApiKey vous sera fourni une fois que vous aurez suivi les invites. Copiez la clé de l’API et collez-la dans le centre d’administration Microsoft Teams.  C’est la seule fois où vous pouvez afficher la clé.
![Capture d’écran montrant la copie de la clé de l’API](./educationImages/Assignments_mopo_turnitin3.png)

Lorsque vous cliquez sur le bouton **Enregistrer** dans le centre d’administration pour ce paramètre, attendez jusqu’à 24 heures avant que ces paramètres soient appliqués.

[En savoir plus sur l’intégration entre Turnitin et Microsoft teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[En savoir plus sur Turnitin](https://www.turnitin.com/)
