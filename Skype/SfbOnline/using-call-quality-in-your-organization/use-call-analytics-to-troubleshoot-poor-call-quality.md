---
title: "Qualité des appels Analytique d’appeler utiliser pour résoudre les problèmes de mauvaise Skype pour entreprise"
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
description: "Analytique d’appeler plus d’informations sur les périphériques, les réseaux et connectivité permet de résoudre les problèmes utilisateur Skype pour les réunions et les appels de l’entreprise."
ms.openlocfilehash: cbb728c14c58393a5ec71cc538ad958ba58fb947
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>Qualité des appels Analytique d’appeler utiliser pour résoudre les problèmes de mauvaise Skype pour entreprise

Appel Analytique vous aide à résoudre les problèmes de connexion ou d’appel Skype pour les entreprises. Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité pour les appels et les réunions de chaque utilisateur de votre Skype pour le compte de l’entreprise. Si la génération, du site et client informations ont été ajoutées pour appeler Analytique, elle s’affiche également pour chaque appel et la session. Les informations disponibles via l’appel d’Analytique peuvent vous aider à déterminer pourquoi un utilisateur avait un appel médiocre ou expérience de la réunion. 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Résoudre les problèmes de qualité d’appel à l’aide d’appeler l’Analytique

Le niveau d’autorisation qui vous sont assigné détermine le type d’informations que vous avez accès à en appeler un Analytique :
  
- **Skype pour l’administration de l’entreprise**: vous avez accès à toutes les informations dans Analytique d’appel et le Skype pour le centre d’administration de l’entreprise.
    
- **Agent de support technique avec les autorisations de niveau 1**: affiche un ensemble limité de données Analytique d’appeler. Vous pouvez résoudre des appels, mais vous allez remettre les problèmes liés aux réunions d’un agent de niveau 2. Vous n’avez pas accès au reste de la Skype pour le centre d’administration de l’entreprise.
    
- **Agent de support technique avec les autorisations de niveau 2**: vous voir toutes les données disponibles dans l’appel d’Analytique et peut aider à résoudre les problèmes avec les appels et les réunions. Vous n’avez pas accès au reste de la Skype pour le centre d’administration de l’entreprise.
    
Consultez votre Skype pour l’administration de l’entreprise, si vous avez besoin d’aide avec les autorisations.
  
 **Analytique d’appeler ouvert comme un agent de support technique de niveau 1 ou niveau 2**
  
1. Accédez au centre d’administration Office 365 et vous connecter en utilisant votre compte de travail ou l’école. Dans votre navigateur web passez à *https://adminportal.services.skypeforbusiness.com*.
    
2. **Recherche d’utilisateur**, commencez à taper une adresse sip ou nom de l’utilisateur dont vous souhaitez résoudre les problèmes et puis sélectionnez l’utilisateur dans la liste les appels.
    
    ![Capture d’écran de la zone de recherche de l’utilisateur d’appeler l’Analytique dans le Skype pour Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Dans l' **historique des appels**, sélectionnez l’appel ou la réunion que vous souhaitez dépanner.
    
    ![Capture d’écran montre la page de l’historique des appels pour un utilisateur avec des informations telles que les informations de contact de l’utilisateur, un résumé de la qualité de 7 jours et l’activité pour les réunions et les appels et une vue d’ensemble des dates et des heures, les destinataires et qualité audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Sélectionnez l’onglet **Avancé** , puis recherchez des éléments jaunes et rouges qui indiquent des problèmes de connexion ou de qualité médiocre d’appel.
    
    Dans les détails de la session pour chaque appel ou d’une réunion, des problèmes mineurs s’affichent en jaune. (Par exemple, dans l’écran suivant, les valeurs sont en jaune pour variation moyenne, variation de Max et les taux de perte de paquet moyenne.) Si un élément est jaune, elle est en dehors de la plage normale et il contribue au problème, mais il n’est probablement pas la cause principale du problème. Si quelque chose est rouge, il s’agit d’un problème important, et il est probable que la cause principale de la qualité médiocre d’appel pour cette session. 
    
    ![Capture d’écran montre l’onglet Avancé de l’historique des appels de l’utilisateur avec la section réseau entrant de développé pour afficher que les données de la variation moyenne, max variation et taux de perte de paquet moyenne sont affichées dans une couleur jaune, ce qui signifie qu’ils sont des problèmes mineurs.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
Dans de rares cas, la qualité de données d’expérience n’est pas reçue pour les sessions audio. Cela est souvent dû par la suppression de l’appel et la connexion avec le client termine. Lorsque cela se produit, la session est « non disponible ».
  
Pour les sessions audio qui n’ont pas la qualité de données d’expérience (QoE), le tableau suivant décrit les principaux problèmes qui relèvent d’une session en tant que « médiocre ».
  
|**Problème**|**Zone**|**Description**|
|:-----|:-----|:-----|
|Appelez le programme d’installation  <br/> |Session  <br/> |Le code d’erreur Ms-diag 20 à 29 indique l’échec de la configuration de l’appel. L’utilisateur n’a pas pu joindre l’appel ou la réunion.  <br/> |
|Réseau audio classées appel médiocre  <br/> |Session  <br/> |Problèmes de qualité de réseau ont été rencontrées dans les domaines de gigue, perte de paquets, de dégradation NMOS, RTT, ou masquées de rapport. Pour plus d’informations sur les conditions utilisées pour classifier les appels médiocres, consultez ce [blog Microsoft valider](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Périphérique ne fonctionne ne pas  <br/> |DISPOSITIF  <br/> | Un périphérique ne fonctionne pas correctement. Périphérique ne fonctionne ne pas ratios est les suivantes : <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## <a name="related-topics"></a>Rubriques connexes
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?](difference-between-call-analytics-and-call-quality-dashboard.md)

## <a name="feedback"></a>Commentaires ?
Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).