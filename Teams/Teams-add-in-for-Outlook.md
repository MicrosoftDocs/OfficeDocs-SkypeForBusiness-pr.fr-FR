---
title: Utiliser le complément Réunion Microsoft Teams dans Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installe un complément dans Outlook qui permet aux utilisateurs de planifier une réunion Teams depuis Outlook.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1cdd071dfe19c50650d6f18605a5aeed5b39300
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327846"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Utiliser le complément Réunion Teams dans Outlook
=======================================

Le complément réunion Teams permet aux utilisateurs de planifier une réunion Teams à partir d’Outlook. Le complément est disponible pour Outlook sur Windows, Mac, web et mobile.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Le complément Réunion Teams dans Outlook pour Windows

Le complément Réunion Teams est installé automatiquement pour les utilisateurs pour lesquels Microsoft Teams et Office 2010, Office2013 ou Office 2016 sont installés sur leur PC Windows. Le complément Réunion Teams apparaît sur le ruban Calendrier Outlook.

![Capture d'écran du complément réunion Teams sur le ruban Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Les autorisations utilisateur pour exécuter le fichier Regsvr32.exe constituent une condition minimale requise pour que le complément réunion Teams soit installé sur l’ordinateur.
> - Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.
> - Si vous utilisez une installation d’Office Outlook à partir du Microsoft Store, le complément réunion Teams n’est pas pris en charge. Les utilisateurs qui ont besoin de ce complément sont invités à installer la version « démarrer en un clic » d’Office, comme décrit dans l’article [Office sur Windows 10 en mode S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Le complément Réunion Teams dans Outlook pour Mac

Le bouton réunion Teams dans Outlook pour Mac apparaît dans le ruban Outlook pour Mac si Outlook est en cours d’exécution de la version de production 16.24.414.0 et ultérieure et est activé avec un abonnement client Office 365.

Les coordonnées de la réunion (lien de participation et numéros à composer Teams) sont ajoutées à l’invitation à la réunion une fois que l’utilisateur clique sur **envoyer**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Le complément Réunion Teams dans Outlook Web App

Le bouton réunions Teams dans Outlook Web App s’affiche dans le cadre de la création d’un nouvel événement si l’utilisateur utilise une version antérieure du nouveau Outlook sur le web. Pour en savoir plus sur la manière dont les utilisateurs peuvent essayer la version antérieure du nouvel Outlook sur le web, consultez le [blog Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Capture d'écran du complément réunion Teams dans Outlook Web App](media/teams-meeting-add-in-web.png)

Les coordonnées de la réunion (lien de participation et numéros à composer Teams) sont ajoutées à l’invitation à la réunion une fois que l’utilisateur clique sur **envoyer**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Complément réunion Teams dans Outlook Mobile (iOS et Android)

Le bouton réunion Teams s’affiche dans les dernières versions de l’application Outlook iOS et Android.

![Capture d'écran du complément réunion Teams dans Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Les coordonnées de la réunion (lien de participation et numéros à composer Teams) sont ajoutées à l’invitation à la réunion une fois que l’utilisateur clique sur **envoyer**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Complément réunion Teams dans et FindTime pour Outlook
FindTime est un complément pour Outlook qui permet aux utilisateurs d’atteindre un consensus sur les horaires de réunion au sein des entreprises. Une fois que les participants à la réunion ont fourni leurs horaires préférés, FindTime envoie l’invitation à la réunion au nom de l’utilisateur. Si l’option **Réunion en ligne** est sélectionnée dans FindTime, FindTime planifiera une réunion Skype Entreprise ou Microsoft Teams. (FindTime utilise la valeur définie par votre organisation comme canal de réunion en ligne par défaut).

> [!NOTE]  
> Si vous avez enregistré un paramètre Skype Entreprise dans votre [Tableau de bord Findtime](https://findtime.microsoft.com/UserDashboard), FindTime l’utilisera à la place de Microsoft Teams. Si vous voulez utiliser Microsoft Teams, supprimez le paramètre Skype Entreprise dans le tableau de bord.

Pour plus d’informations, consultez l’article[Planifier des réunions avec FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Exigences d'authentification

Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne. Si les utilisateurs n'utilisent pas cette méthode pour se connecter, ils pourront continuer à utiliser le client Teams mais ne pourront pas planifier de réunions en ligne Teams à l'aide du complément Outlook. Vous pouvez résoudre ce problème de l'une des manières suivantes :

- Si l'authentification moderne n'est pas configurée pour votre organisation, vous devez la configurer.
- Si l'authentification moderne est configurée, mais qu'ils l'ont annulée dans la boîte de dialogue, vous devez demander aux utilisateurs de se connecter à nouveau en utilisant l'authentification multifacteur.

Pour savoir comment configurer l'authentification, reportez-vous à la rubrique [Modèles d'identité et authentification dans Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Activer les réunions privées

**L'autorisation de planification de réunions privées** doit être activée depuis le Centre d'administration Microsoft Teams pour que le complément soit déployé. Dans le centre d’administration, accédez à **Réunions** > **Stratégies de la réunion**, puis, dans la section**Général**, définissez**Autoriser la planification des réunions privées ** vers sur.)

![Capture d’écran des paramètres dans le centre d’administration de Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

Le client Teams installe le complément correct en déterminant si les utilisateurs ont besoin de la version 32 bits ou 64 bits.

> [!NOTE]
> Il est possible que les utilisateurs doivent redémarrer Outlook après une installation ou mise à niveau de Teams pour obtenir le complément le plus récent.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Stratégie de mise à niveau Teams et complément réunions Teams pour Outlook

Les clients peuvent [choisir leur mise à niveau de la migration de Skype Entreprise vers Microsoft Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Les administrateurs de client peuvent utiliser le mode de coexistence Teams pour définir cette migration pour leurs utilisateurs. Les administrateurs de locataire ont la possibilité d’autoriser les utilisateurs à utiliser Teams en parallèle Skype Entreprise (mode d’îlots). 

Lorsque les utilisateurs qui travaillent en mode d’île planifient une réunion dans Outlook, ils peuvent généralement choisir de planifier une réunion Skype Entreprise ou une réunion Teams. Dans Outlook sur le web, Outlook Windows et Mac, les utilisateurs voient les compléments Skype Entreprise et Teams en mode île. En raison de certaines limitations de la version initiale, Outlook Mobile ne peut prendre en charge que la création de réunions Skype Entreprise **ou** Teams. Pour plus de détails, voir le tableau suivant.

| Mode de coexistence dans le centre d’administration Microsoft Teams | Fournisseur de réunions par défaut dans Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Île | Skype Entreprise |
| Skype Entreprise uniquement | Skype Entreprise |
| Collaboration Skype Entreprise avec Teams | Skype Entreprise |
| Collaboration Skype Entreprise avec Teams et réunions | Équipes |
| Teams uniquement | Équipes |

## <a name="other-considerations"></a>Autres considérations

Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :

- Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal. Les réunions de canal doivent être planifiées au sein de Teams.
- Le complément ne fonctionnera pas si un proxy d'authentification se trouve dans le chemin d'accès réseau de l'ordinateur de l'utilisateur et des services Teams.
- Les utilisateurs ne peuvent pas planifier d’événements en direct à partir d’Outlook. Accédez à Teams pour planifier des événements en direct. Pour plus d’informations, consultez [Que sont les événements en direct Microsoft Teams ?](teams-live-events/what-are-teams-live-events.md)

## <a name="troubleshooting"></a>Résolution des problèmes

Si vous ne parvenez pas à obtenir le complément de la réunion Teams pour installer Outlook, essayez de suivre ces étapes de dépannage.

- Assurez-vous que toutes les mises à jour disponibles pour le client de bureau Outlook aient été appliquées.
- Redémarrez le client de bureau Teams.
- Déconnectez-vous, puis reconnectez-vous pour le client de bureau Teams.
- Fermez le client Outlook pour ordinateur de bureau. (Veillez à ce qu' Outlook ne soit pas exécuté en mode d’administration.)
- Vérifiez que le nom du compte utilisateur connecté ne contienne pas d’espaces. (Il s’agit d’un problème connu qui sera corrigé dans une prochaine mise à jour.)
- Vérifiez que l’authentification unique de Yammer ne soit pas activée.

Si votre administrateur a configuré Microsoft Exchange pour [contrôler l’accès à Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un délégué ne pourra pas planifier une réunion Teams au nom du responsable. La solution pour cette configuration est en cours de développement et sera publiée ultérieurement. 

Pour des orientations générales sur la procédure de désactivation des compléments, consultez la rubrique [Afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
