---
title: Utiliser l’Analyse des appels pour résoudre les problèmes de qualité des appels
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
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: Analytique appeler plus d’informations sur les appareils, les réseaux et connectivité permet de résoudre les problèmes d’utilisateur avec Microsoft Teams et Skype pour les réunions et les appels professionnels.
ms.openlocfilehash: e437401f759e92aa13c0d6680ef30eabd20ffc56
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543182"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Utiliser l’Analyse des appels pour résoudre les problèmes de qualité des appels

Appel Analytique vous permet de résoudre les problèmes de connexion ou appel avec Microsoft Teams et Skype pour les entreprises. Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité pour les appels et les réunions de chaque utilisateur dans votre compte Office 365. Si la création, de sites et des clients informations ont été ajoutées à appeler Analytique, elle s’affichera également pour chaque appel et de la session. Informations disponibles par le biais d’Analytique appel peuvent vous aider à comprendre pourquoi un utilisateur avait un appel médiocre ou l’expérience de la réunion. 
  
## <a name="call-analytics-permissions"></a>Autorisations d’appel Analytique

En tant que l’administrateur, vous obtenez un accès total à toutes les fonctionnalités d’appel d’Analytique. En outre, vous pouvez assigner des rôles d’Azure Active Directory au personnel de support. Attribuer le rôle de spécialiste de prise en charge de communications équipes aux utilisateurs qui doivent avoir une vue limitée d’Analytique d’appel. Attribuer le rôle de technicien de prise en charge de communications équipes aux utilisateurs qui ont besoin d’accéder à toutes les fonctionnalités d’appel d’Analytique. Les deux niveaux d’autorisation empêche l’accès au reste du centre d’administration Microsoft Teams.

Gérer les spécialistes du support de communications des problèmes fondamentaux de la qualité des appels. Ils n’examiner les problèmes liés à des réunions. Au lieu de cela, ils collecter des informations connexes et puis réaffecter à un ingénieur du support technique communications. Ingénieurs du support technique communications affichent les informations dans les journaux d’appels détaillées a masqué communications spécialistes du support. Le tableau suivant donne une vue d’ensemble des informations disponibles à communications prise en charge des spécialistes et communications ingénieurs lorsqu’ils utilisent Analytique d’appel.

Le niveau d’autorisation attribué détermine le type d’informations que vous avez accès à dans Analytique des appels :
  
- **Les équipes de service de communications administrateur ou équipes**: vous avez accès à toutes les informations dans Analytique d’appel et dans le centre d’administration Microsoft Teams.
    
- **Spécialiste du support communications équipes**: vous voyez un ensemble limité de données d’appel d’Analytique. Vous pouvez résoudre les appels, mais vous allez remettre des problèmes avec les réunions à un ingénieur du support technique équipes communications. Vous n’avez pas accès au reste du centre d’administration Microsoft Teams.
    
- **Prend en charge les équipes communications ingénieur**: vous voir toutes les données disponibles dans Analytique appeler et peuvent aider à résoudre des problèmes avec les appels et les réunions. Vous n’avez pas accès au reste du centre d’administration Microsoft Teams.
    
> [!NOTE]
> Le rôle de spécialiste de prise en charge des communications est équivalent au support de niveau 1 et le rôle ingénieur de prise en charge des communications est équivalent au support de niveau 2.

Pour plus d’informations sur les rôles d’administration équipes, voir [utiliser les équipes Microsoft rôles d’administrateur pour gérer les équipes](using-admin-roles.md). Pour une comparaison détaillée de la prise en charge des communications équipes spécialiste et communications équipes prennent en charge les rôles ingénieur, voir [Set up Analytique d’appel](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Voir les équipes Skype pour administrateur d’entreprise si vous avez besoin d’aide avec des autorisations.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Résoudre les problèmes de qualité appel à l’aide d’Analytique d’appel

1. Connectez-vous avec votre prise en charge des communications équipes ou les informations d’identification d’administration d’équipes.

2. Dans votre navigateur web, accédez à *https://admin.teams.microsoft.com*.
    
3. Dans le **tableau de bord**, de la **Recherche d’un utilisateur**, commencez à taper le nom ou adresse sip de l’utilisateur dont les appels pour résoudre les problèmes ou sélectionnez **Afficher les utilisateurs** de voir une liste d’utilisateurs.
    
    ![Capture d’écran de la zone de recherche d’un utilisateur de l’appel d’Analytique dans le centre d’administration Microsoft Teams.](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Sélectionnez l’utilisateur dans la liste.

5. Sélectionnez **historique des appels**, puis sélectionnez l’appel ou la réunion que vous souhaitez dépanner.
    
    ![Capture d’écran montre la page Historique des appels pour un utilisateur.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Sélectionnez l’onglet **Avancé** , puis recherchez des éléments jaunes et rouges qui indiquent des problèmes de connexion ou de la qualité des appels médiocres.
    
    Dans les détails de session pour chaque appel ou des réunions, des problèmes mineurs s’affichent en jaune. (Par exemple, dans la capture d’écran suivante, les valeurs sont en jaune pour gigue moyenne et taux de pertes de paquets moyenne gigue Max.) Si un élément est jaune, il est en dehors de la plage normale et il peut contribuer au problème, mais il est peu de chances d’être la cause principale du problème. Si un élément est rouge, il s’agit d’un problème majeur, et il est probable que la cause principale de la qualité des appels médiocres pour cette session. 
    
    ![Capture d’écran montre l’onglet Avancé de l’historique d’appel d’un utilisateur ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
Dans les cas rares, qualité de l’expérience de données n’est pas reçue pour les sessions audio. Souvent, cela est dû à la suppression de l’appel et la connexion avec le client abandonnée. Lorsque cela se produit, l’évaluation de la session n’est **pas disponible**.
  
Pour les sessions audio qui n’ont pas la qualité des données de l’expérience (QoE), le tableau suivant décrit les principaux problèmes associées à une session en tant que **médiocre**.
  
|**Problème**|**Domaine**|**Description**|
|:-----|:-----|:-----|
|Configuration des appels  <br/> |Session  <br/> |Le code d’erreur Ms-diagnostic 20 à 29 indique l’échec de la configuration de l’appel. L’utilisateur n’a pas pu participer à l’appel ou la réunion.  <br/> |
|Réseau audio classés d’appels médiocres  <br/> |Session  <br/> |Problèmes de qualité réseau (tels que la perte de paquets, l’instabilité, dégradation NMOS, durée aller-retour ou taux masqué) se sont produites. Pour plus d’informations sur les conditions d’utilisation pour classer les appels médiocres, consultez le [billet de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Périphérique ne fonctionne ne pas  <br/> |APPAREIL  <br/> | Un périphérique ne fonctionne pas correctement. Périphérique ne fonctionne ne pas ratios est les suivants : <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Rubriques connexes
[Configurer Analyse des appels](set-up-call-analytics.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
