---
title: Liste de contrôle de mise à niveau | Mise à niveau de Skype entreprise vers équipes | Étapes de base
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Plan d’action en dix étapes accéléré pour la mise à niveau de Skype entreprise vers teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397155766bc966c9591f863a3f97fca59dcb1128
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35934549"
---
<a name="about-upgrade-basic"></a>

# <a name="upgrade-basic"></a>Mise à niveau de base

Conçu pour des organisations plus petites ou celles utilisant Skype entreprise Online pour la messagerie instantanée (discussion) et les réunions uniquement, la liste de contrôle de mise à niveau de base est un plan d’action accéléré incluant les activités principales et recommandées et les ressources associées à l’implémentation d’une transition réussie de Skype entreprise vers Teams.

Ces dix étapes simples permettent de tout ce dont vous avez besoin pour effectuer une mise à niveau réussie. Celles-ci sont conçues pour être achevées dans environ 30 à 45 jours, mais vous devez ajuster les dates d’achèvement des tâches en fonction du planning de mise à niveau de votre organisation.

> [!IMPORTANT]
> La mise à niveau de Skype entreprise Online sera annulée le 31 juillet 2021. Après cela, le service Skype entreprise Online ne sera plus accessible ou n’est plus pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui.

Qu’arrive-t-il à Skype entreprise après la mise à niveau? Une fois vos utilisateurs mis à niveau en équipes (mode**teams uniquement** ):

- Le client Skype entreprise est désactivé, et les discussions et les appels sont redirigés vers Teams. Notez que le client ne sera pas désinstallé sur son ordinateur de bureau.
- Toutes les réunions Skype entreprise planifiées avant la mise à niveau fonctionnent comme prévu, mais toutes les nouvelles réunions sont planifiées dans Teams.
- Si les utilisateurs essaient de se connecter à Skype entreprise, ils reçoivent une notification de leur client qu’ils ont été mis à niveau vers Teams.
- Les utilisateurs doivent désinstaller manuellement le client Skype entreprise sur leur appareil mobile.

Pour plus d’informations sur la mise à niveau, consultez notre [Forum aux questions](https://aka.ms/SkypeToTeams-FAQ) .

Vous ne connaissez pas les équipes? [Apprenez-en davantage sur la façon dont les équipes](https://products.office.com/microsoft-teams/group-chat-software) réunissent les conversations, les réunions, les fichiers, les applications Office et les intégrations tierces, en fournissant un seul Hub pour le travail en équipe dans Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Étape 1. Informer les principales parties prenantes

*(Environ quatre à six semaines avant la mise à niveau)*

Les leaders sont responsables du succès de l’entreprise; n’hésitez pas à nous en informer sur les changements technologiques. Dans la mesure où il est possible que tout le monde ne reçois ou ne lisent pas les notifications de mise à niveau, vous devez indiquer à vos parties prenantes (par exemple, PDG, professionnels de l’informatique, marketing et responsables du support technique) avant de commencer à planifier votre mise à niveau.

**Ressources**

- [Exemple de message électronique: communication avec les parties prenantes](upgrade-emails-surveys.md#step-1-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Étape 2. Préparer votre organisation pour Teams

*(Environ quatre à six semaines avant la mise à niveau)*

Teams propose des fonctionnalités Skype entreprise compatibles (par exemple, la messagerie instantanée, les réunions, etc.). En tant que concentrateur véritable pour le travail en équipe, teams permet aux groupes de travail de gérer les projets, les fichiers, les conversations et les applications en un seul endroit. Déterminez le mode d’utilisation des équipes par votre organisation et configurez votre environnement en vue de sa réussite.

> [!Note]
> En tant que client Skype entreprise existant, votre infrastructure réseau actuelle est probablement déjà configurée pour Teams. Pour confirmer cela, vous pouvez suivre les instructions complètes de planification technique associées au ci-dessous (facultatif).

**Ressources**

- [Présentation de Teams](Teams-overview.md)
- [En savoir plus sur les équipes et les canaux](teams-channels-overview.md)
- [Planification technique complète](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Gérer Microsoft Teams Rooms](https://aka.ms/MTRDocs)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Étape 3. Familiarisez-vous avec vos utilisateurs Skype entreprise

*(Environ quatre semaines avant la mise à niveau)*

Les utilisateurs en profondeur sur Skype entreprise peuvent avoir besoin de plus de temps ou d’aide pour effectuer la transition vers Teams. Prenez le temps de passer en revue l’utilisation de Skype entreprise pour identifier les principaux utilisateurs qui ont besoin d’une assistance supplémentaire et de définir un planning de référence d’utilisation pour vous permettre d’effectuer le suivi de vos numéros post-mise à niveau.

**Ressources**

- [Afficher les données d’utilisation dans les rapports d’activité dans Office 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

[Retour au début](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Étape 4. Informer vos utilisateurs qu’ils vont procéder à la mise à niveau de Skype entreprise vers teams

*(Environ deux à trois semaines avant la mise à niveau)*

Le rendez-vous d’un avis suffisant pour vos utilisateurs lui permettra d’avoir le temps de se familiariser avec les équipes, sans affecter le niveau de productivité, ce qui donne une expérience utilisateur plus positive. Envoyez une communication pour leur dire ce qui est en train de changer, la raison de la modification et la manière dont ils peuvent s’en préparer.

> [!Note]
> Le cas échéant, vous pouvez activer teams pour vos utilisateurs via le portail d’administration Office 365.

**Ressources**

- [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)
- [Exemple de message électronique: annonce aux utilisateurs de Skype entreprise](upgrade-emails-surveys.md#step-4-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Étape 5. Activer la notification de mise à niveau utilisateur

*(Environ une semaine avant la mise à niveau)*

La mise à jour de l’état de mise à niveau est activée via le portail d’administration, qui fournit une alerte visuelle dans le client Skype entreprise, que les utilisateurs sont en train de mettre à niveau de Skype entreprise vers Teams.

**Ressources**

- [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Étape 6. Rappelez à vos utilisateurs qu’ils effectuent la mise à niveau de Skype entreprise vers teams

*(Environ cinq jours avant la mise à niveau)*

Les utilisateurs ont occupé leurs responsabilités quotidiennes. Les rappels de la mise à niveau en attente permettent de veiller à ce qu’ils n’aient pas à effectuer les étapes nécessaires pour préparer les équipes. C’est le moment idéal pour rappeler aux utilisateurs les formations disponibles et comment commencer à utiliser Teams.

**Ressources**

- [Exemple de message électronique: rappeler aux utilisateurs de commencer à utiliser teams](upgrade-emails-surveys.md#step-6-email)

[Retour au début](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Étape 7. Mettre à niveau les utilisateurs vers équipes

*(Jour de la mise à niveau)*

C’est aujourd’hui que votre organisation est officiellement mise à niveau vers teams en tant que solution de communication et de collaboration. Dans le centre d’administration de Microsoft Teams, activez le commutateur de mise à niveau en définissant le mode de coexistence sur **équipes uniquement**. (Dans le centre d’administration, accédez à**mise à niveau des équipes** **des paramètres** > à l’échelle de l’organisation.) Les utilisateurs reçoivent une notification dans leur client Skype entreprise qu’ils ont été mis à niveau en équipes.

Nous vous recommandons d’avoir effectué une mise à niveau de tout le monde, vous envoyez un courrier électronique à vos équipes.

**Ressources**

- [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)
- [Exemple de courrier: Bienvenue des utilisateurs dans teams](upgrade-emails-surveys.md#step-7-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Étape 8. Surveiller l’utilisation des équipes par rapport à vos plannings de référence

*(Environ une ou deux semaines après la mise à niveau)*

Le réglage de votre nouvelle technologie peut prendre un certain temps. Activez l’option utilisation pour vérifier que les utilisateurs utilisent une équipe au même niveau (ou plus) qu’avec Skype entreprise. Archivez avec des utilisateurs qui n’utilisent pas les équipes aux niveaux attendus.

**Ressources**

- [Afficher les données d’utilisation](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retour au début](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Étape 9. Mesurer la satisfaction de l’utilisateur

*(Environ une ou deux semaines après la mise à niveau)*

La satisfaction des employés peut influer sur la productivité, la conservation et les résultats commerciaux. Contactez vos utilisateurs pour évaluer l’opinion de la mise à niveau par l’utilisateur et sa satisfaction vis-à-vis des équipes.

**Ressources**

- [Exemple de courrier: utiliser des utilisateurs](upgrade-emails-surveys.md#step-9-email)et des [enquêtes utilisateur](upgrade-emails-surveys.md#step-9-surveys)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Étape 10. Rentabilisez votre investissement grâce à teams

*Façon*

Lorsque les utilisateurs ont l’habitude d’utiliser la messagerie instantanée et les réunions en équipe, encouragez-les à prolonger leur cas d’utilisation en utilisant la collaboration et l’intégration des applications, en optimisant leur nouvelle solution et en maximisant le retour de votre investissement.

**Ressources**

- [Exemple de courrier: encourager les utilisateurs à découvrir les équipes](upgrade-emails-surveys.md#step-10-email)

[Retour au début](#about-upgrade-basic)
