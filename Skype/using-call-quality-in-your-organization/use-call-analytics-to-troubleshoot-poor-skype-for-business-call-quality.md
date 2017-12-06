---
title: "Qualité des appels utilisation appeler Analytique pour résoudre un problème Skype pour les entreprises"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# Qualité des appels utilisation appeler Analytique pour résoudre un problème Skype pour les entreprises

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](66945036-ae87-4c08-a0bb-984e50d6b009.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/66945036-ae87-4c08-a0bb-984e50d6b009). 
  
Appel Analytique vous aide à résoudre les problèmes de connexion ou appel avec Skype Entreprise. Appel Analytique affiche des informations détaillées sur les appareils, réseaux et connectivité pour les appels et les réunions de chaque utilisateur dans votre compte Skype Entreprise. Si la génération, du site et du client informations ont été ajoutées à appeler Analytique, elle s'affiche également pour chaque appel et la session. Informations disponibles via un appel Analytique peuvent vous aider à identifier pourquoi un utilisateur a un appel mauvaise ou expérience de la réunion.
  
> [!NOTE]
> Appel Analytique est en cours d'aperçu. Texte et les images ci-dessus peut ne pas correspondent votre expérience. 
  
## Résoudre les problèmes de qualité d'appel à l'aide d'appeler Analytique

Le niveau d'autorisation attribué détermine le type d'informations que vous avez accès dans appeler Analytique :
  
- **Skype pour l'administrateur d'entreprise**: vous avez accès à toutes les informations dans appeler Analytique et dans le centre d'administration Skype Entreprise.
    
- **Agent de support technique avec des autorisations de niveau 1**: vous voyez un jeu de données dans appeler Analytique limité. Vous pouvez résoudre les appels, mais vous devez remettre les problèmes liés aux réunions à un agent de niveau 2. Vous n'avez pas l'accès au reste du centre d'administration Skype Entreprise.
    
- **Agent de support technique avec des autorisations de niveau 2**: vous voir toutes les données disponibles dans appeler Analytique et peut vous aider à résoudre des problèmes d'appels et réunions. Vous n'avez pas l'accès au reste du centre d'administration Skype Entreprise.
    
Consultez votre administrateur Skype Entreprise si vous avez besoin d'aide avec des autorisations.
  
 **Ouvrez Analytique appeler tant qu'agent de support technique de niveau 1 ou de niveau 2**
  
1. Accédez à [https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com)et puis connectez-vous avec votre nom d'utilisateur et mot de passe.
    
2. Dans la **Recherche de l'utilisateur**, commencez à taper le nom ou sip l'adresse de l'utilisateur dont vous souhaitez résoudre les problèmes, puis sélectionnez l'utilisateur dans la liste les appels.
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. Dans l' **historique des appels**, sélectionnez l'appel ou une réunion que vous souhaitez résoudre les problèmes.
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Sélectionnez l'onglet **Avancé** et consultez ensuite les éléments jaunes et rouges qui indiquent des problèmes de connexion ou de qualité médiocre appel.
    
    Dans les détails de la session pour chaque appel ou une réunion, problèmes secondaires s'affichent en jaune. (Par exemple, dans l'écran suivant, les valeurs sont en jaune pour gigue moyenne, gigue Max et les taux de perte de paquets moyenne.) Si un élément est jaune, il est en dehors de la plage normale et il peut contribuer au problème, mais il n'est probablement pas la cause du problème principale. Si un élément est rouge, il s'agit d'un problème important, et il est probablement la principale raison de la qualité des appels mauvaise pour cette session.
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
Rarement, qualité des données de l'expérience n'est pas reçue pour les sessions audio. Souvent cela est dû à la suppression de l'appel et la connexion avec le client de fin. Dans ce cas, le niveau de session est « non disponible ».
  
Pour les sessions audio qui n'ont pas la qualité des données de l'expérience (QoE), le tableau suivant décrit les principaux problèmes éligibles une session en tant que « médiocre ».
  
|**Problème**|**Domaine**|**Description**|
|:-----|:-----|:-----|
|Appeler le programme d'installation  <br/> |Session  <br/> |Le code d'erreur Ms-diagnostic 20 à 29 indique la configuration des appels a échoué. L'utilisateur n'a pas pu participer à l'appel ou une réunion.  <br/> |
|Réseau audio classées mauvaise appel  <br/> |Session  <br/> |Problèmes de qualité de réseau se sont produites dans des zones tels que la perte de paquets, gigue, dégradation NMOS, RTT, ou masquées ratio. Pour plus d'informations sur les conditions d'utilisation pour classer les appels médiocres, voir ce [billet de blog Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Périphérique ne fonctionne ne pas  <br/> |Appareil  <br/> | Un périphérique ne fonctionne pas correctement. Périphérique ne fonctionne ne pas ratios est les suivantes : <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Configurer Skype pour les entreprises appeler Analytique](set-up-skype-for-business-call-analytics.md)

