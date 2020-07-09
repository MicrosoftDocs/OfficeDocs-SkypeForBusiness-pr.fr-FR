---
title: Utiliser le complément Réunion Microsoft Teams dans Outlook
author: LanaChin
ms.author: v-lanac
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
ms.openlocfilehash: 0e9111f54bc3f94c028c8ddc8549e1202326df4f
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085240"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Utiliser le complément Réunion Teams dans Outlook
=======================================

Le complément réunion Teams permet aux utilisateurs de planifier une réunion Teams à partir d’Outlook. Le complément est disponible pour Outlook sur Windows, Mac, web et mobile.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Le complément Réunion Teams dans Outlook pour Windows

Le complément de réunion équipes est automatiquement installé pour les utilisateurs disposant de Microsoft teams et d’Office 2013, d’Office 2016 ou d’Office 2019 installés sur leur PC Windows. Le complément Réunion Teams apparaît sur le ruban Calendrier Outlook.

![Capture d'écran du complément réunion Teams sur le ruban Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Il n’existe **pas d’URL directe** liée au complément équipes.
> - Il existe d’autres éléments à prendre en considération si votre organisation exécute des équipes et Skype entreprise. Dans certains cas, le complément teams n’est pas disponible dans Outlook. Pour plus d’informations, consultez la rubrique [mise à niveau de Skype entreprise vers teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
> - Les autorisations utilisateur pour exécuter le fichier Regsvr32.exe constituent une condition minimale requise pour que le complément réunion Teams soit installé sur l’ordinateur.
> - Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.
> - Si vous utilisez une installation d’Office Outlook à partir du Microsoft Store, le complément réunion Teams n’est pas pris en charge. Les utilisateurs qui ont besoin de ce complément sont invités à installer la version « démarrer en un clic » d’Office, comme décrit dans l’article [Office sur Windows 10 en mode S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Le complément Réunion Teams dans Outlook pour Mac

Le bouton réunion teams dans Outlook pour Mac s’affiche dans le ruban d’Outlook pour Mac si Outlook exécute la version de production 16.24.414.0 et les versions ultérieures, et est activée avec un abonnement client Microsoft 365 ou Office 365.

Les coordonnées de la réunion (lien de participation et numéros à composer Teams) sont ajoutées à l’invitation à la réunion une fois que l’utilisateur clique sur **envoyer**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Le complément Réunion Teams dans Outlook Web App

Le bouton réunions Teams dans Outlook Web App s’affiche dans le cadre de la création d’un nouvel événement si l’utilisateur utilise une version antérieure du nouveau Outlook sur le web. Pour en savoir plus sur la manière dont les utilisateurs peuvent essayer la version antérieure du nouvel Outlook sur le web, consultez le [blog Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Capture d'écran du complément réunion Teams dans Outlook Web App](media/teams-meeting-add-in-web.png)

Les coordonnées de la réunion (lien de participation et numéros à composer Teams) sont ajoutées à l’invitation à la réunion une fois que l’utilisateur clique sur **envoyer**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Complément réunion Teams dans Outlook Mobile (iOS et Android)

Le bouton réunion Teams s’affiche dans les dernières versions de l’application Outlook iOS et Android.

![Capture d'écran du complément réunion Teams dans Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Les coordonnées de la réunion (lien de participation et numéros à composer Teams) sont ajoutées à l’invitation à la réunion une fois que l’utilisateur clique sur **envoyer**.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Complément réunion teams et FindTime pour Outlook

FindTime est un complément pour Outlook qui permet aux utilisateurs de parvenir à un consensus sur le temps de réunion entre entreprises. Une fois que les participants à la réunion ont fourni leurs horaires préférés, FindTime envoie l’invitation à la réunion au nom de l’utilisateur. Si l’option **Réunion en ligne** est sélectionnée dans FindTime, FindTime planifiera une réunion Skype Entreprise ou Microsoft Teams. (FindTime utilise la valeur définie par votre organisation comme canal de réunion en ligne par défaut).

> [!NOTE]  
> Si vous avez enregistré un paramètre Skype Entreprise dans votre [Tableau de bord Findtime](https://findtime.microsoft.com/UserDashboard), FindTime l’utilisera à la place de Microsoft Teams. Si vous voulez utiliser Microsoft Teams, supprimez le paramètre Skype Entreprise dans le tableau de bord.

Pour plus d’informations, voir [planifier des réunions avec FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Exigences d'authentification

Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne. Si les utilisateurs ne sont pas en mesure de se connecter, ils pourront toujours utiliser le client Teams, mais ils ne seront pas en mesure de planifier des réunions teams en ligne à l’aide du complément Outlook. Vous pouvez résoudre ce problème de l'une des manières suivantes :

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

Lorsque les utilisateurs qui travaillent en mode d’île planifient une réunion dans Outlook, ils peuvent généralement choisir de planifier une réunion Skype Entreprise ou une réunion Teams. Dans Outlook sur le Web, dans Outlook et dans Outlook pour Mac, les utilisateurs voient les compléments Skype entreprise et équipe en mode îlots par défaut. Vous pouvez configurer un paramètre de stratégie de réunion équipes pour contrôler si les utilisateurs en mode îlot peuvent uniquement utiliser le complément réunion teams ou les compléments réunion Skype entreprise et réunion Teams.

En raison de certaines limitations de la version initiale, Outlook Mobile ne peut prendre en charge que la création de réunions Skype Entreprise **ou** Teams. Pour plus de détails, voir le tableau suivant.

| Mode de coexistence dans le centre d’administration Microsoft Teams | Fournisseur de réunions par défaut dans Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Île | Skype Entreprise |
| Skype Entreprise uniquement | Skype Entreprise |
| Collaboration Skype Entreprise avec Teams | Skype Entreprise |
| Collaboration Skype Entreprise avec Teams et réunions | Équipes |
| Teams uniquement | Équipes |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>Définir si les utilisateurs en mode d’îlot peuvent uniquement utiliser le complément de réunion équipes ou les compléments réunion et les réunions Skype entreprise

En tant qu’administrateur, vous pouvez configurer un paramètre de stratégie de réunion équipes pour contrôler le complément de réunion Outlook utilisé pour *les utilisateurs en mode îlot*. Vous pouvez spécifier si les utilisateurs peuvent uniquement utiliser le complément de réunion teams ou les compléments de réunion équipes et de réunions Skype entreprise pour planifier des réunions dans Outlook.

Vous pouvez uniquement appliquer cette politique aux utilisateurs qui sont en mode îlot et dont le paramètre **AllowOutlookAddIn** est défini sur **true** dans la stratégie de réunion Teams. Pour plus d’informations sur la définition de cette stratégie, voir [définir le fournisseur de la réunion pour les utilisateurs en mode îlot](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).

## <a name="other-considerations"></a>Autres considérations

Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :

- Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal. Les réunions de canal doivent être planifiées au sein de Teams.
- Le complément ne fonctionnera pas si un proxy d’authentification figure dans le chemin réseau du PC et des services d’équipe de l’utilisateur.
- Les utilisateurs ne peuvent pas planifier d’événements en direct à partir d’Outlook. Accédez à Teams pour planifier des événements en direct. Pour plus d’informations, consultez [Que sont les événements en direct Microsoft Teams ?](teams-live-events/what-are-teams-live-events.md)

Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="troubleshooting"></a>Résolution des problèmes

Procédez comme suit pour résoudre les problèmes liés au complément réunion Teams.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Le complément réunion teams dans Outlook pour Windows ne s’affiche pas

Si vous ne parvenez pas à obtenir le complément de la réunion Teams pour installer Outlook, essayez de suivre ces étapes de dépannage.

[Téléchargez](https://aka.ms/SaRA-TeamsAddInScenario) et exécutez l' [Assistant de récupération du support Microsoft](https://aka.ms/SaRA_Home) pour effectuer des étapes de résolution des problèmes et des correctifs automatisés.

Vous pouvez également effectuer les étapes suivantes manuellement :

- Les utilisateurs Windows 7 doivent installer la[mise à jour pour Universal Runtime C dans Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) pour le complément de réunion Teams afin de l’utiliser.
- Vérifiez que l’utilisateur dispose d’une stratégie de mise à niveau équipes permettant de planifier des réunions dans Teams. Pour plus d’informations, consultez la rubrique [mise à niveau de Skype entreprise vers teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
- Vérifiez que l’utilisateur dispose d’une stratégie de réunion teams qui autorise le complément Outlook. Pour plus d’informations, voir [gérer les stratégies de réunion dans teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) .
- Assurez-vous que l’utilisateur a installé le client de bureau Teams. Le complément de la réunion ne sera pas installé uniquement lors de l’utilisation du client Web Teams.
- Vérifiez que l’utilisateur dispose de l’installation d’Outlook 2013 ou version ultérieure.
- Assurez-vous que l’utilisateur est autorisé à exécuter regsvr32.exe.
- Vérifiez que toutes les mises à jour disponibles pour le client de bureau Outlook ont été appliquées.
- Procédez comme suit :
  - Redémarrez le client de bureau Teams.
  - Déconnectez-vous, puis reconnectez-vous pour le client de bureau Teams.
  - Fermez le client Outlook pour ordinateur de bureau. (Assurez-vous qu’Outlook n’est pas exécuté en mode administrateur.)

Si le complément n’apparaît toujours pas, assurez-vous qu’il n’est pas désactivé dans Outlook.

- Dans Outlook, sélectionnez **fichier** , puis **options**.
- Dans la boîte de dialogue **options Outlook** , sélectionnez l’onglet **compléments** .
- Vérifier que le **complément réunion de Microsoft teams pour Microsoft Office** figure dans la liste compléments d' **applications actifs**
- Si le complément réunion teams figure dans la liste compléments d' **applications désactivés** , sélectionnez **compléments COM** dans **gérer** , puis sélectionnez **atteindre...**
- Activez la case à cocher en regard de Microsoft **teams Meeting pour Microsoft Office**.
- Dans toutes les boîtes de dialogue, sélectionnez **OK** , puis redémarrez Outlook.

Pour obtenir des instructions générales sur la gestion des compléments, voir [afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Si le complément n’apparaît toujours pas, procédez comme suit pour vérifier les paramètres du Registre.

> [!NOTE]
> La modification incorrecte du registre pourrait endommager sérieusement votre système. Avant d’apporter des modifications au registre, il est recommandé de sauvegarder toutes les données importantes de votre ordinateur.
- Lancer RegEdit.exe
- Accédez à HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins
- Vérifiez que TeamsAddin. FastConnect existe.
- Dans TeamsAddin. FastConnect, vérifiez qu’il existe une valeur LoadBehavior et qu’elle a la valeur 3.
  - Si LoadBehavior a une valeur différente de 3, remplacez-la par 3 et redémarrez Outlook.

### <a name="delegate-scheduling-does-not-work"></a>La planification du délégué ne fonctionne pas

Si votre administrateur a configuré Microsoft Exchange pour [contrôler l’accès à Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un délégué ne pourra pas planifier une réunion Teams au nom du responsable. La solution pour cette configuration est en cours de développement et sera publiée ultérieurement. Pour contourner ce problème, votre administrateur peut ajouter la chaîne suivante à la liste verte d’EWS : «*SchedulingService*». 


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)