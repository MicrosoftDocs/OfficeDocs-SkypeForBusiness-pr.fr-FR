---
title: Utiliser l’analyse des appels pour résoudre les problèmes de mauvaise qualité d’appel
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Utilisez les détails d’une analyse d’appel par utilisateur sur les appareils, les réseaux et la connectivité pour résoudre les problèmes liés aux utilisateurs de Microsoft Teams.
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085320"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Utiliser l’analyse des appels pour résoudre les problèmes de mauvaise qualité d’appel

Cet article explique comment utiliser les analyses des appels pour résoudre les problèmes liés aux appels et à la qualité de réunion Microsoft teams pour des utilisateurs individuels si vous êtes un administrateur teams ou un spécialiste ou un technicien du support technique des communications.


  
## <a name="call-analytics-permissions"></a>Autorisations d’analyse des appels

Cet article part du principe que vous avez déjà configuré l’analyse des appels. Si ce n’est pas le cas, voir [configurer l’analyse des appels pour teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Présentation de l’analyse des appels

L’analyse des appels fournit des informations détaillées sur les appels et les réunions d’équipes pour chaque utilisateur de votre compte 365 Office. Il inclut des informations sur les périphériques, les réseaux, la connectivité et la qualité des appels (tout ce qui peut être un facteur de faible qualité des appels ou des réunions). Si vous téléchargez des informations de création, de site et de client, ces informations sont également affichées pour chaque appel et réunion. Utiliser les fonctions d’analyse des appels pour vous aider à déterminer la raison pour laquelle l’utilisateur a rencontré un problème ou un appel d’une réunion.

L’analyse des appels vous montre chaque partie d’un appel ou d’une réunion, par exemple, d’un participant à un second participant. En analysant ces informations, un administrateur teams peut isoler les zones de problèmes et identifier la cause initiale d’une mauvaise qualité.
   
En tant qu’administrateur Teams, vous bénéficiez d’un accès complet à toutes les données d’analyse des appels pour chaque utilisateur. De plus, vous pouvez attribuer des rôles Azure Active Directory à l’équipe de support technique. Pour en savoir plus sur ces rôles, voir [accorder une autorisation au support technique et au personnel du support technique](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). Ne manquez pas [ce qu’est le rôle de chaque équipe](#what-does-each-teams-support-role-do) .

## <a name="where-to-find-per-user-call-analytics"></a>Où trouver les données d’analyse des appels par utilisateur

Pour afficher toutes les informations d’appel et les données d’un utilisateur, accédez au [Centre d’administration teams](https://admin.teams.microsoft.com). Sous **utilisateurs**, sélectionnez un utilisateur, puis ouvrez l’onglet **historique des appels** sur la page de profil de l’utilisateur. Vous trouverez ci-après les appels et les réunions de cet utilisateur au cours des 30 derniers jours.

![Capture d’écran de toutes les données utilisateur d’analyse](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Pour obtenir des informations supplémentaires sur une session donnée, notamment les statistiques détaillées sur le média et la mise en réseau, cliquez sur une session pour afficher les détails.

![Capture d’écran des données de session utilisateur d’analyse des appels](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>Quels sont les rôles pris en charge par chaque équipe ?

Le **spécialiste de la prise en charge des communications de Microsoft teams** (support de niveau 1) gère les problèmes de qualité des appels de base. Ils ne recherchent pas les problèmes liés aux réunions. En revanche, il recueille des informations connexes, puis le transmet à un ingénieur du support des communications. 

L' **ingénieur du support des communications de teams** (support de niveau 2) affiche des informations dans les journaux d’appels détaillés qui sont masqués par le spécialiste du support des communications de l’équipe. Le tableau ci-dessous répertorie les informations disponibles pour le rôle de support communication de chaque équipe.

Le tableau suivant indique les informations fournies par l’utilisateur pour chaque rôle de support des communications.

|**Activité**|**Concernant**|Ce que voit le **spécialiste** du support des communications|Ce que le **technicien** du support technique peut voir|
|:-----|:-----|:-----|:-----|
|**Appels** <br/> |Nom de l’appelant  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent a effectué la recherche.  <br/> |Nom d’utilisateur.  <br/> |
||Nom du destinataire  <br/> |Affiche en tant qu’utilisateur interne ou utilisateur externe.  <br/> |Nom du destinataire.  <br/> |
||Numéro de téléphone de l'appelant  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |
||Numéro de téléphone du destinataire  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |Le numéro de téléphone complet sauf les trois derniers Par exemple, 15552823 * * *.  <br/> |
||Détails de l' **appel**  >  Onglet **avancé** <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tels que les noms des appareils, l’adresse IP, le mappage de sous-réseau, etc.  <br/> |
||Détails de l' **appel**  >  **Options avancées**  >  Onglet **Déboguer** <br/> |Informations non affichées.  <br/> |Tous les détails indiqués, tels que les suffixes DNS et SSID.  <br/> |
|**Réunions** <br/> |Noms des participants  <br/> |Uniquement le nom de l’utilisateur pour lequel l’agent a effectué la recherche. Autres participants identifiés comme utilisateurs internes ou utilisateurs externes.  <br/> |Tous les noms affichés.  <br/> |
||Nombre de participants  <br/> |Nombre de participants.  <br/> |Nombre de participants.  <br/> |
||Détails de la session  <br/> |Détails de la session accompagnés d’exceptions. Uniquement le nom de l’utilisateur pour lequel la recherche de l’agent est affichée. Autres participants identifiés comme utilisateurs internes ou utilisateurs externes. Les trois derniers chiffres du numéro de téléphone brouillés par des symboles d’astérisque.  <br/> |Détails de la session affichés. Les noms d’utilisateur et les détails de la session apparaissent. Les trois derniers chiffres du numéro de téléphone brouillés par des symboles d’astérisque.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>Résoudre les problèmes de qualité des appels utilisateur 

1. Ouvrez le centre d’administration Teams ( https://admin.teams.microsoft.com) et connectez-vous avec les informations d’identification de votre équipe ou des informations d’identification d’administrateur.

2. Dans le **tableau de bord**, dans recherche de l' **utilisateur**, commencez à taper le nom ou l’adresse SIP de l’utilisateur dont vous souhaitez résoudre les appels ou sélectionnez **afficher les utilisateurs** pour afficher une liste d’utilisateurs.

3. Sélectionnez l’utilisateur dans la liste.

4. Sélectionnez **historique des appels**, puis sélectionnez l’appel ou la réunion que vous voulez résoudre.
    
5. Sélectionnez l’onglet **avancé** , puis recherchez des éléments jaunes ou rouges qui indiquent une mauvaise qualité des appels ou des problèmes de connexion.
    
    Dans les détails de la session pour chaque appel ou réunion, des problèmes mineurs apparaissent en jaune. Si un élément est orange, il se trouve en dehors de la plage normale et peut contribuer à la cause du problème, mais il est improbable qu’il n’y en ait pas. S’il s’agit d’un problème rouge, il s’agit d’un problème important et il est probable que la mauvaise qualité d’appel soit médiocre pour cette session. 
      
Dans de rares cas, les données de qualité d’expérimentation ne sont pas reçues pour les sessions audio. C’est souvent dû au fait d’un appel déposé ou à la fin de la connexion avec le client. Lorsque c’est le cas, l’évaluation de session n’est **pas disponible**.
  
Le tableau suivant répertorie les problèmes liés à la qualité des sessions audio qui présentent une session de qualité **médiocre**.
  
|**Problème**|**Domaine**|**Description**|
|:-----|:-----|:-----|
|Configurer l’appel  <br/> |Session  <br/> |Le code d’erreur MS-diag 20-29 indique que la configuration de l’appel a échoué. L’utilisateur n’a pas pu rejoindre l’appel ou la réunion.  <br/> |
|Appel médiocre du réseau audio  <br/> |Session  <br/> |Des problèmes liés à la qualité du réseau (par exemple, perte de paquets, gigue, dégradation NMOS, RTT ou rapport masqué) ont été détectés.  <br/> |
|L’appareil ne fonctionne pas  <br/> |Device  <br/> | Un appareil ne fonctionne pas correctement. Taux de fonctionnement de l’appareil hors fonctionnement : <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   

## <a name="related-topics"></a>Voir aussi

[Configurer l’analyse des appels par utilisateur](set-up-call-analytics.md)



  
 
