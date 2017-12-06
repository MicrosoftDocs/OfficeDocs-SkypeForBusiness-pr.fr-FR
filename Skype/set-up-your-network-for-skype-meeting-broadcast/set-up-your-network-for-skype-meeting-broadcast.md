---
title: "Configurer votre réseau pour la Diffusion de réunion Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Configurer votre réseau pour la Diffusion de réunion Skype

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](dfa736b9-4920-4f48-b8c0-b5487ec6086f.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/dfa736b9-4920-4f48-b8c0-b5487ec6086f). 
  
Une fois que vous avez [Activer une diffusion de réunion Skype](enable-skype-meeting-broadcast.md) la Diffusion de réunion Skype, vous devez configurer votre réseau. Effectuez ceci si vous souhaitez organiser des webinaires ou d'autres diffusions pour des personnes externes à votre entreprise.
  
Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.
  
Pour ignorer cette étape et ajoutez à la place une autre société à votre fédération afin que vous pouvez les inviter à diffusion, suivez les étapes de [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## Étape 1 : Configurer les domaines autorisés

Utilisez l' **une** des méthodes suivantes pour configurer des domaines autorisés :
  
### 

 **Méthode 1 : Utiliser le centre d'administration Office 365**
  
1. Accédez au **Centre d'administration Office 365** et puis, dans le volet de navigation gauche, cliquez sur **paramètres** > **Services et compléments**, puis choisissez **Skype Entreprise**.
    
2. Dans la page **le partage externe** sous **exceptions de domaine**, sélectionnez **tous les domaines bloqués à l'exception** et entrez les domaines suivants, séparés par une virgule (,) :
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Cliquez sur **Enregistrer**.
    
### 

 **Méthode 2 : Utiliser Windows PowerShell**
  
- Dans le **Menu Démarrer**, avec le bouton droit de **Windows PowerShell**, puis cliquez sur **Exécuter en tant qu'administrateur**. Dans la fenêtre de **Windows PowerShell**, tapez chaque ligne, puis appuyez sur ENTRÉE.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## Étape 2 : Ajouter la diffusion de réunion Skype domaines, des URL et adresses IP adresses

La deuxième étape dans le processus de configuration s'applique à vous ajouter des domaines qui sont nécessaires, puis ajoutez les adresses IP et URL requis pour la diffusion de réunion Skype pour l'utiliser.
  
- **Ajoutez les points de terminaison domaine requis :**
    
    Pour utiliser Diffusion de réunion Skype, les points de terminaison suivants doivent être accessibles aux ordinateurs clients.
    
|
|
|**Ligne**|**Objectif**|**Source | Informations d'identification**|**Destination**|**ExpressRoute pour les communautés Office 365 BGP**|**Adresse CIDR**|**Port**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**Obligatoire :** points de terminaison Skype Entreprise. <br/> |reportez-vous à la section [Skype Entreprise Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) et assurez-vous que toutes les entrées intitulées « Obligatoire » sont accessibles. <br/> ||||
|2  <br/> |**Obligatoire : présentateur et participant**[Diffusion de réunion Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |ordinateur client/utilisateur connecté  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|oui  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**Obligatoire : présentateur et participant**[Diffusion de réunion Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |ordinateur client/utilisateur connecté  <br/> |
```
aka.ms
amp.azure.net

```

|non  <br/> |N/A  <br/> |TCP 443  <br/> |
|4  <br/> |**Obligatoire :**[ présentateur et participant Diffusion de réunion Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) (y compris CDN) <br/> |ordinateur client/utilisateur connecté  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|non  <br/> |N/A  <br/> |TCP 443  <br/> |
   
- **Ajouter la Skype requis pour le point de terminaison URL et adresses IP voir quels sont ceux qui sont requises**[ici](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides

Si vous avez une organisation Skype Entreprise Online et un déploiement local de Lync Server 2010, Microsoft Lync Server 2013 et Skype Entreprise Server 2015 et vos utilisateurs à la fois en ligne et en local, il existe d'autres étapes de configuration dont vous aurez besoin faire en outre ceux présentés ci-dessus pour activer votre organisation locale pour communiquer avec Skype Entreprise Online et permettre à tous les utilisateurs doivent pouvoir créer et rejoindre une Diffusion de réunion Skype. Pour savoir ce que sont ces exigences, voir [configurer votre déploiement local pour la diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## Rubriques connexes

[Activer une diffusion de réunion Skype](enable-skype-meeting-broadcast.md)
  
[URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

