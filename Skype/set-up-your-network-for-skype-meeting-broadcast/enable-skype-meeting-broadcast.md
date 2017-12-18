---
title: "Activer une diffusion de réunion Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "Les membres de votre organisation peuvent utiliser Diffusion de réunion Skype, vous devez l'activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne savez pas Windows PowerShell, faites appel à un partenaire Microsoft d'effectuer cette étape pour vous."
---

# Activer une diffusion de réunion Skype

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Les membres de votre organisation peuvent utiliser Diffusion de réunion Skype, vous devez l'activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne savez pas Windows PowerShell, faites appel à un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d'effectuer cette étape pour vous.
  
> [!CAUTION]
> Diffusion de réunion Skype est désactivée par défaut, car la distribution du contenu multimédia d'une réunion diffusion utilise réseau de remise de contenu (CDN de Microsoft Azure) pour atteindre très haute échelle pour prendre en charge des milliers de diffusion d'une personne qui regarde. Le contenu du média segmenté passant par le CDN est chiffré, puis le cache CDN a une durée de vie limitée. En outre, le composant Azure CDN peut se réunir pas encore tous les éléments des Clauses de modèle de l'Union européenne découlant de la Directive de Protection des données de l'Union européenne. En activant cette fonctionnalité, vous acceptez cet avis. 
  
## Activer la diffusion de réunion Skype au moyen du Centre d'administration de Skype Entreprise

1. Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. Dans le Centre d'administration Office 365, accédez à **Centres d'administration** > **Skype Entreprise**.
    
3. Dans la **Skype centre d'administration entreprise**, accédez à **des réunions en ligne** > **diffuser des réunions** et puis sélectionnez **Activer la diffusion de réunion Skype**.
    
## Activer la diffusion de réunion Skype avec PowerShell

1. Vérifiez que vous exécutez la version 3.0 ou supérieure de Windows PowerShell.
    
1. Pour vérifier que vous exécutez la version 3.0 ou supérieure : cliquez sur **Démarrer** > **Windows PowerShell**.
    
2. Vérifiez la version en tapant  _Get-Host_ fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
2. Dans le **Menu Démarrer**, cliquez sur **Windows PowerShell**.
    
3. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
  Import-PSSession $O365Session
  ```

4. Confirmez votre configuration Diffusion de réunion Skype actuelle en exécutant :
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Vérifiez que le paramètre  _EnableBroadcastMeeting_ est défini sur `False`.
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Activez Diffusion de réunion Skype pour votre organisation en exécutant :
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Vous pouvez vérifier que le paramètre est activé en exécutant  `Get-CsBroadcastMeetingConfiguration` à nouveau.
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Une fois la modification effectuée, sa prise en compte sur le portail Diffusion de réunion Skype peut prendre jusqu'à une heure. 
  
6. Vos utilisateurs peuvent contenir diffuser des réunions avec d'autres utilisateurs dans votre entreprise. Pour afficher les réponses en main, pointez sur leur [Qu'est-ce qu'une diffusion de réunion Skype ?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## Configurer votre réseau pour la diffusion de réunions à des participants externes

Si vous avez un pare-feu, et que vous souhaitez héberger des diffusions pour des personnes extérieures à votre entreprise (qui n'est pas une entreprise fédérée), vous devez configurer votre réseau avec les instructions suivantes : [Configurer votre réseau pour la Diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.
  
Pour ignorer cette étape et les ajouter à la place d'une autre société à votre fédération, consultez [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

