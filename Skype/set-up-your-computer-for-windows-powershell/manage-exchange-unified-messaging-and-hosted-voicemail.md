---
title: "Gérer la messagerie unifiée Exchange et hébergé message vocal dans Skype entreprise Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# Gérer la messagerie unifiée Exchange et hébergé message vocal dans Skype entreprise Online

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Vous pouvez gérer Exchange messagerie vocale hébergé dans Skype Entreprise Online en utilisant un jeu d'applets de commande et messagerie unifiée.
  
## Gérer la messagerie unifiée Exchange et hébergé la messagerie vocale

Les applets de commande suivantes peuvent servir à gérer Exchange messagerie unifiée (MU) et les stratégies de messagerie vocale hébergé :
  
|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [Nouvelle CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [Supprimer CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [Jeu de CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Crée et gère les objets de contact utilisées pour les services de standard automatique et accès abonné, Exchange messagerie unifiée est un service hébergé.  <br/> Skype Entreprise Online fonctionne avec Exchange messagerie unifiée pour fournir plusieurs fonctionnalités liés à la voix, y compris le standard automatique et accès abonné. Standard automatique fournit un moyen pour les appels automatiquement une réponse et routés vers la personne concernée. Accès abonné permet aux utilisateurs de se connecter à Exchange messagerie unifiée et récupérer courrier électronique, des messages vocaux, des contacts et des informations de calendrier.  <br/> Lorsque Exchange MU est fourni sous forme d'un service hébergé, objets contact utilisés pour le standard automatique et accès abonné les services doivent être créés à l'aide de Microsoft PowerShell. Ces objets sont créées et gérées en utilisant les applets de commande **CsExUmContact**. <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [Accorder le CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Gère les stratégies de messagerie vocale hébergé utilisées dans l'organisation. Les stratégies de messagerie vocale hébergé spécifient les appels sans réponse comment sont routés vers le service de messagerie unifiée Exchange. Ces stratégies affectent uniquement les utilisateurs qui ont été activés pour Exchange MU hébergé messagerie vocale.  <br/> Pour vérifier si un utilisateur est activé pour la messagerie vocale hébergé, exécutez une commande semblable à ce qui suit à l'invite PowerShell.  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

