---
title: Déploiements locaux d’une forêt Skype Room System unique
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
ms.openlocfilehash: 5fd9ab3f2a2e581f2f1675bea0f663b95cfa3eb5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214995"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Déploiements locaux d’une forêt Skype Room System unique
 
Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
  
Cette section fournit une vue d’ensemble des étapes de mise en service le compte de système de salle Skype sur Exchange Server et Skype pour Business Server hébergé dans un déploiement local de forêt unique.
  
## <a name="single-forest-on-premises-deployments"></a>Déploiements locaux dans une forêt unique

Si vous disposez déjà d’un compte de boîte aux lettres de ressources pour la salle de conférence, vous pouvez l’utiliser. Dans le cas contraire, vous devrez en créer un nouveau. Vous pouvez utiliser Exchange Management Shell (PowerShell) ou Exchange Management Console pour créer un nouveau compte de boîte aux lettres de ressources. Nous vous recommandons d’utiliser une nouvelle (ancienne boîte aux lettres de supprimer et recréer) boîte aux lettres de ressources de système de salle Skype. Veillez à sauvegarder les données de la boîte aux lettres avant de la supprimer, puis exporter-les dans la boîte aux lettres recréée, à l’aide du client Outlook (voir Exporter ou enregistrer des messages, calendriers, tâches et contacts pour plus d’informations). Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir [Connect ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
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
    
3. Configurez le compte pour résoudre automatiquement les conflits en acceptant/rejetant des réunions. Skype équipé d’un système de salle salle comptes dans Exchange peuvent être gérés par des personnes, mais notez que jusqu'à ce que la personne accepte une réunion n’apparaîtra pas dans le calendrier d’écran d’accueil Skype salle système.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Pour un ensemble complet des commandes disponibles, reportez-vous à Set-CalendarProcessing.
    
   Pour rappeler les organisateurs de réunion pour rendre la réunion un Skype en ligne pour la réunion d’entreprise dans Outlook, exécutez la commande suivante pour configurer une info-courrier pour le nouveau compte : 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilisez les commandes suivantes pour configurer des chaînes localisées. Si cela est requis par votre organisation, vous pouvez également ajouter des traductions personnalisées : 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facultatif : Configurer texte acceptation qui permet aux utilisateurs d’informations sur Skype pour salle de réunion métiers et à quoi s’attendre lorsqu’ils planifier et participer à la réunion réunions. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Consulter un compte de boîte aux lettres de ressources dans Active Directory

Le compte de boîte aux lettres de salle de conférence créé par Exchange à l’étape 1 ci-dessus peut être un objet utilisateur désactivé dans Active Directory. Système de salle Skype ne peut pas se connecter ou s’authentifier en utilisant l’authentification Kerberos/NTLM si le compte est désactivé dans Active Directory. Le client Skype salle système doit être en mesure de s’authentifier auprès d’Exchange Web Services pour récupérer les paramètres du calendrier et doit également être en mesure d’envoyer un message électronique avec le contenu du tableau blanc. 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Activation système Skype salle des comptes pour Skype pour les entreprises

Cette section fournit une vue d’ensemble des étapes requises pour activer Skype pour les entreprises pour votre compte de salle de conférence, qui vont être configuré sur le système de salle Skype. 
  
Après avoir créé un compte de boîte aux lettres de ressources pour les salles de conférence, utilisez Skype pour Business Server Management Shell pour activer des comptes système de salle Skype pour Skype pour les services.
  
> [!NOTE]
> La procédure suivante suppose que vous avez activé le compte de système de salle Skype dans Active Directory. 
  
1. Exécutez la commande suivante pour activer le compte de système de salle Skype sur un Skype pour le pool de serveurs d’entreprise :
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice. Enterprise Voice n’est pas nécessaire pour le système de salle Skype, mais si vous n’activez pas pour Enterprise Voice, le client Skype salle système sera en mesure de fournir des fonctionnalités de numérotation PSTN :
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous activez Enterprise Voice pour le compte de salle de conférence Skype salle système, veillez à configurer une stratégie de voix restreint approprié pour votre organisation. Si le Skype pour salle de réunion Business est une ressource accessible au public, tout le monde peut l’utiliser pour participer à une réunion planifiée ou ad hoc. Après avoir rejoint une réunion, la personne peut appeler n’importe quel numéro. Dans Skype pour Business Server, les appels sortants à partir de la fonctionnalité de conférences utilise la stratégie de voix de l’utilisateur, dans ce cas, le compte système local de Skype utilisé pour participer à la réunion. Dans les versions précédentes de Lync Server, la stratégie vocale de l’organisateur est utilisée. Par conséquent, si un utilisateur d’une version antérieure de Lync Server planifie une salle de réunion et invite le compte de la salle Skype salle système, tout le monde peut utiliser le Skype pour salle de réunion Business pour joindre la réunion et peut appeler n’importe quel téléphone nationales/régionales ou international nombre, tant que l’organisateur est autorisé à appeler ces numéros. 
  

