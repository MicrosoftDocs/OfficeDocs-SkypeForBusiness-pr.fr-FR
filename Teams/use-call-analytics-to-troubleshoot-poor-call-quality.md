---
title: Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Utilisez les détails d’analyse des appels sur les appareils, les réseaux et la connectivité pour résoudre les problèmes liés aux utilisateurs de Microsoft Teams, ainsi que les réunions et les appels Skype entreprise.
ms.openlocfilehash: 05af82a942d54e0f97f2be2b176091f19186cbf4
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749561"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels

L’analyse des appels vous permet de résoudre les problèmes liés aux appels ou à la connexion avec Microsoft teams et Skype entreprise. L’analyse des appels affiche des informations détaillées sur les périphériques, les réseaux et la connectivité pour les appels et les réunions de chaque utilisateur de votre compte 365 Office. Si des informations de construction, de site et de client ont été ajoutées à l’analyse des appels, celles-ci s’afficheront également pour chaque appel et chaque session. Les informations disponibles dans le cadre de la procédure d’analyse des appels peuvent vous aider à déterminer la raison pour laquelle l’utilisateur a rencontré des problèmes de connexion ou de réunion. 
  
## <a name="call-analytics-permissions"></a>Autorisations d’analyse des appels

En tant qu’administrateur, vous bénéficiez d’un accès complet à toutes les fonctionnalités d’analyse d’appel. De plus, vous pouvez attribuer des rôles Azure Active Directory à l’équipe de support technique. Affectez au rôle de spécialiste de la prise en charge des communications équipe aux utilisateurs qui doivent disposer d’un affichage limité de l’analyse des appels. Affectez au rôle de technicien de support communications de l’équipe aux utilisateurs qui ont besoin d’accéder à l’ensemble des fonctionnalités d’analyse des appels. Les deux niveaux d’autorisation empêchent l’accès au reste du centre d’administration Microsoft Teams.

Les spécialistes de la prise en charge des communications traitent des problèmes de qualité d’appel. Ils ne recherchent pas les problèmes liés aux réunions. En revanche, il recueille des informations connexes, puis le transmet à un ingénieur du support des communications. Les ingénieurs de support des communications voient les informations contenues dans les journaux d’appels détaillés des spécialistes du support des communications. Le tableau suivant fournit une vue d’ensemble des informations accessibles aux spécialistes de la prise en charge des communications et aux ingénieurs du support des communications lorsqu’ils utilisent la technique d’analyse des appels.

Le niveau d’autorisation qui vous a été attribué détermine le type d’informations auxquelles vous avez accès dans analyse des appels :
  
- Administrateur de **service teams ou administrateur des communications**: vous avez accès à toutes les informations de l’analyse des appels et au centre d’administration Microsoft Teams.
    
- **Spécialiste du support des communications teams**: un ensemble limité de données est affiché dans l’analyse des appels. Vous pouvez résoudre les problèmes liés aux appels, mais vous devez les résoudre à l’aide d’un ingénieur du support des communications de l’équipe. Vous n’avez pas accès au reste du centre d’administration Microsoft Teams.
    
- **Technicien du support technique des communications**: vous retrouvez toutes les données disponibles dans l’analyse des appels et vous pouvez aider à résoudre les problèmes liés aux appels et aux réunions. Vous n’avez pas accès au reste du centre d’administration Microsoft Teams.
    
> [!NOTE]
> Le rôle de spécialiste du support des communications est équivalent au support de niveau 1 et le rôle d’ingénieur de support des communications équivaut à la prise en charge de niveau 2.

Pour plus d’informations sur les rôles d’administrateur d’équipe, voir [utiliser les rôles d’administrateur Microsoft teams pour gérer teams](using-admin-roles.md). Pour obtenir une comparaison détaillée des rôles de technicien de support de communications d’équipes et de support des communications Teams, voir [configurer l’analyse des appels](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Pour plus d’informations sur les autorisations, voir les informations de l’administrateur de votre équipe et de Skype entreprise.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Résoudre les problèmes de qualité d’appel à l’aide de l’analyse des appels

1. Connectez-vous à l’aide des informations d’identification de votre équipe ou de votre administrateur d’équipe.

2. Dans votre navigateur Web, accédez *https://admin.teams.microsoft.com*à.
    
3. Dans le **tableau de bord**, dans recherche de l' **utilisateur**, commencez à taper le nom ou l’adresse SIP de l’utilisateur dont vous souhaitez résoudre les appels ou sélectionnez **afficher les utilisateurs** pour afficher une liste d’utilisateurs.
    
    ![Capture d’écran de la zone de recherche d’utilisateurs de l’analyse des appels](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Sélectionnez l’utilisateur dans la liste.

5. Sélectionnez **historique des appels**, puis sélectionnez l’appel ou la réunion que vous voulez résoudre.  Un maximum de 500 enregistrements seront renvoyés.
    
    ![Capture d’écran de la page historique des appels d’un utilisateur.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Sélectionnez l’onglet **avancé** , puis recherchez des éléments jaunes ou rouges qui indiquent une mauvaise qualité des appels ou des problèmes de connexion.
    
    Dans les détails de la session pour chaque appel ou réunion, des problèmes mineurs apparaissent en jaune. (Par exemple, dans la capture d’écran ci-dessous, les valeurs sont en jaune pour la gigue moyenne, le taux de scintillement maximal et le taux moyen de perte de paquets.) Si un élément est orange, il se trouve en dehors de la plage normale et peut contribuer à la cause du problème, mais il est improbable qu’il n’y en ait pas. S’il s’agit d’un problème rouge, il s’agit d’un problème important et il est probable que la mauvaise qualité d’appel soit médiocre pour cette session. 
    
    ![Capture d’écran de l’onglet avancé de l’historique des appels d’un utilisateur ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
Dans de rares cas, les données de qualité d’expérimentation ne sont pas reçues pour les sessions audio. C’est souvent dû au fait que l’appel est interrompu et qu’une connexion avec le client s’arrête. Lorsque c’est le cas, l’évaluation de session n’est **pas disponible**.
  
Le tableau suivant répertorie les problèmes liés à la qualité des sessions audio qui présentent une session de qualité **médiocre**.
  
|**Problème**|**Domaine**|**Description**|
|:-----|:-----|:-----|
|Configurer l’appel  <br/> |Session  <br/> |Le code d’erreur MS-diag 20-29 indique que la configuration de l’appel a échoué. L’utilisateur n’a pas pu rejoindre l’appel ou la réunion.  <br/> |
|Appel médiocre du réseau audio  <br/> |Session  <br/> |Des problèmes liés à la qualité du réseau (par exemple, perte de paquets, gigue, dégradation NMOS, RTT ou rapport masqué) ont été détectés. Pour plus d’informations sur les conditions utilisées pour classifier les appels médiocres, reportez-vous à ce [billet de blog Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|L’appareil ne fonctionne pas  <br/> |Device  <br/> | Un appareil ne fonctionne pas correctement. Taux de fonctionnement de l’appareil hors fonctionnement : <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   
## <a name="related-topics"></a>Voir aussi
[Configurer l’analyse des appels](set-up-call-analytics.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
