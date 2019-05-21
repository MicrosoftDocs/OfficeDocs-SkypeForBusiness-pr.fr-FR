---
title: Déploiements locaux d’une forêt Skype Room System unique
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.
ms.openlocfilehash: 0eae077662b050ed2accb5869f1423e0a201a0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287952"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="6c872-103">Déploiements locaux d’une forêt Skype Room System unique</span><span class="sxs-lookup"><span data-stu-id="6c872-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="6c872-104">Consultez cette rubrique pour découvrir comment déployer Skype Room System dans la forêt unique d’un environnement local.</span><span class="sxs-lookup"><span data-stu-id="6c872-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="6c872-105">Cette section fournit une vue d’ensemble des étapes de configuration du compte système de salle Skype sur Exchange Server et de Skype entreprise Server hébergées dans un seul déploiement local de la forêt.</span><span class="sxs-lookup"><span data-stu-id="6c872-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="6c872-106">Déploiements locaux dans une forêt unique</span><span class="sxs-lookup"><span data-stu-id="6c872-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="6c872-107">Si vous disposez déjà d’un compte de boîte aux lettres de ressources pour la salle de conférence, vous pouvez l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="6c872-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="6c872-108">Dans le cas contraire, vous devrez en créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="6c872-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="6c872-109">Vous pouvez utiliser Exchange Management Shell (PowerShell) ou Exchange Management Console pour créer un nouveau compte de boîte aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="6c872-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="6c872-110">Nous vous recommandons d’utiliser une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la recréation) pour le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="6c872-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="6c872-111">Veillez à sauvegarder les données de la boîte aux lettres avant de la supprimer, puis exporter-les dans la boîte aux lettres recréée, à l’aide du client Outlook (voir Exporter ou enregistrer des messages, calendriers, tâches et contacts pour plus d’informations).</span><span class="sxs-lookup"><span data-stu-id="6c872-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="6c872-112">Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir [connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6c872-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="6c872-113">Pour utiliser un compte de boîte aux lettres de ressources (par exemple, LRS-01) suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="6c872-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="6c872-114">Exécutez la commande PowerShell Exchange Management suivante :</span><span class="sxs-lookup"><span data-stu-id="6c872-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="6c872-115">Si vous prévoyez de créer une nouvelle boîte aux lettres, exécutez la commande suivante pour une organisation Exchange locale à forêt unique :</span><span class="sxs-lookup"><span data-stu-id="6c872-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="6c872-p102">Dans l’exemple ci-dessus, on crée un compte d’utilisateur activé dans Active Directory et une boîte aux lettres pour salle de conférence dans une organisation Exchange locale. Le paramètre RoomMailboxPassword spécifie le mot de passe du compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6c872-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="6c872-118">Configurez le compte pour résoudre automatiquement les conflits en acceptant/rejetant des réunions.</span><span class="sxs-lookup"><span data-stu-id="6c872-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="6c872-119">Les comptes de salle de conférence dotés du système de salle Skype dans Exchange peuvent être gérés par des personnes, mais notez qu’une réunion ne s’affiche pas dans le calendrier de l’écran d’accueil de Skype Room.</span><span class="sxs-lookup"><span data-stu-id="6c872-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="6c872-120">Pour un ensemble complet des commandes disponibles, reportez-vous à Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="6c872-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="6c872-121">Pour rappeler aux organisateurs de la réunion de mettre en ligne une réunion Skype entreprise en ligne dans Outlook, exécutez la commande suivante pour configurer un alerte pour le nouveau compte:</span><span class="sxs-lookup"><span data-stu-id="6c872-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="6c872-122">Utilisez les commandes suivantes pour configurer des chaînes localisées.</span><span class="sxs-lookup"><span data-stu-id="6c872-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="6c872-123">Si cela est requis par votre organisation, vous pouvez également ajouter des traductions personnalisées :</span><span class="sxs-lookup"><span data-stu-id="6c872-123">If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="6c872-124">Facultatif: configurer le texte d’acceptation d’une réunion qui fournit aux utilisateurs des informations sur la salle de réunion Skype entreprise et ce à quoi vous pouvez vous attendre lorsqu’ils organisent et joignez des réunions.</span><span class="sxs-lookup"><span data-stu-id="6c872-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="6c872-125">Consulter un compte de boîte aux lettres de ressources dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c872-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="6c872-126">Le compte de boîte aux lettres de salle de conférence créé par Exchange à l’étape 1 ci-dessus peut être un objet utilisateur désactivé dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c872-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="6c872-127">Le système de salle Skype ne peut pas se connecter ou s’authentifier à l’aide de l’authentification Kerberos/NTLM si le compte est désactivé dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c872-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="6c872-128">Le client système de salle Skype doit être en mesure de s’authentifier auprès des services Web Exchange pour récupérer les paramètres du calendrier et doit également être en mesure d’envoyer des courriers électroniques avec le contenu du tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="6c872-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="6c872-129">Par conséquent, si le compte est désactivé, vous devez l’activer dans Active Directory en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="6c872-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="6c872-130">Dans Active Directory, exécutez la commande suivante pour activer la connexion au compte :</span><span class="sxs-lookup"><span data-stu-id="6c872-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="6c872-131">Lors de l’exécution de cette commande, vous serez invité à saisir le mot de passe actuel, puis à saisir le mot de passe deux autres fois pour confirmation.</span><span class="sxs-lookup"><span data-stu-id="6c872-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="6c872-132">Une fois le mot de passe configuré, exécutez la commande suivante pour activer le compte :</span><span class="sxs-lookup"><span data-stu-id="6c872-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="6c872-133">Activation de la gestion des comptes de bureau Skype pour Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="6c872-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="6c872-134">Cette section fournit une vue d’ensemble des étapes requises pour activer Skype entreprise pour votre compte de salle de conférence, qui est configurée dans le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="6c872-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="6c872-135">Une fois que vous avez créé un compte de boîte aux lettres de ressources pour les salles de conférence, vous pouvez utiliser Skype entreprise Server Management Shell pour activer les comptes système de salle Skype pour les services Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6c872-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c872-136">La procédure suivante suppose que vous avez activé le compte système de salle Skype dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c872-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="6c872-137">Exécutez la commande suivante pour activer le compte système de salle Skype dans un pool de serveurs Skype entreprise:</span><span class="sxs-lookup"><span data-stu-id="6c872-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="6c872-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6c872-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="6c872-139">La voix entreprise n’est pas requise pour les systèmes de salle Skype, mais si vous ne l’activez pas pour Enterprise Voice, le client système de salle Skype ne sera pas en mesure de fournir les fonctionnalités de numérotation RTC:</span><span class="sxs-lookup"><span data-stu-id="6c872-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="6c872-140">Si vous activez Enterprise Voice pour le compte de la salle de conférence du système de salle Skype, assurez-vous de configurer une stratégie vocale restreinte adaptée à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6c872-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="6c872-141">Si la salle de réunion Skype entreprise est une ressource publiquement disponible, n’importe qui peut l’utiliser pour rejoindre une réunion, planifiée ou ponctuelle.</span><span class="sxs-lookup"><span data-stu-id="6c872-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="6c872-142">Après avoir rejoint une réunion, la personne peut appeler n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="6c872-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="6c872-143">Dans Skype entreprise Server, la fonction de conférence rendez-vous de conférences utilise la politique vocale de l’utilisateur, dans le cas présent, le compte système de salle Skype utilisé pour rejoindre la réunion.</span><span class="sxs-lookup"><span data-stu-id="6c872-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="6c872-144">Dans les versions précédentes de Lync Server, la stratégie vocale de l’organisateur est utilisée.</span><span class="sxs-lookup"><span data-stu-id="6c872-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="6c872-145">Par conséquent, si un utilisateur d’une version antérieure de Lync Server planifie une salle de réunion et invite le compte de la salle de réunion Skype, tout le monde peut utiliser la salle de réunion Skype entreprise pour accéder à la réunion et peut composer un numéro national/régional ou international. nombre, tant que l’organisateur peut composer le numéro.</span><span class="sxs-lookup"><span data-stu-id="6c872-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

