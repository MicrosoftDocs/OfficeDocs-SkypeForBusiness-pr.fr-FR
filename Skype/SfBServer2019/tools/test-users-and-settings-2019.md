---
title: Configurer les paramètres et les utilisateurs de test de nœuds de l’observeur
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Configurez les comptes d’utilisateur test et les paramètres de nœud d’observation pour les transactions synthétiques Skype Entreprise Server.'
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812764"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="c465c-103">Configurer les paramètres et les utilisateurs de test de nœuds de l’observeur</span><span class="sxs-lookup"><span data-stu-id="c465c-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="c465c-104">**Résumé :** Configurez les paramètres de nœud d’utilisateur test et de nœud d’observation pour les transactions synthétiques Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c465c-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="c465c-105">Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :</span><span class="sxs-lookup"><span data-stu-id="c465c-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="c465c-106">[Configurez les comptes d’utilisateur test](test-users-and-settings-2019.md#testuser) à utiliser par ces nodes d’observation.</span><span class="sxs-lookup"><span data-stu-id="c465c-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="c465c-107">SI vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande **Set-CsTestUserCredential** pour activer ces comptes pour une utilisation sur le nœud observateur ;</span><span class="sxs-lookup"><span data-stu-id="c465c-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="c465c-108">mettre à jour les paramètres de configuration du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="c465c-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="c465c-109">Configurer les comptes d’utilisateur test</span><span class="sxs-lookup"><span data-stu-id="c465c-109">Configure Test User Accounts</span></span>
<span data-ttu-id="c465c-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="c465c-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="c465c-111">Les comptes test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes Active Directory valides.</span><span class="sxs-lookup"><span data-stu-id="c465c-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="c465c-112">En outre, ces comptes doivent être activés pour Skype Entreprise Server, ils doivent avoir des adresses SIP valides et être activés pour Voix Entreprise (pour utiliser la transaction synthétique Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="c465c-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="c465c-113">Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et de les configurer comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="c465c-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="c465c-114">Vous devez assigner au moins trois utilisateurs tests pour chaque pool que vous souhaitez tester.</span><span class="sxs-lookup"><span data-stu-id="c465c-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="c465c-115">Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser la cmdlet Set-CsTestUserCredential et Skype Entreprise Server Management Shell pour permettre à ces comptes de test de fonctionner avec les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="c465c-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="c465c-116">Pour ce faire, exécutez une commande semblable à la suivante (ces commandes supposent que les trois comptes d’utilisateur Active Directory ont été créés et que ces comptes sont activés pour Skype Entreprise Server) :</span><span class="sxs-lookup"><span data-stu-id="c465c-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="c465c-117">Vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c465c-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="c465c-118">Si vous n’incluez pas le mot de passe, Set-CsTestUserCredential cmdlet vous invite à entrer ces informations.</span><span class="sxs-lookup"><span data-stu-id="c465c-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="c465c-119">Le nom d’utilisateur peut être spécifié en utilisant le format nom de domaine \nom d’utilisateur indiqué dans le bloc de code précédent.</span><span class="sxs-lookup"><span data-stu-id="c465c-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="c465c-120">Pour vérifier que les informations d’identification de l’utilisateur test ont été créées, exécutez les commandes ci-après à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c465c-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="c465c-121">Des informations similaires à ceci sont renvoyées pour chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="c465c-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="c465c-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="c465c-122">**UserName**</span></span>|<span data-ttu-id="c465c-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="c465c-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c465c-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="c465c-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="c465c-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="c465c-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="c465c-126">Configurer un nœud d’observation de base avec les transactions synthétiques par défaut</span><span class="sxs-lookup"><span data-stu-id="c465c-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="c465c-127">Une fois les utilisateurs de test créés, vous pouvez créer un nœud d’observation à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="c465c-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="c465c-128">Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="c465c-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="c465c-129">Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c465c-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="c465c-130">Si le nœud observateur utilise l’authentification TrustedServer, les trois comptes de test peuvent être des comptes d’utilisateur valides activés pour Active Directory et Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c465c-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="c465c-131">Si le nœud observeur utilise la méthode d’authentification Negotiate, ces comptes d’utilisateur doivent également être activés pour le nœud de l'Set-CsTestUserCredential cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c465c-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="c465c-132">Pour vérifier que la découverte automatique du pool cible pour se connecter est configurée correctement au lieu de cibler un pool directement, utilisez plutôt les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c465c-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="c465c-133">Configuration de tests étendus</span><span class="sxs-lookup"><span data-stu-id="c465c-133">Configuring Extended Tests</span></span>

<span data-ttu-id="c465c-134">Si vous souhaitez activer le test PSTN, qui vérifie la connectivité avec le réseau téléphonique commuté public, vous devez faire une configuration supplémentaire lors de la configuration du nœud de l’observeur.</span><span class="sxs-lookup"><span data-stu-id="c465c-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="c465c-135">Tout d’abord, vous devez associer vos utilisateurs de test au type de test PSTN en exécutant une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c465c-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="c465c-136">Les résultats de cette commande doivent être stockés dans une variable.</span><span class="sxs-lookup"><span data-stu-id="c465c-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="c465c-137">Dans cet exemple, la variable est nommée $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="c465c-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="c465c-138">Ensuite, vous pouvez utiliser l’applet de la cmdlet **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un pool Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c465c-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="c465c-139">Par exemple, la commande suivante crée une configuration de nœud d’observation pour la atl-cs-001.litwareinc.com du pool, en ajoutant les trois utilisateurs de test créés précédemment et en ajoutant le type de test PSTN :</span><span class="sxs-lookup"><span data-stu-id="c465c-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="c465c-140">La commande précédente échouera si vous n’avez pas installé les fichiers principaux de Skype Entreprise Server et la base de données RTCLocal sur l’ordinateur du nœud observeur.</span><span class="sxs-lookup"><span data-stu-id="c465c-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="c465c-141">Pour tester plusieurs stratégies de voix, vous pouvez créer un test étendu pour chaque stratégie à l’aide de l’cmdlet **New-CsExtendedTest.**</span><span class="sxs-lookup"><span data-stu-id="c465c-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="c465c-142">Les utilisateurs fournis doivent être configurés avec les stratégies de voix souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c465c-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="c465c-143">Les tests étendus sont passés à l’applet de la cmdlet **New-CsWatcherNodeConfiguration** à l’aide de délimiteur-virgules, tels que :</span><span class="sxs-lookup"><span data-stu-id="c465c-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="c465c-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="c465c-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="c465c-145">Étant donné que la cmdlet **New-CsWatcherNodeConfiguration** a été appelée sans utiliser le paramètre Tests, seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="c465c-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="c465c-146">Par conséquent, le nœud de l’observation testera les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="c465c-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="c465c-147">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="c465c-147">Registration</span></span>
    
- <span data-ttu-id="c465c-148">IM (Messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="c465c-148">IM</span></span>
    
- <span data-ttu-id="c465c-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="c465c-149">GroupIM</span></span>
    
- <span data-ttu-id="c465c-150">P2PAV (sessions audio/vidéo d’égal à égal)</span><span class="sxs-lookup"><span data-stu-id="c465c-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="c465c-151">AvConference (audioconférence)</span><span class="sxs-lookup"><span data-stu-id="c465c-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="c465c-152">Présence</span><span class="sxs-lookup"><span data-stu-id="c465c-152">Presence</span></span>
    
- <span data-ttu-id="c465c-153">ABS (Service de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="c465c-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="c465c-154">ABWQ (Service web de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="c465c-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="c465c-155">Les composants suivants ne seront pas testés par défaut :</span><span class="sxs-lookup"><span data-stu-id="c465c-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="c465c-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="c465c-156">ASConference</span></span>
    
- <span data-ttu-id="c465c-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="c465c-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="c465c-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="c465c-158">DataConference</span></span>
    
- <span data-ttu-id="c465c-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="c465c-159">DialinConferencing</span></span>
    
- <span data-ttu-id="c465c-160">ExumConnectivity (Messagerie unifiée Exchange)</span><span class="sxs-lookup"><span data-stu-id="c465c-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="c465c-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="c465c-161">JoinLauncher</span></span>
    
- <span data-ttu-id="c465c-162">MCXP2PIM (messagerie instantanée d’appareil mobile hérité)</span><span class="sxs-lookup"><span data-stu-id="c465c-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="c465c-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="c465c-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="c465c-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="c465c-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="c465c-165">PSTN (appels de passerelle PSTN, spécifiés en tant que test étendu)</span><span class="sxs-lookup"><span data-stu-id="c465c-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="c465c-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="c465c-166">UcwaConference</span></span>
    
- <span data-ttu-id="c465c-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="c465c-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="c465c-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="c465c-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="c465c-169">Ajout et suppression de transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="c465c-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="c465c-170">Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande Set-CsWatcherNodeConfiguration pour ajouter ou supprimer des transactions synthétiques du nœud.</span><span class="sxs-lookup"><span data-stu-id="c465c-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="c465c-171">Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="c465c-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="c465c-172">Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules.</span><span class="sxs-lookup"><span data-stu-id="c465c-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="c465c-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c465c-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="c465c-174">Une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) ont déjà été activés sur le nœud de l’observation.</span><span class="sxs-lookup"><span data-stu-id="c465c-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="c465c-175">Dans ce cas, vous recevez un message d’erreur semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="c465c-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="c465c-176">Set-CsWatcherNodeConfiguration : il existe une séquence de touches en double « DataConference » pour la clé « urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName » ou une contrainte d’identité unique.</span><span class="sxs-lookup"><span data-stu-id="c465c-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="c465c-177">Lorsque cette erreur se produit, aucune modification n’est appliquée.</span><span class="sxs-lookup"><span data-stu-id="c465c-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="c465c-178">La commande doit être ré-exécuté avec le test dupliqué supprimé.</span><span class="sxs-lookup"><span data-stu-id="c465c-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="c465c-179">Pour supprimer une transaction synthétique d’un nœud d’observation, utilisez la méthode Remove.</span><span class="sxs-lookup"><span data-stu-id="c465c-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="c465c-180">Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="c465c-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="c465c-181">Vous pouvez utiliser la méthode Replace pour remplacer tous les tests actuellement activés par un ou plusieurs nouveaux tests.</span><span class="sxs-lookup"><span data-stu-id="c465c-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="c465c-182">Par exemple, si vous souhaitez qu’un nœud observeur exécute uniquement le test de messagerie instantanée, vous pouvez le configurer à l’aide de cette commande :</span><span class="sxs-lookup"><span data-stu-id="c465c-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="c465c-183">Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud de l’observeur spécifié sont désactivées à l’exception de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="c465c-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="c465c-184">Affichage et test de la configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="c465c-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="c465c-185">Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="c465c-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="c465c-186">Cette commande retourne des informations semblables à ceci, en fonction des transactions synthétiques qui ont été affectées au nœud :</span><span class="sxs-lookup"><span data-stu-id="c465c-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="c465c-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="c465c-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="c465c-188">Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c465c-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="c465c-189">Pour vérifier qu’un nœud d’observation a été créé, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c465c-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="c465c-190">Vous recevez des informations semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="c465c-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="c465c-191">Identité : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="c465c-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="c465c-192">ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="c465c-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="c465c-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061 Pour vérifier que le nœud d’observation a été configuré correctement, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c465c-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="c465c-194">Cette commande teste chaque nœud de l’analyseur dans votre déploiement et confirme si les actions suivantes sont terminées :</span><span class="sxs-lookup"><span data-stu-id="c465c-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="c465c-195">Le rôle de bureau d’enregistrement requis est installé</span><span class="sxs-lookup"><span data-stu-id="c465c-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="c465c-196">La clé de Registre requise est créée (terminée lorsque vous avez Set-CsWatcherNodeConfiguration cmdlet)</span><span class="sxs-lookup"><span data-stu-id="c465c-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="c465c-197">Vos serveurs exécutent la version correcte de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c465c-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="c465c-198">Vos ports sont configurés correctement</span><span class="sxs-lookup"><span data-stu-id="c465c-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="c465c-199">Vos utilisateurs de test affectés ont les informations d’identification requises</span><span class="sxs-lookup"><span data-stu-id="c465c-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="c465c-200">Gestion des nœuds observateurs</span><span class="sxs-lookup"><span data-stu-id="c465c-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="c465c-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="c465c-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="c465c-202">En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, vous pouvez également utiliser l’applet de calcul **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : l’activation et la désactivation du nœud observateur et la configuration du nœud observateur pour qu’il utilise des URL Web internes ou externes lors de l’exécution de ses tests.</span><span class="sxs-lookup"><span data-stu-id="c465c-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="c465c-203">Par défaut, les nœuds observateur sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées.</span><span class="sxs-lookup"><span data-stu-id="c465c-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="c465c-204">Toutefois, vous pouvez parfois suspendre ces transactions.</span><span class="sxs-lookup"><span data-stu-id="c465c-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="c465c-205">Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="c465c-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="c465c-206">Sans connectivité réseau, ces transactions échoueront.</span><span class="sxs-lookup"><span data-stu-id="c465c-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="c465c-207">Pour désactiver temporairement un nœud d’observation, exécutez une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c465c-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="c465c-208">Cette commande désactive l’exécution des transactions synthétiques sur le nœud de l'001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c465c-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="c465c-209">Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="c465c-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="c465c-210">La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateur.</span><span class="sxs-lookup"><span data-stu-id="c465c-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="c465c-211">Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande **Remove-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="c465c-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="c465c-212">Cette commande supprime tous les paramètres de configuration de nœuds de l’ordinateur spécifié, ce qui empêche cet ordinateur d’exécute automatiquement des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="c465c-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="c465c-213">Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ou les fichiers système Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c465c-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="c465c-214">Par défaut, les nodes d’observeur utilisent les URL web externes d’une organisation lors de la conduite de tests.</span><span class="sxs-lookup"><span data-stu-id="c465c-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="c465c-215">Toutefois, les nodes d’observation peuvent également être configurés pour utiliser les URL Web internes de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c465c-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="c465c-216">Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="c465c-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="c465c-217">Pour configurer un nœud d’observation afin qu’il utilise des URL internes au lieu d’URL externes, définissez la propriété UseInternalWebURls sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="c465c-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="c465c-218">La réinitialisation de cette propriété sur la valeur par défaut false ($False) entraîne une nouvelle utilisation des URL externes par l’observeur :</span><span class="sxs-lookup"><span data-stu-id="c465c-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="c465c-219">Instructions d’installation spéciales pour les transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="c465c-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="c465c-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="c465c-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="c465c-221">La plupart des transactions synthétiques peuvent s’exécuter sur un nœud d’observation tel qu’il est.</span><span class="sxs-lookup"><span data-stu-id="c465c-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="c465c-222">Dans la plupart des cas, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud de l’analyseur, le nœud de l’observation peut commencer à utiliser cette transaction synthétique lors de ses tests.</span><span class="sxs-lookup"><span data-stu-id="c465c-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="c465c-223">Toutefois, certaines transactions synthétiques nécessitent des instructions d’installation spéciales, comme expliqué dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="c465c-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="c465c-224">Transaction synthétique de conférence de données</span><span class="sxs-lookup"><span data-stu-id="c465c-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="c465c-225">Si votre ordinateur de nœud observeur se trouve en dehors de votre réseau de périmètre, vous ne serez probablement pas en mesure d’exécuter la transaction synthétique de conférence de données, sauf si vous désactivez d’abord les paramètres proxy du navigateur Internet Windows Internet Explorer® pour le compte service réseau en effectuant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c465c-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="c465c-226">Sur l’ordinateur du nœud observeur, cliquez sur **Démarrer,** cliquez sur Tous les **programmes,** cliquez sur **Accessoires,** cliquez avec le bouton droit sur Invite de **commandes,** puis cliquez sur Exécuter **en tant qu’administrateur.**</span><span class="sxs-lookup"><span data-stu-id="c465c-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="c465c-227">Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="c465c-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="c465c-228">Le message suivant s’affiche dans la fenêtre de commande :</span><span class="sxs-lookup"><span data-stu-id="c465c-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="c465c-229">BITSAdmin est supprimé et il n’est pas garanti qu’il soit disponible dans les versions futures de Windows.</span><span class="sxs-lookup"><span data-stu-id="c465c-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="c465c-230">Les outils d’administration du service BITS sont désormais fournis par les cmdlets BITS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c465c-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="c465c-231">Les paramètres de proxy Internet du compte NetworkService sont NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="c465c-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="c465c-232">(connection = valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="c465c-232">(connection = default)</span></span>
  
<span data-ttu-id="c465c-233">Ce message indique que vous avez désactivé les paramètres proxy Internet Explorer pour le compte de service réseau.</span><span class="sxs-lookup"><span data-stu-id="c465c-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="c465c-234">Transaction synthétique de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="c465c-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="c465c-235">La transaction synthétique de messagerie unifiée Exchange vérifie que les utilisateurs de test peuvent se connecter aux comptes de messagerie vocale d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="c465c-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="c465c-236">Les utilisateurs de test doivent être préconfigurés avec des comptes de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c465c-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="c465c-237">Transaction synthétique de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="c465c-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="c465c-238">Pour utiliser la transaction synthétique de conversation permanente, vous devez d’abord créer un canal et accorder aux utilisateurs de test les autorisations de l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="c465c-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="c465c-239">Vous pouvez utiliser la transaction synthétique de conversation permanente pour configurer ce canal :</span><span class="sxs-lookup"><span data-stu-id="c465c-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="c465c-240">Vous devez exécuter cette tâche de configuration à partir de l’entreprise :</span><span class="sxs-lookup"><span data-stu-id="c465c-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="c465c-241">S’il est exécuté à partir d’un ordinateur autre que le serveur, l’utilisateur qui exécute l'; doit être membre du rôle CsPersistentChatAdministrators pour le contrôle d’accès Role-Based (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c465c-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="c465c-242">S’il est exécuté à partir du serveur lui-même, l’utilisateur qui exécute la cmdlet doit être membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c465c-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="c465c-243">Transaction synthétique d’appel PSTN D’égal à égal</span><span class="sxs-lookup"><span data-stu-id="c465c-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="c465c-244">La Test-CsPstnPeerToPeerCall synthétique vérifie la possibilité de passer et de recevoir des appels via un réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="c465c-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="c465c-245">Pour exécuter cette transaction synthétique, vous devez configurer :</span><span class="sxs-lookup"><span data-stu-id="c465c-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="c465c-246">Deux utilisateurs de test à UC (un appelant et un récepteur).</span><span class="sxs-lookup"><span data-stu-id="c465c-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="c465c-247">Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c465c-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="c465c-248">Stratégies VoIP et itinéraires de voix qui permettent aux appels vers le numéro du destinataire d’atteindre la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="c465c-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="c465c-249">Passerelle PSTN qui accepte les appels et les médias qui routent les appels vers le pool d’accueil d’un récepteur, en fonction du numéro composé.</span><span class="sxs-lookup"><span data-stu-id="c465c-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="c465c-250">Transaction synthétique du magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="c465c-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="c465c-251">La transaction synthétique du magasin de contacts unifié vérifie la capacité de Skype Entreprise Server à récupérer des contacts pour le compte d’un utilisateur à partir d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="c465c-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="c465c-252">Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="c465c-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="c465c-253">Lyss-Exchange'authentification de serveur à serveur doit être configurée.</span><span class="sxs-lookup"><span data-stu-id="c465c-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="c465c-254">Les utilisateurs test doivent avoir une boîte aux lettres Exchange valide.</span><span class="sxs-lookup"><span data-stu-id="c465c-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="c465c-255">Une fois ces conditions remplies, vous pouvez exécuter la cmdlet Windows PowerShell suivante pour migrer les listes de contacts des utilisateurs de test vers Exchange :</span><span class="sxs-lookup"><span data-stu-id="c465c-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="c465c-256">La migration vers Exchange des listes de contacts des utilisateurs de test peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="c465c-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="c465c-257">Pour surveiller la progression de la migration, vous pouvez exécuter la même ligne de commande sans l’indicateur -Setup :</span><span class="sxs-lookup"><span data-stu-id="c465c-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="c465c-258">Cette ligne de commande réussit une fois la migration terminée.</span><span class="sxs-lookup"><span data-stu-id="c465c-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="c465c-259">Transaction synthétique XMPP</span><span class="sxs-lookup"><span data-stu-id="c465c-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="c465c-260">La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) nécessite que vous configuriez la fonctionnalité XMPP avec un ou plusieurs domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="c465c-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="c465c-261">Pour activer la transaction synthétique XMPP, vous devez fournir un paramètre XmppTestReceiverMailAddress avec un compte d’utilisateur dans un domaine XMPP routable.</span><span class="sxs-lookup"><span data-stu-id="c465c-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="c465c-262">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c465c-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="c465c-263">Dans cet exemple, une règle Skype Entreprise Server doit exister pour router les messages litwareinc.com vers une passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="c465c-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="c465c-264">Les passerelles et proxys XMPP étaient disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c465c-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c465c-265">Pour [plus d’informations, voir](../migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="c465c-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="c465c-266">Transaction synthétique VIS (Video Interop Server)</span><span class="sxs-lookup"><span data-stu-id="c465c-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="c465c-267">La transaction synthétique VIS (Video Interop Server) nécessite de télécharger et d’installer les fichiers de prise en charge des transactions synthétiques ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="c465c-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="c465c-268">Pour installer VISSTSupportPackage.msi vous assurer que les dépendances (sous System Requirements) pour le msi sont déjà installées.</span><span class="sxs-lookup"><span data-stu-id="c465c-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="c465c-269">Exécutez VISSTSupportPackage.msi pour une installation simple.</span><span class="sxs-lookup"><span data-stu-id="c465c-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="c465c-270">Le fichier .msi installe tous les fichiers dans le chemin d’accès suivant : « %ProgramFiles%\VIS Synthetic Transaction Support Package ».</span><span class="sxs-lookup"><span data-stu-id="c465c-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="c465c-271">Pour plus d’informations sur l’exécuter, reportez-vous à la documentation de l’cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)</span><span class="sxs-lookup"><span data-stu-id="c465c-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="c465c-272">Modification de la fréquence d’utilisation des transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="c465c-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="c465c-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="c465c-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="c465c-274">Par défaut, les transactions synthétiques s’exécutent avec les utilisateurs configurés toutes les 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="c465c-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="c465c-275">Les transactions synthétiques sont exécutés séquentiellement au sein d’un ensemble d’utilisateurs afin d’éviter que deux transactions synthétiques entrent en conflit.</span><span class="sxs-lookup"><span data-stu-id="c465c-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="c465c-276">Un intervalle plus long est nécessaire pour que toutes les transactions synthétiques se terminent.</span><span class="sxs-lookup"><span data-stu-id="c465c-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="c465c-277">S’il est souhaitable d’exécuter des transactions synthétiques plus fréquemment, le nombre de transactions synthétiques qui s’exécutent avec un ensemble donné d’utilisateurs doit être réduit afin que les tests se terminent dans la plage de temps souhaitée avec une certaine mémoire tampon pour les retards occasionnels du réseau.</span><span class="sxs-lookup"><span data-stu-id="c465c-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="c465c-278">Si l’exécution de plus de transactions synthétiques est souhaitable, créez d’autres jeux d’utilisateurs pour exécuter des transactions synthétiques supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c465c-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="c465c-279">Pour modifier la fréquence à laquelle les transactions synthétiques s’exécutent, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c465c-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="c465c-280">Ouvrez System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="c465c-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="c465c-281">Cliquez sur La section Auteur.</span><span class="sxs-lookup"><span data-stu-id="c465c-281">Click Authoring section.</span></span> <span data-ttu-id="c465c-282">Section Règles de clic (sous Auteur)</span><span class="sxs-lookup"><span data-stu-id="c465c-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="c465c-283">Dans la section Règles, recherchez la règle avec le nom « Main Synthetic Transaction Runner Performance Collection Rule »</span><span class="sxs-lookup"><span data-stu-id="c465c-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="c465c-284">Cliquez avec le bouton droit sur la règle, puis sélectionnez Remplacements, sélectionnez Remplacer la règle, puis sélectionnez « Pour tous les objets de la classe : Pool Watcher »</span><span class="sxs-lookup"><span data-stu-id="c465c-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="c465c-285">Dans la fenêtre Remplacer les propriétés, sélectionnez le nom du paramètre « Frequency » et définissez la valeur de remplacement sur la valeur souhaitée.</span><span class="sxs-lookup"><span data-stu-id="c465c-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="c465c-286">Dans la même fenêtre, sélectionnez le pack d’administration auquel ce remplacement doit être appliqué.</span><span class="sxs-lookup"><span data-stu-id="c465c-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="c465c-287">Utilisation de la journalisation enrichie pour les transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="c465c-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="c465c-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="c465c-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="c465c-289">Les transactions synthétiques s’avèrent extrêmement utiles pour aider à identifier les problèmes avec le système.</span><span class="sxs-lookup"><span data-stu-id="c465c-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="c465c-290">Par exemple, la cmdlet Test-CsRegistration peut alerter les administrateurs du fait que les utilisateurs avaient des difficultés à s’inscrire à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c465c-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="c465c-291">Toutefois, des détails supplémentaires peuvent être nécessaires pour déterminer la cause réelle d’une défaillance.</span><span class="sxs-lookup"><span data-stu-id="c465c-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="c465c-292">Pour cette raison, les transactions synthétiques fournissent une journalisation enrichie.</span><span class="sxs-lookup"><span data-stu-id="c465c-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="c465c-293">Avec la journalisation enrichie, pour chaque activité entreprise par une transaction synthétique, les informations suivantes sont enregistrées :</span><span class="sxs-lookup"><span data-stu-id="c465c-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="c465c-294">Heure de début de l’activité.</span><span class="sxs-lookup"><span data-stu-id="c465c-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="c465c-295">Heure de fin de l’activité.</span><span class="sxs-lookup"><span data-stu-id="c465c-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="c465c-296">Action effectuée (création, adhésion ou sortie d’une conférence, signature de Skype Entreprise Server, envoi d’un message instantané, par exemple).</span><span class="sxs-lookup"><span data-stu-id="c465c-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="c465c-297">Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité</span><span class="sxs-lookup"><span data-stu-id="c465c-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="c465c-298">Messages d’inscription SIP.</span><span class="sxs-lookup"><span data-stu-id="c465c-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="c465c-299">Enregistrements d’exception ou codes de diagnostic générés lors de l’activité.</span><span class="sxs-lookup"><span data-stu-id="c465c-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="c465c-300">Résultat net de l’exécution de l’activité.</span><span class="sxs-lookup"><span data-stu-id="c465c-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="c465c-301">Ces informations sont générées automatiquement chaque fois qu’une transaction synthétique est exécuté, mais ne sont pas automatiquement affichées ou enregistrées dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="c465c-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="c465c-302">Si vous exécutez manuellement une transaction synthétique, vous pouvez utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées.</span><span class="sxs-lookup"><span data-stu-id="c465c-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="c465c-303">À partir de là, vous avez la possibilité d’utiliser l’une des deux méthodes pour enregistrer et/ou afficher les messages d’erreur dans le journal enrichi au format XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="c465c-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="c465c-304">Pour récupérer les informations de dépannage, spécifiez le paramètre OutLoggerVariable, suivi d’un nom de variable que vous choisissez :</span><span class="sxs-lookup"><span data-stu-id="c465c-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="c465c-305">: ne faites pas préfacer le nom de la variable avec le caractère $.</span><span class="sxs-lookup"><span data-stu-id="c465c-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="c465c-306">Utilisez un nom de variable tel que RegistrationTest (pas $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="c465c-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="c465c-307">Lorsque vous exécutez cette commande, vous verrez une sortie semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="c465c-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="c465c-308">Fqdn cible : atl-cs-001.litwareinc.com résultat : Latence d’échec : 00:00:00 Message d’erreur : cet ordinateur ne se voit attribuer aucun certificat.</span><span class="sxs-lookup"><span data-stu-id="c465c-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="c465c-309">Diagnostic : vous pouvez accéder à des informations beaucoup plus détaillées sur cet échec que le simple message d’erreur affiché ici.</span><span class="sxs-lookup"><span data-stu-id="c465c-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="c465c-310">Pour accéder à ces informations au format HTML, utilisez une commande semblable à celle-ci pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML :</span><span class="sxs-lookup"><span data-stu-id="c465c-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="c465c-311">Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :</span><span class="sxs-lookup"><span data-stu-id="c465c-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="c465c-312">Vous pouvez afficher ces fichiers à l’aide de Windows Internet Explorer, de Microsoft Visual Studio ou de toute autre application capable d’ouvrir des fichiers HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="c465c-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="c465c-313">Les transactions synthétiques qui s’exécutent à partir de System Center Operations Manager génèrent automatiquement ces fichiers journaux en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="c465c-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="c465c-314">Ces journaux ne sont pas générés si l’exécution échoue avant que Skype Entreprise Server PowerShell soit en mesure de charger et d’exécuter la transaction synthétique.</span><span class="sxs-lookup"><span data-stu-id="c465c-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c465c-315">Par défaut, Skype Entreprise Server enregistre les fichiers journaux dans un dossier qui n’est pas partagé.</span><span class="sxs-lookup"><span data-stu-id="c465c-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="c465c-316">Pour rendre ces journaux facilement accessibles, vous devez partager ce dossier.</span><span class="sxs-lookup"><span data-stu-id="c465c-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="c465c-317">Par exemple : \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="c465c-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
