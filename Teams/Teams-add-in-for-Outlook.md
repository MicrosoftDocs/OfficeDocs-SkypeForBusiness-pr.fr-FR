---
title: Utiliser le complément Réunion Microsoft Teams dans Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 10/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installe un complément dans Outlook qui permet aux utilisateurs de planifier une réunion Teams depuis Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6acb497937ad7548f8ffc745d12b0ddd813b3e46
ms.sourcegitcommit: 38efc00dfadc98cebd362877a1239d852f804f06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353190"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Utiliser le complément Réunion Teams dans Outlook
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Le complément Réunion Teams est installé automatiquement pour les utilisateurs pour lesquels Microsoft Teams et Office 2013 ou Office 2016 sont installés sur leur PC Windows. Le complément Réunion Teams apparaît sur le ruban Calendrier d'Outlook. 

![Capture d'écran du complément Teams sur le ruban Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Les utilisateurs de Windows 7 doivent installer [mise à jour pour Universal Runtime C dans Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) pour le complément de réunion équipes pour travailler.

Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.

> [!NOTE]
> Le complément Réunion Teams n'est pas disponible actuellement pour les utilisateurs Mac.

## <a name="authentication-requirements"></a>Exigences d'authentification

Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne. Si les utilisateurs n'utilisent pas cette méthode pour se connecter, ils pourront continuer à utiliser le client Teams mais ne pourront pas planifier de réunions en ligne Teams à l'aide du complément Outlook. Vous pouvez résoudre ce problème de l'une des manières suivantes :

- Si l'authentification moderne n'est pas configurée pour votre organisation, vous devez la configurer.
- Si l'authentification moderne est configurée, mais qu'ils l'ont annulée dans la boîte de dialogue, vous devez demander aux utilisateurs de se connecter à nouveau en utilisant l'authentification multifacteur.

Pour savoir comment configurer l'authentification, reportez-vous à la rubrique [Modèles d'identité et authentification dans Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Activer les réunions privées

Autoriser la planification pour les réunions privées doit être activée dans le modèle équipes & Skype entreprise centre d’administration pour le plug-in à déployer. Dans le centre d’administration, accédez à des **réunions** > de**Stratégies de réunion**et dans la section **Général** , bascule **Autoriser la planification de réunions privées** on.)

![Capture d’écran des paramètres dans les équipes & Skype entreprise centre d’administration.](media/teams-add-in-for-outlook-image1.png)

Le client Teams installe le complément correct en déterminant si les utilisateurs ont besoin de la version 32 bits ou 64 bits.

> [!NOTE]
> Il est possible que les utilisateurs doivent redémarrer Outlook après une installation ou mise à niveau de Teams pour obtenir le complément le plus récent.

## <a name="other-considerations"></a>Autres considérations

Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :
- Certaines fonctionnalités de réunion en ligne, comme l'enregistrement, les sondages et l'utilisation du tableau blanc ne sont pas encore disponibles.
- Des options de réunion ne sont pas disponibles pour le moment.
- Actuellement, vous pouvez uniquement inviter des personnes de votre entreprise, car les utilisateurs externes ne peuvent pas encore participer aux réunions.
- Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal. Les réunions de canal doivent être planifiées au sein de Teams. Actuellement, le complément Réunion Teams dans Outlook est disponible uniquement pour les utilisateurs Windows, mais il sera pris en charge sur Mac prochainement.
- Le complément ne fonctionnera pas si un proxy d'authentification se trouve dans le chemin d'accès réseau de l'ordinateur de l'utilisateur et des services Teams.
- Le complément est déployée incrémentielle et peuvent ne pas être disponible pour votre organisation encore.

## <a name="troubleshooting"></a>Identification et résolution des problèmes

Si vous ne peut pas obtenir la réunion équipes de complément pour Outlook pour installer, essayez les étapes de dépannage.

- Vérifiez que toutes les mises à jour disponibles pour le client de bureau Outlook ont été appliquées. 
- Redémarrez le client de bureau équipes.
- Déconnectez-vous, puis reconnectez-vous pour le client de bureau équipes.
- Redémarrez le client de bureau Outlook. (Assurez-vous que Outlook n’est pas en cours d’exécution en mode administrateur).
- Assurez-vous que le nom du compte utilisateur connecté ne contient-elle pas d’espaces. (Ceci est un problème connu et sera corrigé dans une prochaine mise à jour.)
- Assurez-vous que l’authentification unique (SSO) est activée.

Pour des orientations générales sur la procédure de désactivation des compléments, consultez la rubrique [Afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

