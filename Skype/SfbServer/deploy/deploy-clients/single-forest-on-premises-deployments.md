---
title: Déploiements locaux à forêt unique de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêt unique.
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120323"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Déploiements locaux à forêt unique de Skype Room System
 
Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêt unique.
  
Cette section fournit une vue d’ensemble des étapes de mise en service du compte Skype Room System sur Exchange Server et Skype Entreprise Server hébergé dans un déploiement local à forêt unique.
  
## <a name="single-forest-on-premises-deployments"></a>Déploiements sur site d’une forêt unique

Si vous avez déjà un compte de boîte aux lettres de ressources pour la salle de conférence, vous pouvez l’utiliser. Dans le cas contraire, vous devrez en créer un. Vous pouvez utiliser Exchange Management Shell (PowerShell) ou console de gestion Exchange pour créer un compte de boîte aux lettres de ressources. Nous vous recommandons d’utiliser une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la re-créer) pour Skype Room System. Assurez-vous de la back up mailbox data before deleting, puis exportez-les vers la boîte aux lettres re-créée à l’aide du client Outlook (pour plus d’informations, voir Export or back up messages, calendar, tasks, and contacts). Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir Connecter ou [restaurer une boîte aux lettres supprimée.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Pour utiliser un compte de boîte aux lettres de ressources existant (par exemple, LRS-01), suivez les étapes ci-dessous :
  
1. Exécutez la commande PowerShell de gestion Exchange suivante :
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Si vous envisagez de créer une boîte aux lettres, exécutez la commande suivante pour une organisation Exchange sur site à forêt unique :
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   L’exemple ci-dessus crée un compte d’utilisateur activé dans Active Directory et une boîte aux lettres de salle pour une salle de conférence dans une organisation Exchange sur site. Le paramètre RoomMailboxPassword spécifie le mot de passe du compte d'utilisateur.
    
3. Configurez le compte pour résoudre automatiquement les conflits en acceptant/rejetant les réunions. Les comptes de salle de conférence équipés du système Skype Room dans Exchange peuvent être gérés par des personnes, mais notez que tant que la personne n’accepte pas une réunion, elle n’apparaîtra pas sur le calendrier de l’écran d’accueil de Skype Room System.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Pour obtenir un ensemble complet de commandes disponibles, voir Set-CalendarProcessing.
    
   Pour rappeler aux organisateurs de la réunion de faire de la réunion une réunion Skype Entreprise en ligne dans Outlook, exécutez la commande suivante pour configurer une mailTip pour le nouveau compte : 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilisez les commandes suivantes pour configurer des chaînes localisées. Si votre organisation l’exige, vous pouvez également ajouter des traductions personnalisées : 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facultatif : configurez un texte d’acceptation de réunion qui fournit aux utilisateurs des informations sur la salle de réunion Skype Entreprise et ce à quoi ils doivent s’attendre lorsqu’ils prévoient et rejoignent des réunions. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Vérifier le compte de boîte aux lettres de ressources dans Active Directory

Le compte de boîte aux lettres de salle de conférence créé par Exchange à l’étape 1 ci-dessus peut être un objet utilisateur désactivé dans Active Directory. Skype Room System ne peut pas se connecter ou s’authentifier à l’aide de l’authentification Kerberos/NTLM si le compte est désactivé dans Active Directory. Le client Skype Room System doit être en mesure de s’authentifier auprès des services web Exchange pour récupérer les paramètres de calendrier et doit également être en mesure d’envoyer des messages électroniques avec le contenu du tableau blanc. 
  
Par conséquent, si le compte est désactivé, vous devez activer ce compte dans Active Directory en faisant ce qui suit : 
  
1. Dans Active Directory, exécutez la commande suivante pour activer la connexion au compte : 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   L’exécution de cette commande vous invite à entrer le mot de passe actuel, puis à entrer à nouveau le mot de passe à deux reprises pour confirmation.
    
2. Une fois le mot de passe définie, exécutez la commande suivante pour activer le compte : 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Activation des comptes Skype Room System pour Skype Entreprise

Cette section fournit une vue d’ensemble des étapes nécessaires pour activer Skype Entreprise pour votre compte de salle de conférence, qui sera configuré sur Skype Room System. 
  
Après avoir créé un compte de boîte aux lettres de ressources pour les salles de conférence, utilisez Skype Entreprise Server Management Shell pour activer les comptes Skype Room System pour les services Skype Entreprise.
  
> [!NOTE]
> La procédure suivante suppose que vous avez activé le compte Skype Room System dans Active Directory. 
  
1. Exécutez la commande suivante pour activer le compte Skype Room System sur un pool Skype Entreprise Server :
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Facultatif : autorisez ce compte à effectuer et à recevoir des appels téléphoniques PSTN en activant le compte pour Voix Entreprise. Voix Entreprise n’est pas nécessaire pour Skype Room System, mais si vous ne l’activez pas pour Voix Entreprise, le client Skype Room System ne sera pas en mesure de fournir la fonctionnalité de numérotation PSTN :
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous activez Voix Entreprise pour le compte de salle de conférence Skype Room System, veillez à configurer une stratégie de voix restreinte adaptée à votre organisation. Si la salle de réunion Skype Entreprise est une ressource disponible publiquement, tout le monde peut l’utiliser pour participer à une réunion, qu’elle soit programmée ou ad hoc. Après avoir rejoint une réunion, la personne peut composer n’importe quel numéro. Dans Skype Entreprise Server, la fonctionnalité d’appel sortant des conférences utilise la stratégie de voix de l’utilisateur, dans ce cas, le compte Skype Room System utilisé pour participer à la réunion. Dans les versions antérieures de Lync Server, la stratégie de voix de l’organisateur est utilisée. Par conséquent, si un utilisateur d’une version antérieure de Lync Server programme une salle de réunion et invite le compte de salle Skype Room System, toute personne peut utiliser la salle de réunion Skype Entreprise pour participer à la réunion et composer n’importe quel numéro de téléphone national/régional ou international, à condition que l’organisateur soit autorisé à composer ces numéros. 
