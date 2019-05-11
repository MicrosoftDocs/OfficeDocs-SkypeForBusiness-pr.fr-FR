---
title: Affectations pour Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Découvrez comment gérer les affectations dans le centre d’administration Microsoft Teams dans les équipes pour l’éducation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 263b9dda6929bd6956df803a33764634808cddf3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914022"
---
# <a name="assignments-in-teams-for-education"></a>Devoirs dans Teams pour l’éducation

Les affectations sont des tâches ou les unités de travail affecté à un membre étudiant ou de l’équipe dans une classe dans le cadre de leur étude. Vous pouvez créer des affectations dans votre classe d’équipes.

[Pour plus d’informations sur les affectations](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Affectations dans le centre d’administration Microsoft Teams

Avec les paramètres d’administration dans le centre d’administration de Microsoft Teams vous pouvez activer les fonctionnalités suivantes activé ou désactivé soit disponible pour étudiants et enseignants au sein de votre organisation. Paramètres liés aux affectations sont les suivantes :

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Résumé de l’e-mail guardian hebdomadaire
Les messages électroniques Guardian sont hebdomadaires courriels étudiants parents ou tuteurs. Les e-mails contiendront des informations sur les affectations de la semaine précédente et pour la semaine à venir et sont envoyées pendant le week-end. Les e-mails doivent être mis à jour par les administrateurs à l’aide de la fonctionnalité de synchronisation des données de l’école.

Ce paramètre est désactivé par défaut.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode est une plateforme de codage bloc qui offre vie informatique pour tous les étudiants. 

Il s’agit d’un produit tiers ou un service qui est soumis à ses propres termes et une politique de confidentialité. Vous êtes responsable de l’utilisation des services et des produits tiers.

Ce paramètre est désactivé par défaut.

[En savoir plus sur MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin est un service de détection plagiat. Il s’agit d’un produit tiers ou un service qui est soumis à ses propres termes et une politique de confidentialité. Vous êtes responsable de l’utilisation des services et des produits tiers.

Ce paramètre est désactivé par défaut.

Pour activer correctement Turnitin pour votre organisation, vous devrez possède déjà un abonnement Turnitin. Vous devrez saisir les informations supplémentaires suivantes, qui se trouve dans la console d’administration de Turnitin :

  * _TurnitinApiKey_: il s’agit d’un GUID à 32 caractères trouvé dans la console d’administration sous intégrations.
  * _TurnitinApiUrl_: il s’agit de l’URL HTTPS de votre console d’administration Turnitin.

Voici quelques instructions pour vous aider à obtenir ces informations.

Le TurnitinApiUrl est l’adresse d’hôte de la console d’administration.
![Recherche de la TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin1.png)

Accédez à l’onglet intégrations et ajoutez une intégration.
![Recherche de la TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin2.png)

Le TurnitinApiKey bénéficiera vous une fois que vous suivez les invites. Copiez cette clé et collez-le dans le centre d’administration Microsoft Teams. 
![Recherche de la TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin3.png)

[Pour plus d’informations sur l’intégration entre Turnitin et Microsoft Teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[En savoir plus sur Turnitin](https://www.turnitin.com/)
