---
title: Déploiements locaux d’une forêt Skype Room System unique
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
ms.openlocfilehash: 47cbd43709dda35d728bf8324362bec075dc74b1
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768697"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Déploiements locaux d’une forêt Skype Room System unique
 
Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
  
Cette section fournit une vue d’ensemble des étapes de configuration du compte système de salle Skype sur Exchange Server et de Skype entreprise Server hébergées dans un seul déploiement local de la forêt.
  
## <a name="single-forest-on-premises-deployments"></a>Déploiements locaux dans une forêt unique

Si vous disposez déjà d’un compte de boîte aux lettres de ressources pour la salle de conférence, vous pouvez l’utiliser. Dans le cas contraire, vous devrez en créer un nouveau. Vous pouvez utiliser Exchange Management Shell (PowerShell) ou Exchange Management Console pour créer un nouveau compte de boîte aux lettres de ressources. Nous vous recommandons d’utiliser une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la recréation) pour le système de salle Skype. Veillez à sauvegarder les données de la boîte aux lettres avant de la supprimer, puis exporter-les dans la boîte aux lettres recréée, à l’aide du client Outlook (voir Exporter ou enregistrer des messages, calendriers, tâches et contacts pour plus d’informations). Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir [connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Pour utiliser un compte de boîte aux lettres de ressources (par exemple, LRS-01) suivez les étapes ci-dessous :
  
1. Exécutez la commande PowerShell Exchange Management suivante :
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Si vous prévoyez de créer une nouvelle boîte aux lettres, exécutez la commande suivante pour une organisation Exchange locale à forêt unique :
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Dans l’exemple ci-dessus, on crée un compte d’utilisateur activé dans Active Directory et une boîte aux lettres pour salle de conférence dans une organisation Exchange locale. Le paramètre RoomMailboxPassword spécifie le mot de passe du compte d’utilisateur.
    
3. Configurez le compte pour résoudre automatiquement les conflits en acceptant/rejetant des réunions. Les comptes de salle de conférence dotés du système de salle Skype dans Exchange peuvent être gérés par des personnes, mais notez qu’une réunion ne s’affiche pas dans le calendrier de l’écran d’accueil de Skype Room.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Pour un ensemble complet des commandes disponibles, reportez-vous à Set-CalendarProcessing.
    
   Pour rappeler aux organisateurs de la réunion de mettre en ligne une réunion Skype entreprise en ligne dans Outlook, exécutez la commande suivante pour configurer un alerte pour le nouveau compte : 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilisez les commandes suivantes pour configurer des chaînes localisées. Si cela est requis par votre organisation, vous pouvez également ajouter des traductions personnalisées : 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facultatif : configurer le texte d’acceptation d’une réunion qui fournit aux utilisateurs des informations sur la salle de réunion Skype entreprise et ce à quoi vous pouvez vous attendre lorsqu’ils organisent et joignez des réunions. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Consulter un compte de boîte aux lettres de ressources dans Active Directory

Le compte de boîte aux lettres de salle de conférence créé par Exchange à l’étape 1 ci-dessus peut être un objet utilisateur désactivé dans Active Directory. Le système de salle Skype ne peut pas se connecter ou s’authentifier à l’aide de l’authentification Kerberos/NTLM si le compte est désactivé dans Active Directory. Le client système de salle Skype doit être en mesure de s’authentifier auprès des services Web Exchange pour récupérer les paramètres du calendrier et doit également être en mesure d’envoyer des courriers électroniques avec le contenu du tableau blanc. 
  
Par conséquent, si le compte est désactivé, vous devez l’activer dans Active Directory en procédant comme suit : 
  
1. Dans Active Directory, exécutez la commande suivante pour activer la connexion au compte : 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Lors de l’exécution de cette commande, vous serez invité à saisir le mot de passe actuel, puis à saisir le mot de passe deux autres fois pour confirmation.
    
2. Une fois le mot de passe configuré, exécutez la commande suivante pour activer le compte : 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Activation de la gestion des comptes de bureau Skype pour Skype entreprise

Cette section fournit une vue d’ensemble des étapes requises pour activer Skype entreprise pour votre compte de salle de conférence, qui est configurée dans le système de salle Skype. 
  
Une fois que vous avez créé un compte de boîte aux lettres de ressources pour les salles de conférence, vous pouvez utiliser Skype entreprise Server Management Shell pour activer les comptes système de salle Skype pour les services Skype entreprise.
  
> [!NOTE]
> La procédure suivante suppose que vous avez activé le compte système de salle Skype dans Active Directory. 
  
1. Exécutez la commande suivante pour activer le compte système de salle Skype dans un pool de serveurs Skype entreprise :
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice. La voix entreprise n’est pas requise pour les systèmes de salle Skype, mais si vous ne l’activez pas pour Enterprise Voice, le client système de salle Skype ne sera pas en mesure de fournir les fonctionnalités de numérotation RTC :
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous activez Enterprise Voice pour le compte de la salle de conférence du système de salle Skype, assurez-vous de configurer une stratégie vocale restreinte adaptée à votre organisation. Si la salle de réunion Skype entreprise est une ressource publiquement disponible, n’importe qui peut l’utiliser pour rejoindre une réunion, planifiée ou ponctuelle. Après avoir rejoint une réunion, la personne peut appeler n’importe quel numéro. Dans Skype entreprise Server, la fonction de conférence rendez-vous de conférences utilise la politique vocale de l’utilisateur, dans le cas présent, le compte système de salle Skype utilisé pour rejoindre la réunion. Dans les versions précédentes de Lync Server, la stratégie vocale de l’organisateur est utilisée. Par conséquent, si un utilisateur d’une version antérieure de Lync Server planifie une salle de réunion et invite le compte de la salle de réunion Skype, tout le monde peut utiliser la salle de réunion Skype entreprise pour rejoindre la réunion et peut composer le numéro de téléphone national/régional ou international, à condition que l’organisateur puisse composer le numéro. 
  

