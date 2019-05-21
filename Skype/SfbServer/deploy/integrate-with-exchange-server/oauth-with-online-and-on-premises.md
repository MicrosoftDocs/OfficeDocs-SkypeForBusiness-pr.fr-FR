---
title: Intégration de Skype entreprise Online et du serveur Exchange
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange sur site et Skype entreprise Online permet d’activer les fonctionnalités d’intégration de Skype entreprise et Exchange décrites dans la rubrique prise en charge des fonctionnalités.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278125"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="c146d-103">Configurer l’intégration entre Skype entreprise Online, Microsoft teams et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c146d-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="c146d-104">La configuration de l’intégration d’Exchange Server et de Skype entreprise Online permet d’activer les fonctionnalités d’intégration Skype entreprise et Exchange décrites dans la rubrique [prise en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="c146d-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="c146d-105">Cette rubrique s’applique à l’intégration à Exchange Server 2013 à 2019.</span><span class="sxs-lookup"><span data-stu-id="c146d-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c146d-106">Que devez-vous savoir avant de commencer ?</span><span class="sxs-lookup"><span data-stu-id="c146d-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c146d-107">Temps estimé pour réaliser cette tâche : 15 minutes</span><span class="sxs-lookup"><span data-stu-id="c146d-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="c146d-108">Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées.</span><span class="sxs-lookup"><span data-stu-id="c146d-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="c146d-109">Pour connaître les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et noyau](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="c146d-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="c146d-110">Pour plus d’informations sur les raccourcis clavier susceptibles d’être appliqués aux procédures décrites dans cette rubrique, voir [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="c146d-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="c146d-111">Configurer l’intégration entre Exchange Server et O365</span><span class="sxs-lookup"><span data-stu-id="c146d-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="c146d-112">Étape 1: configuration de l’authentification OAuth entre Exchange Server et O365</span><span class="sxs-lookup"><span data-stu-id="c146d-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="c146d-113">Suivez les étapes décrites dans l’article suivant:</span><span class="sxs-lookup"><span data-stu-id="c146d-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="c146d-114">Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c146d-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="c146d-115">Étape 2: créer un compte d’utilisateur de messagerie pour l’application partenaire de Skype entreprise Online ou teams</span><span class="sxs-lookup"><span data-stu-id="c146d-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="c146d-116">Cette étape est exécutée sur le serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="c146d-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="c146d-117">Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés.</span><span class="sxs-lookup"><span data-stu-id="c146d-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="c146d-118">Ce compte sera alors utilisé lors de l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="c146d-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="c146d-119">Spécifiez un domaine vérifié pour votre organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="c146d-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="c146d-120">Ce domaine doit être identique à celui utilisé pour le domaine SMTP principal utilisé pour les comptes Exchange locaux.</span><span class="sxs-lookup"><span data-stu-id="c146d-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="c146d-121">Ce domaine est connu sous \<le nom de\> domaine vérifié dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="c146d-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="c146d-122">Par ailleurs, \<le\> DomainControllerFQDN doit être le nom de domaine complet d’un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="c146d-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="c146d-123">Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c146d-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="c146d-124">Les deux commandes qui suivent permettront d’attribuer les rôles de gestion ArchiveApplication et UserApplication à ce nouveau compte.</span><span class="sxs-lookup"><span data-stu-id="c146d-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="c146d-125">Étape 3: créer et activer une application partenaire pour Skype entreprise Online ou teams</span><span class="sxs-lookup"><span data-stu-id="c146d-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="c146d-126">Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="c146d-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="c146d-127">Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="c146d-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="c146d-128">Vérifiez que tout fonctionne correctement</span><span class="sxs-lookup"><span data-stu-id="c146d-128">Verify your success</span></span>

<span data-ttu-id="c146d-129">Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="c146d-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="c146d-130">Confirmer le fonctionnement de la délégation de calendrier Outlook entre deux utilisateurs de teams avec des boîtes aux lettres Exchange Server 2016 ou 2019.</span><span class="sxs-lookup"><span data-stu-id="c146d-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="c146d-131">L’historique des conversations pour les clients mobiles est visible dans le dossier historique des conversations Outlook.</span><span class="sxs-lookup"><span data-stu-id="c146d-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="c146d-132">Vous pouvez également examiner votre trafic.</span><span class="sxs-lookup"><span data-stu-id="c146d-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="c146d-133">Le trafic d’une connexion OAuth est réellement distinctif (et ne ressemble pas à l’authentification de base), en particulier par rapport aux domaines, où vous allez commencer à voir le trafic de l’émetteur qui ressemble à ce qui suit: 00000004-0000-0ff1-CE00-000000000000 @ (parfois avec un/avant). le signe @), dans les jetons transmis.</span><span class="sxs-lookup"><span data-stu-id="c146d-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="c146d-134">Aucun nom d’utilisateur ou mot de passe ne s’affiche, qui est le point de OAuth.</span><span class="sxs-lookup"><span data-stu-id="c146d-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="c146d-135">Néanmoins, vous verrez l’émetteur’Office', dans le cas où «4» est Skype entreprise, ainsi que le domaine de votre abonnement.</span><span class="sxs-lookup"><span data-stu-id="c146d-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="c146d-136">Si vous voulez vous assurer que vous utilisez correctement OAuth, assurez-vous que vous savez à quoi il doit s’attendre et que vous savez à quoi ressemble le trafic.</span><span class="sxs-lookup"><span data-stu-id="c146d-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="c146d-137">Voici [ce à quoi vous pouvez vous attendre, vous](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)trouverez ci-dessous un [exemple standard de trafic OAuth dans une application Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (il est réellement utile de lire, même si elle n’utilise pas de jeton d’actualisation), et il existe des extensions Fiddler qui vous permettront d’accéder à votre JWT OAuth (JSON). Jeton Web).</span><span class="sxs-lookup"><span data-stu-id="c146d-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="c146d-138">Voici un [exemple de configuration d’une valeur unique](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mais vous pouvez utiliser n’importe quel outil de suivi réseau qui vous plaît pour engager ce processus.</span><span class="sxs-lookup"><span data-stu-id="c146d-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c146d-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c146d-139">Related topics</span></span>

[<span data-ttu-id="c146d-140">Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c146d-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
