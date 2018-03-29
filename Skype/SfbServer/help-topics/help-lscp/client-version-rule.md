---
title: Règle de version du client
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
ms.openlocfilehash: 88316487ccd6f061127f92a762ac2d8c17b6a9c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-rule"></a>Règle de version du client
 
Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :
  
- Ajout de nouvelles règles à une stratégie de version de client
    
- Modification des règles composant une stratégie de version de client existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Agent utilisateur** Vous pouvez sélectionner un type de client à partir de la liste. Le tableau suivant définit les codes d’agent utilisateur.
    
|**Nom du client**|**Agent utilisateur**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync téléphone Office Communicator Phone Edition  <br/> |OCPhone  <br/> |
|Communicator Phone Edition Platform  <br/> |CPE  <br/> |
|Unified Communications Platform  <br/> |UCCP  <br/> |
|Participant Lync 2010  <br/> |AOC  <br/> |
|Complément Live Meeting  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client Real-time Communications  <br/> |RTC  <br/> |
|Lync 2010 pour iPad  <br/> |iPadLync  <br/> |
|Lync 2010 pour l’iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 pour Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 pour Ericsson  <br/> |NokiaLync  <br/> |
|Lync 2010 pour Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |
   
- **Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants, ou utiliser des caractères génériques pour indiquer le numéro de version du client.
    
  - **Version principale** Spécifie le numéro qui correspond à la principale version du client.
    
  - **Version secondaire** Spécifie le numéro qui correspond à la version mineure du client.
    
  - **Générer** Spécifie le numéro de version qui correspond à la version principale et secondaire du client.
    
  - **Mise à jour** Spécifie le numéro qui correspond à la version mise à jour du client.
    
- **Opération de comparaison** Vous pouvez spécifier l’opération de correspondance pour la version de client que vous avez spécifié dans les étapes précédentes. Les opérations suivantes sont disponibles :
    
  - **Identique à**
    
  - **Différent de**
    
  - **Antérieur à**
    
  - **Antérieur ou simultané**
    
  - **Postérieur à**
    
  - **Postérieur ou simultané**
    
- **Action** Vous pouvez spécifier l’action à exécuter lorsque les critères dans les étapes précédentes sont remplies. Les actions suivantes sont disponibles :
    
  - **Autoriser** Permet au client d’ouvrir une session.
    
  - **Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour de Service de mise à jour de Windows Server ou de Microsoft Update. Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionné.
    
    > [!NOTE]
    > La sélection de cette action, une notification s’affiche les prochaine fois qu’ils vous connecter sur Skype pour les entreprises. La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été lancés vers le Service de mise à jour de Windows Server ou de Microsoft Update. Pour éviter toute confusion, vous devez choisir cette action uniquement après que les mises à jour sont disponibles. 
  
  - **Autoriser l’URL** Permet au client d’ouvrir une session et affiche un message permettant de télécharger une autre version de client. Vous devez spécifier l’URL dans le champ **URL**.
    
  - **Bloc** Le client empêche l’ouverture de session.
    
  - **Bloc et mise à niveau** Empêche l’ouverture de session du client et permet au client de recevoir des mises à jour du Service de mise à jour de Windows Server ou de Microsoft Update. Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionné.
    
  - **Bloquer avec une URL** : empêche le client de se connecter et affiche un message à l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.
    
Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, consultez [Interopérabilité du Client dans Microsoft Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de la version client, reportez-vous à la section [Modifier l’Action par défaut pour les Clients pas explicitement prises en charge ou restreint](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation sur les opérations.

