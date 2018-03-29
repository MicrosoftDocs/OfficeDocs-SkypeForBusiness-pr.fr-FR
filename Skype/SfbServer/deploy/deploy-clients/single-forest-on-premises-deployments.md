---
title: Déploiements locaux d’une forêt Skype Room System unique
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
ms.openlocfilehash: b998c0b1e139951297eca8a963536dd59dcd4b39
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Déploiements locaux d’une forêt Skype Room System unique
 
Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
  
Cette section fournit une vue d’ensemble des étapes de mise en service le compte système local de Skype sur Exchange Server et Skype pour Business Server hébergée dans un déploiement sur site de forêt unique.
  
## <a name="single-forest-on-premises-deployments"></a>Déploiements locaux dans une forêt unique

Si vous disposez déjà d’un compte de boîte aux lettres de ressources pour la salle de conférence, vous pouvez l’utiliser. Dans le cas contraire, vous devrez en créer un nouveau. Vous pouvez utiliser Exchange Management Shell (PowerShell) ou Exchange Management Console pour créer un nouveau compte de boîte aux lettres de ressources. Nous recommandons d’utiliser un nouveau (supprimer l’ancienne boîte aux lettres et les recréer) boîte aux lettres de ressources pour le système de salle de Skype. Veillez à sauvegarder les données de la boîte aux lettres avant de la supprimer, puis exporter-les dans la boîte aux lettres recréée, à l’aide du client Outlook (voir Exporter ou enregistrer des messages, calendriers, tâches et contacts pour plus d’informations). Pour restaurer les réunions perdues lors de la suppression de la boîte aux lettres, voir [se connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx). 
  
Pour utiliser un compte de boîte aux lettres de ressources (par exemple, LRS-01) suivez les étapes ci-dessous :
  
1. Exécutez la commande PowerShell Exchange Management suivante :
    
  ```
  Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

2. Si vous prévoyez de créer une nouvelle boîte aux lettres, exécutez la commande suivante pour une organisation Exchange locale à forêt unique :
    
  ```
  New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

  Dans l’exemple ci-dessus, on crée un compte d’utilisateur activé dans Active Directory et une boîte aux lettres pour salle de conférence dans une organisation Exchange locale. Le paramètre RoomMailboxPassword spécifie le mot de passe du compte d’utilisateur.
    
3. Configurez le compte pour résoudre automatiquement les conflits en acceptant/rejetant des réunions. Skype équipé d’un système de salle salle dans Exchange, les comptes peuvent être gérés par des personnes, mais notez que jusqu'à ce que l’utilisateur accepte une réunion n’apparaîtra pas dans le calendrier d’écran d’accueil du système de salle de Skype.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Pour un ensemble complet des commandes disponibles, reportez-vous à Set-CalendarProcessing.
    
   Pour rappeler les organisateurs de la réunion pour rendre la réunion un Skype en ligne pour une réunion d’affaires dans Outlook, exécutez la commande suivante pour configurer un MailTip pour le nouveau compte : 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilisez les commandes suivantes pour configurer des chaînes localisées. Si cela est requis par votre organisation, vous pouvez également ajouter des traductions personnalisées : 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facultatif : Configuration texte d’acceptation qui fournit aux utilisateurs des informations sur Skype pour salle de réunion commerciale et à quoi s’attendre lorsqu’ils planifier et joindre la réunion réunions. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Consulter un compte de boîte aux lettres de ressources dans Active Directory

Le compte de boîte aux lettres de salle de conférence créé par Exchange à l’étape 1 ci-dessus peut être un objet utilisateur désactivé dans Active Directory. Système de salle de Skype ne peut pas se connecter ou s’authentifier à l’aide de l’authentification Kerberos/NTLM si le compte est désactivé dans Active Directory. Le client Skype espace système doit être en mesure de s’authentifier auprès des Services Web Exchange pour récupérer les paramètres de calendrier et doit également être en mesure d’envoyer du courrier électronique avec le contenu du tableau blanc. 
  
Par conséquent, si le compte est désactivé, vous devez l’activer dans Active Directory en procédant comme suit : 
  
1. Dans Active Directory, exécutez la commande suivante pour activer la connexion au compte : 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   Lors de l’exécution de cette commande, vous serez invité à saisir le mot de passe actuel, puis à saisir le mot de passe deux autres fois pour confirmation.
    
2. Une fois le mot de passe configuré, exécutez la commande suivante pour activer le compte : 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>L’activation du système de salle de Skype comptes pour Skype pour entreprise

Cette section fournit une vue d’ensemble des étapes requises pour activer Skype pour entreprise pour votre compte de salle de conférence, qui est configuré sur le système local de Skype. 
  
Après avoir créé un compte de boîte aux lettres de ressources pour les salles de conférence, utilisez Skype pour Business Server Management Shell pour activer les comptes système local de Skype pour Skype pour les services.
  
> [!NOTE]
> La procédure suivante suppose que vous avez activé le compte système local de Skype dans Active Directory. 
  
1. Exécutez la commande suivante pour activer le compte système local de Skype sur un Skype pour un pool de serveurs d’entreprise :
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Facultatif : Autoriser ce compte pour effectuer et de recevoir les appels RTPC en activant le compte de Voix Entreprise. Voix Entreprise n’est pas requise pour le système de salle de Skype, mais si vous ne l’activez pas pour Voix Entreprise, le client Skype espace système ne sera pas en mesure de fournir la fonctionnalité de numérotation PSTN :
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true

   ```

> [!NOTE]
> Si vous activez la Voix Entreprise pour le compte de salle de conférence Skype espace système, assurez-vous de configurer une stratégie de voix restreint adapté à votre organisation. Si le Skype pour salle de réunion commerciale est une ressource publiquement disponible, tout le monde peut l’utiliser pour joindre une réunion, ad hoc ou planifiée. Après avoir rejoint une réunion, la personne peut appeler n’importe quel numéro. Dans Skype pour Business Server, les appels sortants à partir de la fonctionnalité de conférences utilise la stratégie de la voix de l’utilisateur, dans ce cas, le compte système local de Skype permet de joindre la réunion. Dans les versions précédentes de Lync Server, la stratégie vocale de l’organisateur est utilisée. Par conséquent, si un utilisateur d’une version antérieure de Lync Server planifie une salle de réunion et invite le compte d’espace de système de salle de Skype, tout le monde permet le Skype pour salle de réunion commerciale pour joindre la réunion et peut appeler n’importe quel téléphone nationales/régionales ou international nombre, tant que l’organisateur n’est autorisé à composer ces numéros. 
  

