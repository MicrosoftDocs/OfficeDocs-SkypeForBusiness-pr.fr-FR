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
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89f9ba68dd4fbd1cef271c0dd0a3fb73e10637a7
ms.sourcegitcommit: 4060f20e8e3ce5a0464c12cfebdf8fe3473733fe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626980"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Utiliser le complément Réunion Teams dans Outlook
=======================================

Le complément réunion teams permet aux utilisateurs de planifier une réunion teams à partir d’Outlook. Le complément est disponible pour Outlook sur Windows, Mac, Web et mobile.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Complément réunion teams dans Outlook pour Windows

Le complément de réunion équipes est automatiquement installé pour les utilisateurs disposant de Microsoft teams et d’Office 2010, Office 2013 ou Office 2016 installés sur leur PC Windows. Le complément Réunion Teams apparaît sur le ruban Calendrier d'Outlook.

![Capture d’écran du complément réunion teams sur le ruban Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Pour pouvoir exécuter le fichier Regsvr32. exe, le complément réunion teams doit être installé sur l’ordinateur.
> - Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.
> - Les utilisateurs de Windows 7 doivent installer la [mise à jour du runtime C universel dans Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) pour que le complément réunion teams fonctionne.
> - Si vous utilisez une installation d’Office Outlook à partir du Microsoft Store, le complément de réunion teams n’est pas pris en charge. Les utilisateurs qui ont besoin de ce complément sont invités à installer la version « démarrer en un clic » d’Office, comme décrit dans l’article [Office sur Windows 10 en mode S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) .


## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Complément réunion teams dans Outlook pour Mac

Le bouton réunion teams dans Outlook pour Mac s’affiche dans le ruban d’Outlook pour Mac si Outlook exécute la version de production 16.24.414.0 et les versions ultérieures.

Les coordonnées de la réunion (le lien de participation aux équipes et les numéros de connexion) seront ajoutés à l’invitation à la réunion une fois que l’utilisateur a cliqué sur **Envoyer**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Complément réunion teams dans Outlook Web App

Le bouton réunions teams dans Outlook Web App s’affiche dans le cadre de la nouvelle création d’événements si l’utilisateur se trouve dans une version antérieure de la nouvelle version d’Outlook sur le Web. Pour plus d’informations sur la façon dont les utilisateurs peuvent essayer la version antérieure de la nouvelle version d’Outlook sur le Web, consultez le [blog Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) .

![Capture d’écran du complément réunion teams dans Outlook Web App](media/teams-meeting-add-in-web.png)

Les coordonnées de la réunion (le lien de participation aux équipes et les numéros de connexion) seront ajoutés à l’invitation à la réunion une fois que l’utilisateur a cliqué sur **Envoyer**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Complément réunion teams dans Outlook Mobile (iOS et Android)

Le bouton réunion teams apparaît dans les dernières versions de l’application Outlook iOS et Android.

![Capture d’écran du complément réunion teams dans Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Les coordonnées de la réunion (le lien de participation aux équipes et les numéros de connexion) seront ajoutés à l’invitation à la réunion une fois que l’utilisateur a cliqué sur **Envoyer**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Complément réunion teams dans et FindTime pour Outlook
FindTime est un complément pour Outlook qui permet aux utilisateurs de parvenir à un consensus sur le temps de réunion entre entreprises. Lorsque les invités de la réunion ont fourni leurs horaires préférés, FindTime envoie l’invitation à la réunion de la part de l’utilisateur. Si l’option **réunion en ligne** est sélectionnée dans FindTime, FindTime planifiera une réunion Skype entreprise ou Microsoft Teams. (FindTime va utiliser selon la configuration définie par votre organisation comme canal de réunion en ligne par défaut).

> [!NOTE]  
> Si vous avez enregistré un paramètre Skype entreprise dans votre [tableau de bord de Findtime](https://findtime.microsoft.com/UserDashboard), Findtime utilisera ce paramètre au lieu de Microsoft Teams. Si vous voulez utiliser Microsoft Teams, supprimez le paramètre Skype entreprise dans votre tableau de bord.

Pour plus d’informations, voir [planifier des réunions à l’aide de FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) .

## <a name="authentication-requirements"></a>Exigences d'authentification

Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne. Si les utilisateurs n'utilisent pas cette méthode pour se connecter, ils pourront continuer à utiliser le client Teams mais ne pourront pas planifier de réunions en ligne Teams à l'aide du complément Outlook. Vous pouvez résoudre ce problème de l'une des manières suivantes :

- Si l'authentification moderne n'est pas configurée pour votre organisation, vous devez la configurer.
- Si l’authentification moderne est configurée, mais qu’elle a été annulée dans la boîte de dialogue, vous devez demander aux utilisateurs de se reconnecter à l’aide de l’authentification multifacteur.

Pour savoir comment configurer l'authentification, reportez-vous à la rubrique [Modèles d'identité et authentification dans Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Activer les réunions privées

La **possibilité de planifier des réunions privées** doit être activée dans le centre d’administration Microsoft teams pour que le complément soit déployé. Dans le centre d’administration, accédez à **Réunions** > **Stratégies de la réunion**, puis, dans la section**Général**, définissez**Autoriser la planification des réunions privées ** vers sur.)

![Capture d’écran des paramètres dans le centre d’administration de Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

Le client Teams installe le complément correct en déterminant si les utilisateurs ont besoin de la version 32 bits ou 64 bits.

> [!NOTE]
> Il est possible que les utilisateurs doivent redémarrer Outlook après une installation ou mise à niveau de Teams pour obtenir le complément le plus récent.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Stratégie de mise à niveau des équipes et complément réunion teams pour Outlook

Les clients peuvent [choisir le passage de la mise à niveau de Skype entreprise à teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Les administrateurs de clients peuvent utiliser le mode de coexistence équipes pour définir ce voyage pour leurs utilisateurs. Les administrateurs de clients ont la possibilité de permettre aux utilisateurs d’utiliser teams en même temps que Skype entreprise (en mode insulaire). 

Lorsque les utilisateurs qui se trouvent dans le mode îlot planifient une réunion dans Outlook, il s’agit généralement de pouvoir choisir de planifier une réunion Skype entreprise ou Teams. Dans Outlook sur le Web, Outlook sur le Web et Outlook pour Mac, les utilisateurs voient les compléments Skype entreprise et équipe dans le mode îlot. En raison de certaines limitations de la version initiale, Outlook Mobile peut uniquement prendre en charge la création de réunions Skype entreprise **ou** Teams. Pour plus d’informations, consultez le tableau suivant.

| Mode de coexistence dans le centre d’administration teams | Fournisseur de réunions par défaut dans Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Archipels | Skype Entreprise |
| Skype Entreprise uniquement | Skype Entreprise |
| Collaboration avec teams dans Skype entreprise | Skype Entreprise |
| Skype entreprise avec collaboration et réunions en équipe | Équipes |
| Teams uniquement | Équipes |

## <a name="other-considerations"></a>Autres considérations à prendre en compte

Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :

- Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal. Les réunions de canal doivent être planifiées au sein de Teams.
- Le complément ne fonctionnera pas si un proxy d'authentification se trouve dans le chemin d'accès réseau de l'ordinateur de l'utilisateur et des services Teams.
- Les utilisateurs ne peuvent pas planifier des événements dynamiques à partir d’Outlook. Accédez à teams pour planifier des événements en direct. Pour plus d’informations, voir [qu’est-ce que Microsoft teams Live Events ?](teams-live-events/what-are-teams-live-events.md)

## <a name="troubleshooting"></a>Résolution des problèmes

Si vous ne parvenez pas à obtenir le complément de la réunion Teams pour installer Outlook, essayez de suivre ces étapes de dépannage.

- Vérifiez que toutes les mises à jour disponibles pour le client de bureau Outlook ont été appliquées.
- Redémarrez le client de bureau Teams.
- Déconnectez-vous, puis reconnectez-vous pour le client de bureau Teams.
- Fermez le client Outlook pour ordinateur de bureau. (Veillez à ce qu' Outlook ne soit pas exécuté en mode d’administration.)
- Vérifiez que le nom du compte utilisateur connecté ne contienne pas d’espaces. (Il s’agit d’un problème connu qui sera corrigé dans une prochaine mise à jour.)
- Vérifiez que l’authentification unique de Yammer ne soit pas activée.

Si votre administrateur a configuré Microsoft Exchange pour [contrôler l’accès à Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un délégué ne sera pas en mesure de planifier une réunion teams de la part du responsable. La solution de cette configuration est en développement et sera publiée prochainement. 

Pour des orientations générales sur la procédure de désactivation des compléments, consultez la rubrique [Afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
