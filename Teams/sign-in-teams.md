---
title: Se connecter à des équipes de Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Conseils pour vous connecter à Microsoft Teams à l’aide de l’authentification moderne.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443f20b1ecd8295acc4f731211c69d23a79f28dd
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="b3ec5-103">Se connecter à des équipes de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b3ec5-103">Sign in to Microsoft Teams</span></span>
==========================

<span data-ttu-id="b3ec5-104">Teams de Microsoft utilise une authentification moderne pour conserver l’expérience de connexion simple et sécurisée.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="b3ec5-105">Comment modernes de fonctionnement de l’authentification</span><span class="sxs-lookup"><span data-stu-id="b3ec5-105">How modern authentication works</span></span>

<span data-ttu-id="b3ec5-106">Authentification moderne est un processus qui permet aux équipes de savoir que les utilisateurs ont déjà entré leurs informations d’identification (par exemple leur messagerie électronique et un mot de passe), ailleurs, et ils ne doivent pas être doit entrer à nouveau afin de démarrer l’application.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-106">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="b3ec5-107">L’expérience dépend de plusieurs facteurs, tels que si les utilisateurs travaillent dans Windows ou sur un Mac.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-107">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="b3ec5-108">Elle varie également selon que votre organisation a activé l’authentification unifactorielle ou plusieurs facteurs d’authentification (plusieurs facteurs d’authentification implique généralement la vérification des informations d’identification via un téléphone, en fournissant un code unique, en entrant un code confidentiel, ou présentation d’une empreinte numérique).</span><span class="sxs-lookup"><span data-stu-id="b3ec5-108">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="b3ec5-109">Voici un récapitulatif de chaque scénario d’authentification modernes.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-109">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="b3ec5-110">Utilisateurs de Windows</span><span class="sxs-lookup"><span data-stu-id="b3ec5-110">Windows users</span></span> 

- <span data-ttu-id="b3ec5-111">Si les utilisateurs ont déjà signé à d’autres applications Office, par l’intermédiaire de leur compte Office 365 Enterprise, lorsqu’ils démarrent des équipes, ils sont immédiatement amenés à l’application.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-111">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="b3ec5-112">Il n’a pas besoin d’entrer leurs informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-112">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="b3ec5-113">Si les utilisateurs ne sont pas signés leur compte Office 365 Enterprise n’importe où ailleurs, lorsqu’ils démarrent des équipes, ils êtes invités à fournir les soit unique ou plusieurs facteur d’authentification (SFA ou AMF), en fonction de ce que votre organisation a décidé qu’ils aimeraient le processus d’entraîner.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-113">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="b3ec5-114">Si les utilisateurs sont connectés à un ordinateur à un domaine, lorsqu’ils démarrent des équipes, ils vous serez peut-être invités à traverser une étape supplémentaire pour l’authentification en fonction de si votre organisation a opté pour exiger AMF ou si leur ordinateur requiert déjà AMF pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-114">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="b3ec5-115">Si leur ordinateur requiert déjà AMF pour vous connecter, lorsqu’il ouvre des équipes, l’application automatiquement démarre.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-115">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="b3ec5-116">Utilisateurs de Mac</span><span class="sxs-lookup"><span data-stu-id="b3ec5-116">Mac users</span></span> 

<span data-ttu-id="b3ec5-117">Lorsque les utilisateurs démarrent des équipes, leur ordinateur ne sera en mesure d’extraire leurs informations d’identification de leur compte Office 365 Enterprise ou l’un de leurs autres applications Office.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-117">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="b3ec5-118">Au lieu de cela, ils verront un message demandant les SFA ou AMF (selon les paramètres de votre organisation).</span><span class="sxs-lookup"><span data-stu-id="b3ec5-118">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="b3ec5-119">Une fois que les utilisateurs entrent leurs informations d’identification, elles ne sont pas requises pour leur donner à nouveau.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-119">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="b3ec5-120">À ce stade, les équipes automatiquement démarre chaque fois qu’il travaillait sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-120">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="b3ec5-121">Comptes de commutation d’authentification moderne à la fin</span><span class="sxs-lookup"><span data-stu-id="b3ec5-121">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="b3ec5-122">Si les utilisateurs travaillent sur un ordinateur à un domaine (par exemple, si leurs clients a activé Kerberos), ils ne peuvent pas basculer les comptes d’utilisateurs une fois qu’ils ont effectuées d’authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-122">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="b3ec5-123">Si les utilisateurs ne travaillent pas sur un ordinateur à un domaine, ils peuvent changer de compte.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-123">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="b3ec5-124">La déconnexion de Microsoft Teams la fin de l’authentification moderne</span><span class="sxs-lookup"><span data-stu-id="b3ec5-124">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="b3ec5-125">Pour vous déconnecter des équipes, les utilisateurs peuvent cliquez sur leur image de profil en haut de l’application et puis sélectionnez **déconnexion**. Ils peuvent également droit sur l’icône de l’application dans la barre des tâches et puis sélectionnez **Déconnecter**. Une fois qu’ils ont Déconnectez-vous des équipes, ils doivent entrer leurs informations d’identification pour lancer l’application.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-125">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="b3ec5-126">Résolution des problèmes d’authentification moderne</span><span class="sxs-lookup"><span data-stu-id="b3ec5-126">Troubleshooting modern authentication</span></span>

<span data-ttu-id="b3ec5-127">Authentification moderne est disponible pour chaque organisation qu’utilise des équipes, si les utilisateurs ne sont pas en mesure de terminer le processus, il peut donc une anomalie avec votre domaine ou un compte Office 365 entreprise de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b3ec5-127">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="b3ec5-128">Pour plus d’informations, consultez [pourquoi j’éprouve des difficultés à l’ouverture de session Microsoft Teams ?](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="b3ec5-128">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

