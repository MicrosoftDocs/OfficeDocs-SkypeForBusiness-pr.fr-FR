---
title: Envoyer un e-mail de bienvenue aux utilisateurs de connexion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Résumé : Découvrez comment accueillir les utilisateurs à des conférences téléphoniques dans Skype Entreprise Server.'
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817494"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="13347-103">Envoyer un e-mail de bienvenue aux utilisateurs de connexion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="13347-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="13347-104">**Résumé :** Découvrez comment accueillir les utilisateurs à des conférences téléphoniques dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="13347-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="13347-105">Après avoir configuré les conférences téléphoniques et vérifié qu’elles fonctionnent correctement, vous devez définir des numéros d’identification personnelle initiaux pour les utilisateurs et informer les utilisateurs de la disponibilité de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="13347-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="13347-106">Vous pouvez inclure des instructions d’introduction telles que le code confidentiel initial et le lien vers la page web Paramètres de conférence conférence.</span><span class="sxs-lookup"><span data-stu-id="13347-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="13347-107">En règle générale, vous utilisez l’cmdlet **Set-CsClientPin** pour réinitialiser les code confidentiels, mais vous pouvez utiliser la procédure de cette rubrique si vous souhaitez envoyer un message électronique d’introduction avec les informations de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="13347-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="13347-108">Si vous ne souhaitez pas envoyer ce message, utilisez plutôt **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="13347-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="13347-109">Vous pouvez utiliser le script **Set-CsPinSendCAWelcomeMail** pour définir le code confidentiel et envoyer un message électronique de bienvenue à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13347-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="13347-110">Par défaut, le script ne réinitialise pas les codes confidentiels déjà définis, mais vous pouvez utiliser le paramètre Force pour forcer la réinitialisation d’un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="13347-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="13347-111">Le message électronique est envoyé à l’aide du protocole SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="13347-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="13347-112">Vous pouvez créer un script qui exécute le script **Set-CsPinSendCAWelcomeMail** de manière itérative pour définir des codes confidentiels et envoyer un message électronique à un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="13347-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="13347-113">Vous pouvez modifier le modèle du message électronique (le fichier CAWelcomeEmailTemplate.html) pour ajouter des liens supplémentaires aux pages intranet ou modifier le texte du message.</span><span class="sxs-lookup"><span data-stu-id="13347-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="13347-114">Définir un code confidentiel initial et envoyer un e-mail de bienvenue</span><span class="sxs-lookup"><span data-stu-id="13347-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="13347-115">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="13347-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="13347-116">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="13347-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="13347-117">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="13347-117">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

<span data-ttu-id="13347-118">**SmtpServer** Par défaut, le script utilise la valeur de la variable **d’environnement réservée $PSEmailServer** pour ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="13347-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="13347-119">Si la variable **$PSEmailServer** n’est pas définie, vous devez spécifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="13347-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="13347-120">**Informations d’identification** Par défaut, le script utilise les informations d’identification de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="13347-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="13347-121">Si l’utilisateur actuel n’a pas le droit d’envoyer un message électronique au nom de l’expéditeur spécifié dans le champ De, vous devez entrer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="13347-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="13347-122">En règle générale, spécifiez ce paramètre si vous n’indiquez pas votre adresse de messagerie dans le champ De.</span><span class="sxs-lookup"><span data-stu-id="13347-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="13347-123">L’exemple suivant crée un code confidentiel, puis envoie un message électronique de bienvenue de Marco à Bob.</span><span class="sxs-lookup"><span data-stu-id="13347-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="13347-124">Il utilise le texte du message électronique enregistré dans le modèle par défaut et crée le message électronique au format HTML.</span><span class="sxs-lookup"><span data-stu-id="13347-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="13347-125">L’objet par défaut est « Bienvenue dans les conférences téléphoniques » :</span><span class="sxs-lookup"><span data-stu-id="13347-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="13347-126">L’exemple suivant force un nouveau code confidentiel avec la valeur « 383042650 » pour Bob, même si Bob avait un code confidentiel existant, puis envoie un message électronique de bienvenue de Marco à Bob.</span><span class="sxs-lookup"><span data-stu-id="13347-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="13347-127">Comme le paramètre Credential est spécifié, la personne exécutant la commande est invitée à entrer un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="13347-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="13347-128">Le courrier électronique est envoyé à l’aide du SSL (Secure Sockets Layer) :</span><span class="sxs-lookup"><span data-stu-id="13347-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
