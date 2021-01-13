---
title: Liste de contrôle de la mise à niveau| Mise à niveau de Skype Entreprise vers Teams | Étapes de base
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Suivez ce plan d’action rapide de dix étapes pour passer d’une configurer Skype Entreprise de base à la configurer Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809084"
---
# <a name="upgrade-basic"></a>Mise à niveau de base

<a name="about-upgrade-basic"></a>

Conçue pour les petites organisations ou celles qui utilisent Skype Entreprise Online pour la messagerie instantanée (conversation) et les réunions uniquement, la liste de contrôle Mise à niveau de base est un plan d’action accélérée qui inclut des activités principales et recommandées ainsi que des ressources associées pour la réussite du passage de Skype Entreprise à Teams.

Ces dix étapes simples fournissent tout ce dont vous avez besoin pour réussir la mise à niveau. Ces tâches sont conçues pour être effectuées en 30 à 45 jours, mais vous devez ajuster les dates d’achèvement des tâches en fonction du calendrier de mise à niveau de votre organisation.

> [!IMPORTANT]
> Skype Entreprise Online ne sera plus disponible le 31 juillet 2021. Après cette période, le service Skype Entreprise Online ne sera plus accessible ni pris en charge. Pour optimiser l’avantage et vous assurer que votre organisation a le temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre voyage vers Microsoft Teams dès aujourd’hui.

Qu’advient-il de Skype Entreprise après la mise à niveau ? Après la mise à niveau de vos utilisateurs vers Teams (mode **Teams uniquement**) :

- Son client Skype Entreprise est désactivé, et toutes les discussions et appels se placent dans Teams. Notez que cela ne désinstalle pas le client sur son ordinateur de bureau.
- Toute réunion Skype Entreprise qui a été programmée avant le travail de mise à niveau, mais toutes les nouvelles réunions sont prévues dans Teams. Le plug-in Skype Entreprise ne sera plus disponible dans Outlook. 
- Si un utilisateur tente de se connecter à Skype Entreprise, il reçoit une notification de la part de son client lui signalant qu’il a été mis à niveau vers Teams.
- Les utilisateurs doivent désinstaller manuellement le client Skype Entreprise sur leurs appareils mobiles.

Consultez notre [FAQ pour](https://aka.ms/SkypeToTeams-FAQ) d’autres questions sur votre mise à niveau.

Vous n’êtes pas familiarisé avec Teams ? Découvrez comment [Teams](https://products.office.com/microsoft-teams/group-chat-software) regroupe les conversations, les réunions, les fichiers, les applications Office et les intégrations tierces, en offrant une plateforme unique pour le travail d’équipe dans Microsoft 365 et Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Étape 1. Informer les principales parties prenantes

*(Environ quatre à six semaines avant la mise à niveau)*

Les cadres supérieurs sont responsables du succès de l’entreprise. assurez-vous de les tenir au courant des changements technologiques. Étant donné que toutes les personnes n’ont pas reçu ou lu la notification d’éligibilité à la mise à niveau, vous devez en informer les parties prenantes (par exemple, PDG, professionnels de l’informatique, responsables marketing et du service d’aide) avant de commencer à planifier votre mise à niveau.

**Ressources :**

- [Exemple de courrier électronique : communication avec les parties prenantes](upgrade-emails-surveys.md#step-1-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Étape 2. Préparer votre organisation pour Teams

*(Environ quatre à six semaines avant la mise à niveau)*

Teams offre des fonctionnalités compatibles de Skype Entreprise, telles que la messagerie instantanée (conversation) et les réunions, mais elle peut également en faire beaucoup plus. En tant que plateforme pour le travail d’équipe, Teams permet aux groupes de travail de gérer des projets, des fichiers, des conversations et des applications dans un seul emplacement. Par défaut, Teams est activé pour toutes les organisations. Décidez comment votre organisation utilisera Teams et configurez votre environnement pour le succès. 

> [!Note]
> En tant que client Skype Entreprise, votre infrastructure réseau actuelle est probablement déjà configurée pour Teams. Pour confirmer cela, vous pouvez suivre les instructions de « Planification technique complète » ci-dessous (facultatives).

**Ressources :**

- [Présentation de Teams](Teams-overview.md)
- [Prise en main de Microsoft Teams](get-started-with-teams-quick-start.md)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Étape 3. Connaître les utilisateurs de Skype Entreprise

*(Environ quatre semaines avant la mise à niveau)*

Les utilisateurs qui sont fortement adoptées sur Skype Entreprise peuvent avoir besoin de davantage de temps ou d’aide pour effectuer la transition vers Teams. Prenez le temps de passer en revue votre utilisation actuelle de Skype Entreprise pour identifier vos principaux utilisateurs qui ont besoin d’un support supplémentaire et établir un point de comparaison de votre utilisation, que vous pouvez suivre par rapport à vos numéros après la mise à niveau.

**Ressources :**

- [Rapports Microsoft 365 dans le Centre d’administration](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[Retour au début](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Étape 4. Informez vos utilisateurs qu’ils vont mettre à niveau Skype Entreprise vers Teams

*(Environ deux à trois semaines avant la mise à niveau)*

Si vous fournissez aé davantage de temps à vos utilisateurs, vous leur donnez le temps de vous familiariser avec Teams sans affecter négativement leur productivité et ainsi une expérience utilisateur plus positive. Envoyez une communication pour lui dire ce qui change, pourquoi elle change et comment elle peut se préparer.

> [!Note]
> Si nécessaire, vous pouvez activer Teams pour vos utilisateurs via le Centre d’administration Microsoft 365 pour le moment.

**Ressources :**

- [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)
- [Exemple de message électronique : annonce aux utilisateurs concernant Skype Entreprise](upgrade-emails-surveys.md#step-4-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Étape 5. Activer la notification de mise à niveau utilisateur

*(Environ une semaine avant la mise à niveau)*

Maintenez l’activation de la mise à niveau en activant la notification de mise à niveau utilisateur via le portail d’administration, en fournissant une alerte visuelle dans le client Skype Entreprise, qui avertit les utilisateurs de la mise à niveau de Skype Entreprise vers Teams.

**Ressources :**

- [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Étape 6. Rappelez à vos utilisateurs qu’ils vont mettre à niveau Skype Entreprise vers Teams

*(Environ cinq jours avant la mise à niveau)*

Les utilisateurs sont occupés par leurs responsabilités quotidiennes. Le rappel de la mise à niveau en attente permet de s’assurer qu’il doit suivre les étapes nécessaires pour se préparer à Teams. C’est le moment idéal pour rappeler aux utilisateurs la formation disponible et la façon de commencer à travailler avec Teams.

**Ressources :**

- [Exemple de courrier électronique : rappeler aux utilisateurs de commencer à travailler dans Teams](upgrade-emails-surveys.md#step-6-email)

[Retour au début](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Étape 7. Mettre à niveau les utilisateurs vers Teams !

*(Jour de mise à niveau)*

Aujourd’hui, c’est le jour où votre organisation fait officiellement la mise à niveau vers Teams comme solution de communication et de collaboration. Dans le Centre d’administration Microsoft Teams, activez le commutateur de mise à niveau en activant le mode de coexistence **sur Teams uniquement.** (Dans le Centre d’administration, voir **Paramètres à l’échelle de l’organisation.**  >  **Mise à niveau teams**.) Les utilisateurs reçoivent une notification dans leur client Skype Entreprise leur avertissant qu’ils ont été mis à niveau vers Teams.

Nous vous recommandons d’envoyer un courrier électronique de bienvenue à Teams après la mise à niveau de tout le monde.

**Ressources :**

- [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)
- [Exemple de courrier électronique : bienvenue des utilisateurs dans Teams](upgrade-emails-surveys.md#step-7-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Étape 8. Surveiller l’utilisation de Teams par rapport à votre référence

*(Environ une ou deux semaines après la mise à niveau)*

L’ajustement à une nouvelle technologie peut prendre du temps. Vérifiez l’utilisation pour vérifier que les utilisateurs utilisent Teams au même niveau, ou supérieur, comme dans Skype Entreprise. Consultez les utilisateurs qui n’utilisent pas Teams aux niveaux attendus.

**Ressources :**

- [Voir les données d’utilisation](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retour au début](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Étape 9. Mesurer la satisfaction des utilisateurs

*(Environ une ou deux semaines après la mise à niveau)*

La satisfaction des employés peut influencer la productivité, la rétention et, finalement, les résultats d’entreprise. Parlez-en à vos utilisateurs pour évaluer les opinions des utilisateurs concernant la mise à niveau et leur satisfaction concernant Teams.

**Ressources :**

- [Exemple de courrier électronique : contactez les utilisateurs,](upgrade-emails-surveys.md#step-9-email)ainsi que les enquêtes [des utilisateurs](upgrade-emails-surveys.md#step-9-surveys)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Étape 10. Optimisez votre retour sur investissement avec Teams

*(en cours)*

Une fois que les utilisateurs sont à l’aise avec la messagerie instantanée (conversation) et les réunions dans Teams, encouragez-les à étendre leur cas d’utilisation en utilisant la collaboration et l’intégration des applications Teams, optimiser véritablement leur nouvelle solution et maximiser un retour sur investissement.

**Ressources :**

- [Exemple de courrier électronique : encouragez les utilisateurs à explorer davantage Teams](upgrade-emails-surveys.md#step-10-email)

[Retour au début](#about-upgrade-basic)
