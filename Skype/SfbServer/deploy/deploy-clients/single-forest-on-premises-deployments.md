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
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820754"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="adafc-103">Déploiements locaux à forêt unique de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="adafc-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="adafc-104">Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêt unique.</span><span class="sxs-lookup"><span data-stu-id="adafc-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="adafc-105">Cette section fournit une vue d’ensemble des étapes de mise en service du compte Skype Room System sur Exchange Server et Skype Entreprise Server hébergé dans un déploiement local à forêt unique.</span><span class="sxs-lookup"><span data-stu-id="adafc-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="adafc-106">Déploiements sur site d’une forêt unique</span><span class="sxs-lookup"><span data-stu-id="adafc-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="adafc-107">Si vous avez déjà un compte de boîte aux lettres de ressources pour la salle de conférence, vous pouvez l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="adafc-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="adafc-108">Dans le cas contraire, vous devrez en créer un.</span><span class="sxs-lookup"><span data-stu-id="adafc-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="adafc-109">Vous pouvez utiliser Exchange Management Shell (PowerShell) ou console de gestion Exchange pour créer un compte de boîte aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="adafc-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="adafc-110">Nous vous recommandons d’utiliser une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la re-créer) pour Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="adafc-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="adafc-111">Assurez-vous de la back up mailbox data before deleting, puis exportez-les vers la boîte aux lettres re-créée à l’aide du client Outlook (pour plus d’informations, voir Export or back up messages, calendar, tasks, and contacts).</span><span class="sxs-lookup"><span data-stu-id="adafc-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="adafc-112">Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir Connecter ou [restaurer une boîte aux lettres supprimée.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="adafc-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="adafc-113">Pour utiliser un compte de boîte aux lettres de ressources existant (par exemple, LRS-01), suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="adafc-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="adafc-114">Exécutez la commande PowerShell de gestion Exchange suivante :</span><span class="sxs-lookup"><span data-stu-id="adafc-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="adafc-115">Si vous envisagez de créer une boîte aux lettres, exécutez la commande suivante pour une organisation Exchange sur site à forêt unique :</span><span class="sxs-lookup"><span data-stu-id="adafc-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="adafc-116">L’exemple ci-dessus crée un compte d’utilisateur activé dans Active Directory et une boîte aux lettres de salle pour une salle de conférence dans une organisation Exchange sur site.</span><span class="sxs-lookup"><span data-stu-id="adafc-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="adafc-117">Le paramètre RoomMailboxPassword spécifie le mot de passe du compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adafc-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="adafc-118">Configurez le compte pour résoudre automatiquement les conflits en acceptant/rejetant les réunions.</span><span class="sxs-lookup"><span data-stu-id="adafc-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="adafc-119">Les comptes de salle de conférence équipés du système Skype Room dans Exchange peuvent être gérés par des personnes, mais notez que tant que la personne n’accepte pas une réunion, elle n’apparaîtra pas sur le calendrier de l’écran d’accueil de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="adafc-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="adafc-120">Pour obtenir un ensemble complet de commandes disponibles, voir Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="adafc-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="adafc-121">Pour rappeler aux organisateurs de la réunion de faire de la réunion une réunion Skype Entreprise en ligne dans Outlook, exécutez la commande suivante pour configurer une mailTip pour le nouveau compte :</span><span class="sxs-lookup"><span data-stu-id="adafc-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="adafc-122">Utilisez les commandes suivantes pour configurer des chaînes localisées.</span><span class="sxs-lookup"><span data-stu-id="adafc-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="adafc-123">Si votre organisation l’exige, vous pouvez également ajouter des traductions personnalisées :</span><span class="sxs-lookup"><span data-stu-id="adafc-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="adafc-124">Facultatif : configurez un texte d’acceptation de réunion qui fournit aux utilisateurs des informations sur la salle de réunion Skype Entreprise et ce à quoi ils doivent s’attendre lorsqu’ils prévoient et rejoignent des réunions.</span><span class="sxs-lookup"><span data-stu-id="adafc-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="adafc-125">Vérifier le compte de boîte aux lettres de ressources dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="adafc-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="adafc-126">Le compte de boîte aux lettres de salle de conférence créé par Exchange à l’étape 1 ci-dessus peut être un objet utilisateur désactivé dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="adafc-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="adafc-127">Skype Room System ne peut pas se connecter ou s’authentifier à l’aide de l’authentification Kerberos/NTLM si le compte est désactivé dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="adafc-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="adafc-128">Le client Skype Room System doit être en mesure de s’authentifier auprès des services web Exchange pour récupérer les paramètres de calendrier et doit également être en mesure d’envoyer des messages électroniques avec le contenu du tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="adafc-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="adafc-129">Par conséquent, si le compte est désactivé, vous devez activer ce compte dans Active Directory en faisant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="adafc-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="adafc-130">Dans Active Directory, exécutez la commande suivante pour activer la connexion au compte :</span><span class="sxs-lookup"><span data-stu-id="adafc-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="adafc-131">L’exécution de cette commande vous invite à entrer le mot de passe actuel, puis à entrer à nouveau le mot de passe à deux reprises pour confirmation.</span><span class="sxs-lookup"><span data-stu-id="adafc-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="adafc-132">Une fois le mot de passe définie, exécutez la commande suivante pour activer le compte :</span><span class="sxs-lookup"><span data-stu-id="adafc-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="adafc-133">Activation des comptes Skype Room System pour Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="adafc-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="adafc-134">Cette section fournit une vue d’ensemble des étapes nécessaires pour activer Skype Entreprise pour votre compte de salle de conférence, qui sera configuré sur Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="adafc-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="adafc-135">Après avoir créé un compte de boîte aux lettres de ressources pour les salles de conférence, utilisez Skype Entreprise Server Management Shell pour activer les comptes Skype Room System pour les services Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="adafc-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adafc-136">La procédure suivante suppose que vous avez activé le compte Skype Room System dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="adafc-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="adafc-137">Exécutez la commande suivante pour activer le compte Skype Room System sur un pool Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="adafc-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="adafc-138">Facultatif : autorisez ce compte à effectuer et à recevoir des appels téléphoniques PSTN en activant le compte pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="adafc-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="adafc-139">Voix Entreprise n’est pas nécessaire pour Skype Room System, mais si vous ne l’activez pas pour Voix Entreprise, le client Skype Room System ne sera pas en mesure de fournir la fonctionnalité de numérotation PSTN :</span><span class="sxs-lookup"><span data-stu-id="adafc-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="adafc-140">Si vous activez Voix Entreprise pour le compte de salle de conférence Skype Room System, veillez à configurer une stratégie de voix restreinte adaptée à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="adafc-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="adafc-141">Si la salle de réunion Skype Entreprise est une ressource disponible publiquement, tout le monde peut l’utiliser pour participer à une réunion, qu’elle soit programmée ou ad hoc.</span><span class="sxs-lookup"><span data-stu-id="adafc-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="adafc-142">Après avoir rejoint une réunion, la personne peut composer n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="adafc-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="adafc-143">Dans Skype Entreprise Server, la fonctionnalité d’appel sortant des conférences utilise la stratégie de voix de l’utilisateur, dans ce cas, le compte Skype Room System utilisé pour participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="adafc-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="adafc-144">Dans les versions antérieures de Lync Server, la stratégie de voix de l’organisateur est utilisée.</span><span class="sxs-lookup"><span data-stu-id="adafc-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="adafc-145">Par conséquent, si un utilisateur d’une version antérieure de Lync Server organise une salle de réunion et invite le compte de salle Skype Room System, toute personne peut utiliser la salle de réunion Skype Entreprise pour participer à la réunion et composer n’importe quel numéro de téléphone national/régional ou international, à condition que l’organisateur soit autorisé à composer ces numéros.</span><span class="sxs-lookup"><span data-stu-id="adafc-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

