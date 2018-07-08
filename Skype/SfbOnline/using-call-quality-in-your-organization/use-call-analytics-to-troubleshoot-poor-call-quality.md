---
title: Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Utilisez Analytique appeler plus d’informations sur les appareils, réseaux et la connectivité à résoudre les problèmes utilisateur Skype pour les réunions et les appels professionnels.
ms.openlocfilehash: 3610aff4b82f7d1fb0016a8934ec0feb640cc8ff
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211004"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels

Appel Analytique vous aide à résoudre des problèmes de connexion ou appel avec Microsoft Teams et Skype pour les entreprises. Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité pour les appels et les réunions de chaque utilisateur dans votre compte Office 365. Si la création, de sites et des clients informations ont été ajoutées à appeler Analytique, elle s’affichera également pour chaque appel et de la session. Informations disponibles par le biais d’Analytique appel peuvent vous aider à comprendre pourquoi un utilisateur avait un appel médiocre ou l’expérience de la réunion. 
  
**Appel Analytique est maintenant disponible dans le Microsoft Teams et Skype entreprise centre d’administration.** Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **Historique des appels** . Vous pouvez procéder par la recherche sur la page de profil utilisateur par une recherche de l’utilisateur du tableau de bord ou la recherche de l’utilisateur des **utilisateurs** dans le volet de navigation gauche.

> [!IMPORTANT]
> Autorisations de l’agent de support technique et le téléchargement de topologie réseau seront disponibles dans le nouveau portail d’administration dans les mois à venir. En attendant, vous pouvez continuer à utiliser https://adminportal.services.skypeforbusiness.com pour l’accès de support technique de niveau 1 et niveau 2.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Résoudre les problèmes de qualité appel à l’aide d’Analytique d’appel

Le niveau d’autorisation attribué détermine le type d’informations que vous avez accès à dans Analytique des appels :
  
- **Skype pour administrateur d’entreprise**: vous avez accès à toutes les informations dans Analytique des appels et le Skype pour le centre d’administration Business.
    
- **Agent de support technique disposant des autorisations de niveau 1**: vous voyez un ensemble limité de données d’appel d’Analytique. Vous pouvez résoudre les appels, mais vous allez remettre les problèmes liés aux réunions pour un agent de niveau 2. Vous n’avez pas accès au reste du Skype pour le centre d’administration Business.
    
- **Agent de support technique disposant des autorisations de niveau 2**: vous voir toutes les données disponibles dans Analytique appeler et peuvent aider à résoudre des problèmes avec les appels et les réunions. Vous n’avez pas accès au reste du Skype pour le centre d’administration Business.
    
Consultez votre Skype pour administrateur d’entreprise si vous avez besoin d’aide avec des autorisations.
  
 **Ouvrez Analytique appeler comme un agent de support technique de niveau 1 ou de niveau 2**
  
1. Accédez au centre d’administration Office 365 et connectez-vous à l’aide de votre compte professionnel ou de l’école. Accédez à dans votre navigateur web *https://adminportal.services.skypeforbusiness.com*.
    
2. Dans la **Recherche d’un utilisateur**, commencez à taper l’adresse sip ou nom de l’utilisateur dont les appels pour résoudre les problèmes, puis sélectionnez l’utilisateur dans la liste.
    
    ![Capture d’écran de la zone de recherche d’un utilisateur d’appeler les Analytique dans le Skype entreprise centre d’administration.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Dans l' **historique des appels**, sélectionnez l’appel ou la réunion que vous souhaitez dépanner.
    
    ![Capture d’écran montre la page Historique des appels pour un utilisateur avec des informations telles que les informations de contact de l’utilisateur, un résumé de l’activité pour les réunions et les appels et la qualité de 7 jours et une vue d’ensemble des dates et heures, les destinataires et la qualité audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Sélectionnez l’onglet **Avancé** , puis recherchez des éléments jaunes et rouges qui indiquent des problèmes de connexion ou de la qualité des appels médiocres.
    
    Dans les détails de session pour chaque appel ou des réunions, des problèmes mineurs s’affichent en jaune. (Par exemple, dans la capture d’écran suivante, les valeurs sont en jaune pour gigue moyenne et taux de pertes de paquets moyenne gigue Max.) Si un élément est jaune, il est en dehors de la plage normale et il peut contribuer au problème, mais il est peu de chances d’être la cause principale du problème. Si un élément est rouge, il s’agit d’un problème majeur, et il est probable que la cause principale de la qualité des appels médiocres pour cette session. 
    
    ![Capture d’écran montre l’onglet Avancé de l’historique d’appel d’un utilisateur avec la section réseau entrant développée pour afficher que les données de gigue moyenne, max gigue et taux de pertes de paquets moyenne sont affichées dans une couleur jaune, ce qui signifie qu’ils sont des problèmes mineurs.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
Dans les cas rares, qualité de l’expérience de données n’est pas reçue pour les sessions audio. Souvent, cela est dû à la suppression de l’appel et la connexion avec le client abandonnée. Lorsque cela se produit, l’évaluation de la session est « non disponible ».
  
Pour les sessions audio qui n’ont pas la qualité des données de l’expérience (QoE), le tableau suivant décrit les principaux problèmes associées à une session en tant que « faible ».
  
|**Problème**|**Zone**|**Description**|
|:-----|:-----|:-----|
|Configuration des appels  <br/> |Session  <br/> |Le code d’erreur Ms-diagnostic 20 à 29 indique l’échec de la configuration de l’appel. L’utilisateur n’a pas pu participer à l’appel ou la réunion.  <br/> |
|Réseau audio classés d’appels médiocres  <br/> |Session  <br/> |Problèmes de qualité réseau se sont produites dans des domaines tels que la perte de paquets, gigue, dégradation NMOS, durée aller-retour, ou réparation du rapport. Pour plus d’informations sur les conditions d’utilisation pour classer les appels médiocres, consultez le [billet de blog de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Périphérique ne fonctionne ne pas  <br/> |APPAREIL  <br/> | Un périphérique ne fonctionne pas correctement. Périphérique ne fonctionne ne pas ratios est les suivants : <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Rubriques connexes
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Appel Analytique et tableau de bord de qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
