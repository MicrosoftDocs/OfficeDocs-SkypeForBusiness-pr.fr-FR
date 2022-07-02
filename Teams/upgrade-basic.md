---
title: Liste de contrôle de mise à niveau| Mise à niveau de Skype Business vers Teams | Étapes de base
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Suivez ce plan d’action en dix étapes accéléré pour passer d’une configuration de base Skype Entreprise à la configuration de Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: aab5ff20ef241b3e80eaf7909fb960eff94bfbe8
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606023"
---
# <a name="upgrade-basic"></a>Mettre à niveau de base

<a name="about-upgrade-basic"></a>

Conçue pour les organisations plus petites ou celles qui utilisent Skype Entreprise Online pour la messagerie instantanée (conversation) et les réunions uniquement, la liste de contrôle Upgrade Basic est un plan d’action accéléré qui inclut les activités principales recommandées et les ressources associées pour implémenter un déplacement réussi de Skype Entreprise vers Teams.

Ces dix étapes simples fournissent tout ce dont vous avez besoin pour une mise à niveau réussie. Ils sont conçus pour être terminés dans environ 30 à 45 jours, mais vous devez ajuster les dates d’achèvement des tâches en fonction du calendrier de mise à niveau de votre organisation.

> [!IMPORTANT]
> Skype Entreprise Online a pris sa retraite le 31 juillet 2021. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre parcours vers Microsoft Teams dès aujourd’hui.

Que se passe-t-il Skype Entreprise après la mise à niveau ? Après la mise à niveau de vos utilisateurs vers Teams (mode **Teams uniquement**) :

- Leur client Skype Entreprise est désactivé et tous les appels et conversations sont passés à Teams. Notez que cela ne désinstallera pas le client sur ses bureaux.
- Toutes les réunions Skype Entreprise planifiées avant le travail de mise à niveau comme prévu, mais toutes les nouvelles réunions sont planifiées dans Teams. Le plug-in Skype Entreprise ne sera plus disponible dans Outlook. 
- Si les utilisateurs tentent de se connecter à Skype Entreprise, ils reçoivent une notification de leur client indiquant qu’ils ont été mis à niveau vers Teams.
- Les utilisateurs doivent désinstaller manuellement le client Skype Entreprise sur leurs appareils mobiles.

Consultez notre [FAQ](./faq-journey.yml) pour obtenir des questions supplémentaires sur votre mise à niveau.

Vous n’êtes pas familiarisé avec Teams ? [Découvrez comment Teams](https://products.office.com/microsoft-teams/group-chat-software) réunit des conversations, des réunions, des fichiers, des applications Office et des intégrations tierces, en fournissant un hub unique pour le travail d’équipe dans Microsoft 365 et Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Étape 1. Notifier vos parties prenantes clés

*(Environ quatre à six semaines avant la mise à niveau)*

Les dirigeants supérieurs sont responsables de la réussite de l’entreprise; veillez à les tenir au courant des changements technologiques. Étant donné qu’il est possible que tout le monde n’ait pas reçu ou lu la notification d’éligibilité à la mise à niveau, vous devez informer vos parties prenantes (par exemple, PDG, professionnels de l’informatique, marketing et prospects de support technique) avant de commencer à planifier votre mise à niveau.

**Ressources:**

- [Exemple d’e-mail : communication avec les parties prenantes](upgrade-emails-surveys.md#step-1-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Étape 2. Préparer votre organisation pour Teams

*(Environ quatre à six semaines avant la mise à niveau)*

Teams offre des fonctionnalités de Skype Entreprise compatibles, telles que la messagerie instantanée (conversation) et les réunions, mais elle peut également faire beaucoup plus. En tant que véritable hub pour le travail d’équipe, Teams permet aux groupes de travail de gérer des projets, des fichiers, des conversations et des applications dans un même emplacement. Par défaut, Teams est activé pour toutes les organisations. Déterminez comment votre organisation utilisera Teams et configurera votre environnement pour qu’il réussisse. 

> [!Note]
> En tant que client Skype Entreprise existant, votre infrastructure réseau actuelle est probablement déjà configurée pour Teams. Pour confirmer cela, vous pouvez suivre les instructions relatives à la « planification technique complète » ci-dessous (facultatif).

**Ressources:**

- [Présentation de Teams](Teams-overview.md)
- [Prise en main de Microsoft Teams](get-started-with-teams-quick-start.md)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Étape 3. Connaître vos utilisateurs Skype Entreprise

*(Environ quatre semaines avant la mise à niveau)*

Les utilisateurs qui sont profondément adoptés sur Skype Entreprise peuvent avoir besoin d’un peu plus de temps ou d’assistance pour effectuer la transition vers Teams. Prenez le temps de passer en revue votre utilisation actuelle Skype Entreprise afin d’identifier vos principaux utilisateurs qui ont besoin d’un support supplémentaire et d’établir une base de référence d’utilisation que vous pouvez suivre par rapport à vos numéros post-mise à niveau.

**Ressources:**

- [Rapports Microsoft 365 dans le Centre d’administration](/microsoft-365/admin/activity-reports/activity-reports)

[Retour au début](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Étape 4. Notifier à vos utilisateurs qu’ils seront mis à niveau de Skype Entreprise vers Teams

*(Environ deux à trois semaines avant la mise à niveau)*

En informant vos utilisateurs, vous leur donnerez le temps de se familiariser avec Teams sans affecter négativement leur productivité, ce qui leur donnera une expérience utilisateur plus positive. Envoyez une communication pour lui dire ce qui change, pourquoi il change et comment il peut se préparer.

> [!Note]
> Si nécessaire, vous pouvez activer Teams pour vos utilisateurs via le Centre d'administration Microsoft 365 à ce stade.

**Ressources:**

- [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)
- [Exemple d’e-mail : annonce aux utilisateurs concernant Skype Entreprise](upgrade-emails-surveys.md#step-4-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Étape 5. Activer la notification de mise à niveau de l’utilisateur

*(Environ une semaine avant la mise à niveau)*

Maintenez l’élan de mise à niveau en activant la notification de mise à niveau de l’utilisateur via le portail d’administration, en fournissant une alerte visuelle dans le client Skype Entreprise indiquant que les utilisateurs sont mis à niveau de Skype Entreprise vers Teams.

**Ressources:**

- [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Étape 6. Rappeler à vos utilisateurs qu’ils seront mis à niveau de Skype Entreprise vers Teams

*(Environ cinq jours avant la mise à niveau)*

Les utilisateurs sont occupés avec leurs responsabilités quotidiennes. Le rappel de la mise à niveau en attente permet de s’assurer qu’ils n’oublient pas de suivre les étapes nécessaires pour se préparer à Teams. C’est le moment idéal pour rappeler aux utilisateurs la formation disponible et la prise en main de Teams.

**Ressources:**

- [Exemple d’e-mail : rappeler aux utilisateurs de bien démarrer avec Teams](upgrade-emails-surveys.md#step-6-email)

[Retour au début](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Étape 7. Mettez à niveau les utilisateurs vers Teams !

*(Jour de mise à niveau)*

Aujourd’hui est le jour où votre organisation passe officiellement à Teams en tant que solution de communication et de collaboration. Dans le Centre d’administration Microsoft Teams, activez le commutateur de mise à niveau en définissant le mode de coexistence **sur Teams uniquement**. (Dans le Centre d’administration, accédez à **Teams** >  **Paramètres de mise à niveau teams**.) Les utilisateurs recevront une notification dans leur client Skype Entreprise indiquant qu’ils ont été mis à niveau vers Teams.

Nous vous recommandons d’envoyer un e-mail de bienvenue à Teams une fois que tout le monde a été mis à niveau.

**Ressources:**

- [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)
- [Exemple d’e-mail : bienvenue des utilisateurs dans Teams](upgrade-emails-surveys.md#step-7-email)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Étape 8. Surveiller l’utilisation de Teams par rapport à votre base de référence

*(Environ une ou deux semaines après la mise à niveau)*

L’ajustement à une nouvelle technologie peut prendre un certain temps. Vérifiez l’utilisation pour vérifier que les utilisateurs utilisent Teams au même niveau (ou supérieur) qu’avec Skype Entreprise. Contactez les utilisateurs qui n’utilisent pas Teams aux niveaux attendus.

**Ressources:**

- [Afficher les données d’utilisation](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retour au début](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Étape 9. Mesurer la satisfaction des utilisateurs

*(Environ une ou deux semaines après la mise à niveau)*

La satisfaction des employés peut influencer la productivité, la rétention et, en fin de compte, les résultats opérationnels. Contactez vos utilisateurs pour évaluer les sentiments des utilisateurs concernant la mise à niveau et leur satisfaction vis-à-vis de Teams.

**Ressources:**

- [Exemple d’e-mail : vérifier auprès des utilisateurs](upgrade-emails-surveys.md#step-9-email), ainsi que [des enquêtes sur les utilisateurs](upgrade-emails-surveys.md#step-9-surveys)

[Retour au début](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Étape 10. Optimiser votre retour sur investissement avec Teams

*(En cours)*

Une fois que les utilisateurs sont à l’aise avec la messagerie instantanée (conversation) et les réunions dans Teams, encouragez-les à étendre leur cas d’utilisation à l’aide de la collaboration teams et de l’intégration d’applications, en optimisant véritablement leur nouvelle solution et en maximisant le retour sur investissement.

**Ressources:**

- [Exemple d’e-mail : encourager les utilisateurs à explorer Teams plus loin](upgrade-emails-surveys.md#step-10-email)

[Retour au début](#about-upgrade-basic)
