---
title: Règle de version du client
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
ms.openlocfilehash: 8f2e969b2724ed1239f7531bd4be03552be9039b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19991500"
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
|Lync Web App, Office Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition Platform  <br/> |CPE  <br/> |
|Unified Communications Platform  <br/> |UCCP  <br/> |
|Participant Lync 2010  <br/> |AOC  <br/> |
|Complément Live Meeting  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client Real-time Communications  <br/> |RTC  <br/> |
|Lync 2010 pour iPad  <br/> |iPadLync  <br/> |
|Lync 2010 pour iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 pour Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 pour Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 pour Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |
   
- **Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants, ou utiliser des caractères génériques pour indiquer le numéro de version du client.
    
  - **Version principale** Spécifie le numéro qui correspond à la version principale du client.
    
  - **Version secondaire** Spécifie le numéro qui correspond à la version mineure du client.
    
  - **Créer** Spécifie le numéro de version correspondant à la version principale et secondaire du client.
    
  - **Mise à jour** Spécifie le numéro qui correspond à la version mise à jour du client.
    
- **Opération de comparaison** Vous pouvez spécifier l’opération de correspondance pour la version de client que vous avez spécifié dans les étapes précédentes. Les opérations suivantes sont disponibles :
    
  - **Identique à**
    
  - **Différent de**
    
  - **Antérieur à**
    
  - **Antérieur ou simultané**
    
  - **Postérieur à**
    
  - **Postérieur ou simultané**
    
- **Action** Vous pouvez spécifier l’action à effectuer lorsque les critères ci-dessus sont remplies. Les actions suivantes sont disponibles :
    
  - **Autoriser** Autorise le client à se connecter.
    
  - **Autoriser et mettre à niveau** Autorise le client à se connecter et de recevoir des mises à jour de Service de mise à jour de Windows Server ou Microsoft Update. Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionnée.
    
    > [!NOTE]
    > Sélectionnez cette action entraîne une notification à afficher les prochaine fois que les utilisateurs se connectent à Skype pour les entreprises. La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées pour le Service de mise à jour de Windows Server ou Microsoft Update. Pour éviter toute confusion, vous devez choisir cette action uniquement une fois que les mises à jour sont disponibles. 
  
  - **Autoriser avec une URL** Autorise le client à se connecter et affiche un message sur l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.
    
  - **Bloc** Empêche le client de se connecter.
    
  - **Blocage et mise à niveau** Empêche le client de se connecter et autorise le client à recevoir des mises à jour de Service de mise à jour de Windows Server ou Microsoft Update. Cette action est disponible uniquement lorsque l’agent utilisateur **OC** est sélectionnée.
    
  - **Bloquer avec une URL** : empêche le client de se connecter et affiche un message à l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.
    
Pour plus d’informations sur l’interopérabilité entre les clients et les versions du client, voir [Interopérabilité des clients](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modifier l’Action par défaut pour les Clients pas explicitement pris en charge ou restreints](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation des opérations.

