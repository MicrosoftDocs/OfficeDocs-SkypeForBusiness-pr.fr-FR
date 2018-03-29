---
title: Personnaliser l'expérience de client Mac dans Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: Cet article décrit les préférences et valeurs par défaut disponibles pour le client Skype Entreprise sur un client Mac ainsi que leur modification hors de l'application.
ms.openlocfilehash: 8c779ad35d82b42bc8e162599265f6a25f7a65c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="501b5-103">Personnaliser l'expérience de client Mac dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="501b5-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="501b5-104">Cet article décrit les préférences et valeurs par défaut disponibles pour le client Skype Entreprise sur un client Mac ainsi que leur modification hors de l'application.</span><span class="sxs-lookup"><span data-stu-id="501b5-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="501b5-105">Paramètres des préférences clients de Skype Entreprise sur Mac</span><span class="sxs-lookup"><span data-stu-id="501b5-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="501b5-106">Certaines fonctions et des comportements qui sont disponibles pour Skype pour les entreprises sur les clients Mac sont déterminées par les paramètres de préférence sur le client.</span><span class="sxs-lookup"><span data-stu-id="501b5-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="501b5-107">Le Skype pour le commerce sur Préférences Mac se trouvent dans un fichier situé sur un Mac qui ont installé le Skype pour client d’entreprise situé à l’adresse suivante :</span><span class="sxs-lookup"><span data-stu-id="501b5-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="501b5-108">**~/Library/Containers/com.Microsoft.SkypeForBusiness/Data/Library/Preferences/com.Microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="501b5-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="501b5-109">Pour définir ces préférences, accéder à une invite de terminal sur le client Mac et comme nécessaire entrer des commandes clés de com.microsoft.SkypeForBusiness écriture par défaut en utilisant les touches de préférence décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="501b5-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="501b5-110">**Clés de préférence client**</span><span class="sxs-lookup"><span data-stu-id="501b5-110">**Client preference keys**</span></span>


|<span data-ttu-id="501b5-111">**Clé**</span><span class="sxs-lookup"><span data-stu-id="501b5-111">**Key**</span></span>|<span data-ttu-id="501b5-112">**Type de**</span><span class="sxs-lookup"><span data-stu-id="501b5-112">**Type**</span></span>|<span data-ttu-id="501b5-113">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="501b5-113">**Value**</span></span>|<span data-ttu-id="501b5-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="501b5-114">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="501b5-115">AutoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="501b5-115">AutoDetectAutoDicoveryURLs</span></span>  <br/> |<span data-ttu-id="501b5-116">Bool</span><span class="sxs-lookup"><span data-stu-id="501b5-116">Bool</span></span>  <br/> |<span data-ttu-id="501b5-117">0 = configuration manuelle du serveur</span><span class="sxs-lookup"><span data-stu-id="501b5-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="501b5-118">1 = détection automatique du serveur (par défaut)</span><span class="sxs-lookup"><span data-stu-id="501b5-118">1 = automatic server detection (default)</span></span>  <br/> |<span data-ttu-id="501b5-119">Permet de spécifier comment Skype pour entreprise identifie le transport et le serveur à utiliser lors de l’ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="501b5-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="501b5-120">Si vous activez ce paramètre de stratégie, vous devez spécifier **internalAutoDiscoveryURL** et **externalAutoDiscoveryURL**.</span><span class="sxs-lookup"><span data-stu-id="501b5-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span> <br/> |
|<span data-ttu-id="501b5-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="501b5-121">internalAutoDiscoveryURL</span></span>  <br/> |<span data-ttu-id="501b5-122">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-122">String</span></span>  <br/> |<span data-ttu-id="501b5-123">URL de découverte automatique complète</span><span class="sxs-lookup"><span data-stu-id="501b5-123">Full autodiscover URL</span></span>  <br/> |<span data-ttu-id="501b5-124">URL de découverte automatique interne</span><span class="sxs-lookup"><span data-stu-id="501b5-124">Internal autodiscover URL</span></span>  <br/> |
|<span data-ttu-id="501b5-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="501b5-125">externalAutoDiscoveryURL</span></span>  <br/> |<span data-ttu-id="501b5-126">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-126">String</span></span>  <br/> |<span data-ttu-id="501b5-127">URL de découverte automatique complète</span><span class="sxs-lookup"><span data-stu-id="501b5-127">Full autodiscover URL</span></span>  <br/> |<span data-ttu-id="501b5-128">URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="501b5-128">External autodiscover URL</span></span>  <br/> |
|<span data-ttu-id="501b5-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="501b5-129">httpProxyDomain</span></span>  <br/> |<span data-ttu-id="501b5-130">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-130">String</span></span>  <br/> ||<span data-ttu-id="501b5-131">Domaine HTTP proxy</span><span class="sxs-lookup"><span data-stu-id="501b5-131">HTTP Proxy Domain</span></span>  <br/> |
|<span data-ttu-id="501b5-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="501b5-132">httpProxyUserName</span></span>  <br/> |<span data-ttu-id="501b5-133">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-133">String</span></span>  <br/> ||<span data-ttu-id="501b5-134">Nom d'utilisateur HTTP proxy</span><span class="sxs-lookup"><span data-stu-id="501b5-134">HTTP Proxy Username</span></span>  <br/> |
|<span data-ttu-id="501b5-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="501b5-135">httpProxyPassword</span></span>  <br/> |<span data-ttu-id="501b5-136">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-136">String</span></span>  <br/> ||<span data-ttu-id="501b5-137">Mot de passe HTTP proxy</span><span class="sxs-lookup"><span data-stu-id="501b5-137">HTTP Proxy Password</span></span>  <br/> |
|<span data-ttu-id="501b5-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="501b5-138">trustedDomainList</span></span>  <br/> |<span data-ttu-id="501b5-139">Tableau</span><span class="sxs-lookup"><span data-stu-id="501b5-139">Array</span></span>  <br/> ||<span data-ttu-id="501b5-140">Liste de domaines approuvés pour les redirections HTTP.</span><span class="sxs-lookup"><span data-stu-id="501b5-140">List of trusted domains for HTTP redirects.</span></span>  <br/> |
|<span data-ttu-id="501b5-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="501b5-141">autoAcceptTimeout</span></span>  <br/> |<span data-ttu-id="501b5-142">Numéro</span><span class="sxs-lookup"><span data-stu-id="501b5-142">Number</span></span>  <br/> |<span data-ttu-id="501b5-143">300 (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="501b5-143">300 (default)</span></span>  <br/> |<span data-ttu-id="501b5-144">Délai d'expiration de l'acceptation automatique pour les utilisateurs ne disposant pas d'historique des conversations côté serveur</span><span class="sxs-lookup"><span data-stu-id="501b5-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>  <br/> |
|<span data-ttu-id="501b5-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="501b5-145">warnWhenUnknownLocationForE911</span></span>  <br/> |<span data-ttu-id="501b5-146">Bool</span><span class="sxs-lookup"><span data-stu-id="501b5-146">Bool</span></span>  <br/> |<span data-ttu-id="501b5-147">0 = Désactivé</span><span class="sxs-lookup"><span data-stu-id="501b5-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="501b5-148">1 = Activé</span><span class="sxs-lookup"><span data-stu-id="501b5-148">1 = Enabled</span></span>  <br/> |<span data-ttu-id="501b5-149">Avertit l'utilisateur lorsqu'un numéro d'urgence est composé à partir d'un emplacement inconnu.</span><span class="sxs-lookup"><span data-stu-id="501b5-149">Warns the user when dialing an emergency number from an unknown location.</span></span>  <br/> |
|<span data-ttu-id="501b5-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="501b5-150">sipAddress</span></span>  <br/> |<span data-ttu-id="501b5-151">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-151">String</span></span>  <br/> ||<span data-ttu-id="501b5-152">L’adresse SIP (Email) utilisé pour vous connecter sur Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="501b5-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="501b5-153">nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="501b5-153">userName</span></span>  <br/> |<span data-ttu-id="501b5-154">Chaîne</span><span class="sxs-lookup"><span data-stu-id="501b5-154">String</span></span>  <br/> ||<span data-ttu-id="501b5-155">L’UPN (nom d’utilisateur) utilisé pour vous connecter sur Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="501b5-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="501b5-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="501b5-156">userNameInAdvancedOnly</span></span>  <br/> |<span data-ttu-id="501b5-157">Bool</span><span class="sxs-lookup"><span data-stu-id="501b5-157">Bool</span></span>  <br/> |<span data-ttu-id="501b5-158">0 = afficher le champ de nom d’utilisateur sur l’écran de connexion principal et dans la boîte de dialogue Propriétés avancées</span><span class="sxs-lookup"><span data-stu-id="501b5-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="501b5-159">1 = afficher le champ de nom d’utilisateur uniquement dans la boîte de dialogue Propriétés avancées (par défaut)</span><span class="sxs-lookup"><span data-stu-id="501b5-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>  <br/> |<span data-ttu-id="501b5-160">Spécifiez où le champ de nom d’utilisateur s’affiche lors de l’ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="501b5-160">Specify where the User Name field is displayed during sign-in.</span></span>  <br/> |
   
### <a name="usage-examples"></a><span data-ttu-id="501b5-161">Exemples d'utilisation</span><span class="sxs-lookup"><span data-stu-id="501b5-161">Usage examples</span></span>

<span data-ttu-id="501b5-162">Pour ajouter un seul domaine (Contoso.com) à la liste des domaines approuvés, vous utiliseriez la clé trustedDomainList comme indiqué :</span><span class="sxs-lookup"><span data-stu-id="501b5-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="501b5-163">écrire des valeurs par défaut com.microsoft.SkypeForBusiness trustedDomainList-tableau-ajouter « Contoso.com »</span><span class="sxs-lookup"><span data-stu-id="501b5-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="501b5-164">Pour ajouter plusieurs domaines à la liste des domaines approuvés, utilisez la clé trustedDomainList comme suit :</span><span class="sxs-lookup"><span data-stu-id="501b5-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="501b5-165">écrire des valeurs par défaut com.microsoft.SkypeForBusiness trustedDomainList-tableau-Ajouter « sfb.com », « abc.com » test «.org »</span><span class="sxs-lookup"><span data-stu-id="501b5-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
<span data-ttu-id="501b5-166">Vous trouverez des conseils sur l’utilisation de la commande par défaut dans la [bibliothèque de référence d’Apple](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/defaults.1.mdl).</span><span class="sxs-lookup"><span data-stu-id="501b5-166">Guidance on the use of the defaults command can be found in [Apple's reference library](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/defaults.1.mdl).</span></span> <span data-ttu-id="501b5-167">Même si cette page ancienne n'est plus actualisée, les informations sur la commande de paramètres par défaut demeurent applicables.</span><span class="sxs-lookup"><span data-stu-id="501b5-167">Although this page is old and no longer maintained, the information about the defaults command is unchanged and still applicable.</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="501b5-168">Exemples de paramètres non modifiés</span><span class="sxs-lookup"><span data-stu-id="501b5-168">Sample unedited settings</span></span>

<span data-ttu-id="501b5-169">À titre de référence, voici un exemple de fichier de paramètres incluant uniquement des paramètres par défaut : </span><span class="sxs-lookup"><span data-stu-id="501b5-169">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}

```


