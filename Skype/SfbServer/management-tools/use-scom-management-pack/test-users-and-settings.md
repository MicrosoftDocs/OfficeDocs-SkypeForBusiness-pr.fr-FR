---
title: Configuration des paramètres et des utilisateurs test de nœud observateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Résumé : Configurez des comptes d’utilisateurs de test et les paramètres du nœud observateur pour Skype pour les transactions synthétiques Business Server.'
ms.openlocfilehash: f1f80632c20212a1aa9a78bc272a8bc6340c9366
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904166"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="70e0e-103">Configuration des paramètres et des utilisateurs test de nœud observateur</span><span class="sxs-lookup"><span data-stu-id="70e0e-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="70e0e-104">**Résumé :** Configurer les comptes d’utilisateurs de test et les paramètres du nœud observateur pour Skype pour les transactions synthétiques Business Server.</span><span class="sxs-lookup"><span data-stu-id="70e0e-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="70e0e-105">Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :</span><span class="sxs-lookup"><span data-stu-id="70e0e-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="70e0e-106">[Configurer les comptes d’utilisateurs Test](test-users-and-settings.md#testuser) devant être utilisé par les nœuds Observateur.</span><span class="sxs-lookup"><span data-stu-id="70e0e-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="70e0e-107">Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande **Set-CsTestUserCredential** pour activer ces comptes pour une utilisation sur le nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="70e0e-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="70e0e-108">Mettre à jour les paramètres de configuration du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="70e0e-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="70e0e-109">Configurer les comptes d’utilisateurs tests</span><span class="sxs-lookup"><span data-stu-id="70e0e-109">Configure Test User Accounts</span></span>
<span data-ttu-id="70e0e-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="70e0e-110"></span></span>

<span data-ttu-id="70e0e-111">Comptes de test n’avez pas besoin représenter les personnes réelle, mais ils doivent être des comptes Active Directory valides.</span><span class="sxs-lookup"><span data-stu-id="70e0e-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="70e0e-112">En outre, ces comptes doivent être activés pour Skype pour Business Server, ils doivent avoir des adresses SIP valides, et ils doivent être activés pour Enterprise Voice (utiliser la transaction synthétique Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="70e0e-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="70e0e-113">Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et configurez-les comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="70e0e-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="70e0e-114">Vous devez affecter au moins deux utilisateurs test pour chaque pool que vous souhaitez tester.</span><span class="sxs-lookup"><span data-stu-id="70e0e-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="70e0e-115">Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande Set-cstestusercredential n’et le Skype pour Business Server Management Shell activer ces comptes pour travailler avec les transactions synthétiques de test.</span><span class="sxs-lookup"><span data-stu-id="70e0e-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="70e0e-116">Cela en exécutant une commande semblable à ce qui suit (les commandes suivantes partent du principe que les deux comptes d’utilisateur Active Directory ont été créés et que ces comptes sont activés pour Skype pour Business Server) :</span><span class="sxs-lookup"><span data-stu-id="70e0e-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="70e0e-p104">Vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe. Si vous omettez le mot de passe, l’applet de commande Set-CsTestUserCredential vous invitera à entrer ces informations. Le nom d’utilisateur peut être spécifié au format nom de domaine/nom d’utilisateur indiqué ci-dessus dans le bloc de code précédent.</span><span class="sxs-lookup"><span data-stu-id="70e0e-p104">You must include not only the SIP address, but also the user name and password. If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information. The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="70e0e-120">Pour vérifier que les informations d’identification utilisateur de test ont été créées, exécutez ces commandes à partir de la Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="70e0e-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="70e0e-121">Des informations semblables aux suivantes sont retournées pour chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="70e0e-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="70e0e-122">**nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="70e0e-122">**UserName**</span></span>|<span data-ttu-id="70e0e-123">**mot de passe**</span><span class="sxs-lookup"><span data-stu-id="70e0e-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70e0e-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="70e0e-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="70e0e-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="70e0e-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="70e0e-126">Configurer un nœud observateur de base avec les transactions synthétiques par défaut</span><span class="sxs-lookup"><span data-stu-id="70e0e-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="70e0e-127">Une fois les utilisateurs tests créés, vous pouvez créer un nœud observateur en exécutant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="70e0e-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="70e0e-128">Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="70e0e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="70e0e-129">Le nouveau nœud Observateur utilise également le test utilisateurs watcher1@litwareinc.com et watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="70e0e-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="70e0e-130">Si le nœud Observateur utilise l’authentification TrustedServer, les comptes de deux test peuvent être des comptes d’utilisateur valide pour Active Directory et Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="70e0e-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="70e0e-131">Si le nœud observateur utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud observateur à l’aide de l’applet de commande Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="70e0e-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="70e0e-132">Pour vérifier que la découverte automatique du pool cible pour se connecter est correctement configurée, au lieu de cibler un pool directement, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="70e0e-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="70e0e-133">Configuration de tests étendus</span><span class="sxs-lookup"><span data-stu-id="70e0e-133">Configuring Extended Tests</span></span>

<span data-ttu-id="70e0e-p106">Si vous souhaitez activer le test PSTN, qui vérifie la connectivité avec le réseau téléphonique commuté, vous devez effectuer certaines tâches de configuration supplémentaires lors de la configuration du nœud observateur. Tout d’abord, vous devez associer vos utilisateurs test au type de test PSTN en exécutant une commande semblable à la suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p106">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node. First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="70e0e-p107">Les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, il s’agit de la variable nommée $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="70e0e-p107">The results of this command must be stored in a variable. In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="70e0e-138">Ensuite, vous pouvez utiliser l’applet de commande **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un Skype pour le pool de serveurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="70e0e-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="70e0e-139">Par exemple, la commande suivante crée une nouvelle configuration de nœud observateur pour le pool atl-cs-001, ajout de deux utilisateurs test créés précédemment, et ajout de la passerelle PSTN type de test :</span><span class="sxs-lookup"><span data-stu-id="70e0e-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="70e0e-140">La commande précédente échoue si vous n’avez pas installé les fichiers principaux de Skype Entreprise Server et la base de données RTCLocal sur l’ordinateur nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="70e0e-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="70e0e-p109">Pour tester plusieurs stratégies de voix, vous pouvez créer un test étendu pour chaque stratégie à l’aide de l’applet de commande **New-Cs ExtendedTest**. Les utilisateurs fournis doivent être configurés avec les stratégies de voix souhaitées. Les tests étendus sont ensuite passés à l’applet de commande **New-CsWatcherNodeConfiguration** à l’aide de virgules de délimitation, comme suit :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p109">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet. The users provided should be configured with the desired voice policies. The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="70e0e-144">-ExtendedTests @{ajouter = $pstnTest1, $pstnTest2, $pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="70e0e-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="70e0e-p110">Dans la mesure où l’applet de commande **New-CsWatcherNodeConfiguration** est appelée sans utiliser le paramètre Tests, seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Dans ce cas, le nœud observateur testera les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p110">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="70e0e-147">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="70e0e-147">Registration</span></span>
    
- <span data-ttu-id="70e0e-148">IM</span><span class="sxs-lookup"><span data-stu-id="70e0e-148">IM</span></span>
    
- <span data-ttu-id="70e0e-149">GroupIM (messagerie instantanée de groupe)</span><span class="sxs-lookup"><span data-stu-id="70e0e-149">GroupIM</span></span>
    
- <span data-ttu-id="70e0e-150">P2PAV (sessions audio/vidéo d’égal à égal)</span><span class="sxs-lookup"><span data-stu-id="70e0e-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="70e0e-151">AvConference (audioconférence)</span><span class="sxs-lookup"><span data-stu-id="70e0e-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="70e0e-152">Presence</span><span class="sxs-lookup"><span data-stu-id="70e0e-152">Presence</span></span>
    
- <span data-ttu-id="70e0e-153">ABS (Service de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="70e0e-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="70e0e-154">ABWQ (Service web de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="70e0e-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="70e0e-155">Les composants suivants ne seront pas testés par défaut :</span><span class="sxs-lookup"><span data-stu-id="70e0e-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="70e0e-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="70e0e-156">ASConference</span></span>
    
- <span data-ttu-id="70e0e-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="70e0e-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="70e0e-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="70e0e-158">DataConference</span></span>
    
- <span data-ttu-id="70e0e-159">DialInConferencing</span><span class="sxs-lookup"><span data-stu-id="70e0e-159">DialinConferencing</span></span>
    
- <span data-ttu-id="70e0e-160">ExumConnectivity (Messagerie unifiée Exchange)</span><span class="sxs-lookup"><span data-stu-id="70e0e-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="70e0e-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="70e0e-161">JoinLauncher</span></span>
    
- <span data-ttu-id="70e0e-162">MCXP2PIM (messagerie instantanée hérité appareil mobile)</span><span class="sxs-lookup"><span data-stu-id="70e0e-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="70e0e-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="70e0e-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="70e0e-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="70e0e-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="70e0e-165">PSTN (appels de passerelle PSTN, spécifiés comme test étendu.)</span><span class="sxs-lookup"><span data-stu-id="70e0e-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="70e0e-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="70e0e-166">UcwaConference</span></span>
    
- <span data-ttu-id="70e0e-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="70e0e-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="70e0e-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="70e0e-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="70e0e-169">Ajout et suppression de transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="70e0e-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="70e0e-p111">Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande Set-CsWatcherNodeConfiguration pour ajouter ou supprimer des transactions synthétiques du nœud. Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p111">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node. For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="70e0e-p112">Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p112">Multiple tests can be added by separating the test names by using commas. For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="70e0e-p113">Une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) ont déjà été activés sur le nœud observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p113">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="70e0e-176">Set-CsWatcherNodeConfiguration : il existe une combinaison de clés dupliquée « DataConference » pour la clé « urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName » ou une contrainte d’identité unique.</span><span class="sxs-lookup"><span data-stu-id="70e0e-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="70e0e-177">Lorsque cette erreur se produit, aucune modification n’est appliquée.</span><span class="sxs-lookup"><span data-stu-id="70e0e-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="70e0e-178">La commande doit être réexécutée en supprimant le test dupliqué.</span><span class="sxs-lookup"><span data-stu-id="70e0e-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="70e0e-p115">Pour supprimer une transaction synthétique d’un nœud observateur, utilisez la méthode Remove. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p115">To remove a synthetic transaction from a watcher node, use the Remove method. For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="70e0e-p116">Vous pouvez utiliser la méthode Replace pour remplacer tous les tests activés actuellement par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez que le nœud observateur exécute seulement le test de messagerie instantanée, vous pouvez exécuter la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p116">You can use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="70e0e-183">Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud observateur spécifié sont désactivées, à l’exception de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="70e0e-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="70e0e-184">Affichage et test de la configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="70e0e-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="70e0e-185">Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="70e0e-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="70e0e-186">Cette commande retourne des informations semblables aux suivantes, en fonction des transactions synthétiques qui ont été assignées au nœud :</span><span class="sxs-lookup"><span data-stu-id="70e0e-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="70e0e-187">Inscription par messagerie instantanée GroupIM P2PAV AvConference présence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="70e0e-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="70e0e-188">Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="70e0e-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="70e0e-189">Pour vérifier qu’un nœud observateur a été créé, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="70e0e-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="70e0e-190">Des informations semblables aux suivantes sont retournées :</span><span class="sxs-lookup"><span data-stu-id="70e0e-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="70e0e-191">Identité : atl-cs-001</span><span class="sxs-lookup"><span data-stu-id="70e0e-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="70e0e-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="70e0e-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="70e0e-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="70e0e-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="70e0e-194">TargetFqdn : atl-cs-001</span><span class="sxs-lookup"><span data-stu-id="70e0e-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="70e0e-195">Numéro_port : 5061</span><span class="sxs-lookup"><span data-stu-id="70e0e-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="70e0e-196">Pour vérifier que le nœud observateur a été correctement configuré, tapez la commande suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="70e0e-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="70e0e-197">Cette commande teste chaque nœud observateur de votre déploiement et vérifie si :</span><span class="sxs-lookup"><span data-stu-id="70e0e-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="70e0e-198">Le rôle de serveur d’inscriptions requis est installé.</span><span class="sxs-lookup"><span data-stu-id="70e0e-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="70e0e-199">La clé de Registre obligatoire est créée (terminée lorsque vous avez exécuté l’applet de commande Set-CsWatcherNodeConfiguration).</span><span class="sxs-lookup"><span data-stu-id="70e0e-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="70e0e-200">Vos serveurs exécutent la version correcte de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="70e0e-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="70e0e-201">Si vos ports sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="70e0e-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="70e0e-202">Vos utilisateurs de test assignés disposent les informations d’identification requises.</span><span class="sxs-lookup"><span data-stu-id="70e0e-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="70e0e-203">Gestion des nœuds observateurs</span><span class="sxs-lookup"><span data-stu-id="70e0e-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="70e0e-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="70e0e-204"></span></span>

<span data-ttu-id="70e0e-205">En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, vous pouvez également utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : d’une part, l’activation et la désactivation du nœud observateur et, d’autre part, la configuration du nœud observateur pour utiliser des URLweb internes ou externes lors de l’exécution de ses tests.</span><span class="sxs-lookup"><span data-stu-id="70e0e-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="70e0e-p117">Par défaut, les nœuds observateurs sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Parfois, cependant, vous souhaiterez peut-être suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, ces transactions sont vouées à l’échec. Pour désactiver temporairement un nœud observateur, exécutez une commande semblable à celle-ci à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p117">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions. At times, however, you may want to suspend those transactions. For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions. Without network connectivity, those transactions will fail. To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="70e0e-p118">Cette commande désactive l’exécution des transactions synthétiques sur le nœud observateur atl 001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p118">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="70e0e-p119">La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateurs. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande **Remove-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p119">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="70e0e-215">Cette commande supprime tous les paramètres de configuration du nœud observateur de l’ordinateur spécifié, ce qui empêche ainsi l’ordinateur d’exécuter automatiquement des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="70e0e-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="70e0e-216">Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ou la Skype pour les fichiers système Business Server.</span><span class="sxs-lookup"><span data-stu-id="70e0e-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="70e0e-p121">Par défaut, les nœuds observateurs utilisent les URL web externes d’une organisation dans le cadre de leurs tests. Cependant, les nœuds observateurs peuvent également être configurés de manière à utiliser les URL web internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud observateur de manière à utiliser des URL internes à la place d’URL externes, affectez à la propriété UseInternalWebURls la valeur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p121">By default, watcher nodes use an organization's external Web URLs when conducting tests. However, watcher nodes can also be configured to use the organization's internal Web URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="70e0e-221">La réinitialisation de cette propriété à la valeur par défaut False ($False) fera que l’observateur utilisera de nouveau les URL externes :</span><span class="sxs-lookup"><span data-stu-id="70e0e-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="70e0e-222">Instructions d’installation spéciales pour les transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="70e0e-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="70e0e-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="70e0e-223"></span></span>

<span data-ttu-id="70e0e-p122">La plupart des transactions synthétiques peuvent s’exécuter sur un nœud observateur en l’état. Dans la plupart des cas, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud observateur, ce dernier peut commencer à utiliser la transaction synthétique lors de ses tests. Toutefois, il existe des transactions synthétiques qui nécessitent des instructions d’installation spéciales, comme détaillé dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="70e0e-p122">Most synthetic transactions can run on a watcher node as-is. In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes. However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="70e0e-227">Transaction synthétique de conférence de données</span><span class="sxs-lookup"><span data-stu-id="70e0e-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-228">Si votre ordinateur de nœud observateur se situe à l’extérieur de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données à moins que vous ne désactiviez au préalable les paramètres proxy du navigateur Internet Windows Internet Explorer® pour le compte Service réseau, en procédant de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="70e0e-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="70e0e-229">Sur l’ordinateur nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="70e0e-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="70e0e-230">Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="70e0e-230">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="70e0e-231">Le message suivant s’affiche dans la fenêtre Commande :</span><span class="sxs-lookup"><span data-stu-id="70e0e-231">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="70e0e-p123">BITSAdmin est déconseillé et ne sera peut-être pas disponible dans les versions ultérieures de Windows. Les outils d’administration pour le service BITS sont désormais fournis par les applets de commande BITS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70e0e-p123">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="70e0e-234">Les paramètres proxy Internet pour le compte NetworkService sont définis sur NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="70e0e-234">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="70e0e-235">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="70e0e-235">(connection = default)</span></span>
  
<span data-ttu-id="70e0e-236">Ce message signifie que vous avez désactivé les paramètres proxy d’Internet Explorer pour le compte Service réseau.</span><span class="sxs-lookup"><span data-stu-id="70e0e-236">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="70e0e-237">Transaction synthétique de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="70e0e-237">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-238">La transaction synthétique de la messagerie unifiée Exchange vérifie que les utilisateurs test peuvent se connecter à des comptes de messagerie vocale hébergés dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="70e0e-238">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="70e0e-239">Les utilisateurs test doivent être préconfigurés avec des comptes de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="70e0e-239">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="70e0e-240">Transaction synthétique de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="70e0e-240">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-241">Pour utiliser la transaction synthétique de conversation permanente, vous devez d’abord créer un canal et donner aux utilisateurs test l’autorisation de l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="70e0e-241">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="70e0e-242">Vous pouvez utiliser la transaction synthétique de conversation permanente pour configurer ce canal :</span><span class="sxs-lookup"><span data-stu-id="70e0e-242">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="70e0e-243">Vous devez exécuter cette tâche de configuration au sein de l’entreprise :</span><span class="sxs-lookup"><span data-stu-id="70e0e-243">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="70e0e-244">Si elle est exécutée à partir d’un ordinateur non-serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle CsPersistentChatAdministrators pour le contrôle d’accès en fonction du rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="70e0e-244">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="70e0e-245">Si elle est exécutée à partir du serveur lui-même, l’utilisateur qui exécute l’applet de commande doit être membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="70e0e-245">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="70e0e-246">Transaction synthétique pour les appels d’égal à égal PSTN</span><span class="sxs-lookup"><span data-stu-id="70e0e-246">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-247">La transaction synthétique Test-CSPstnPeerToPeerCall vérifie la capacité de passer et recevoir des appels via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="70e0e-247">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="70e0e-248">Pour exécuter cette transaction synthétique, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="70e0e-248">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="70e0e-249">Deux utilisateurs test (un appelant et un récepteur) activés pour les communications unifiées (UC).</span><span class="sxs-lookup"><span data-stu-id="70e0e-249">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="70e0e-250">Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="70e0e-250">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="70e0e-251">Itinéraires voix et stratégies VoIP qui autorisent les appels au numéro du récepteur d’atteindre la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="70e0e-251">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="70e0e-252">Une passerelle PSTN qui accepte l’appel et les médias qui achemine les appels vers le pool d’accueil d’un récepteur, en fonction du numéro composé.</span><span class="sxs-lookup"><span data-stu-id="70e0e-252">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="70e0e-253">Transaction synthétique du magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="70e0e-253">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-254">La transaction synthétique du magasin de contacts unifié vérifie la capacité de Skype pour Business Server récupérer des contacts au nom d’un utilisateur à partir d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="70e0e-254">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="70e0e-255">Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="70e0e-255">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="70e0e-256">L’authentification serveur à serveur Lyss-Exchange doit être configurée.</span><span class="sxs-lookup"><span data-stu-id="70e0e-256">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="70e0e-257">Les utilisateurs test doivent disposer d’une boîte aux lettres Exchange valide.</span><span class="sxs-lookup"><span data-stu-id="70e0e-257">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="70e0e-258">Une fois ces conditions sont remplies, vous pouvez exécuter l’applet de commande Windows PowerShell suivante pour migrer des listes de contacts des utilisateurs de test vers Exchange :</span><span class="sxs-lookup"><span data-stu-id="70e0e-258">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="70e0e-259">La migration des listes de contacts des utilisateurs test vers Exchange peut prendre un moment.</span><span class="sxs-lookup"><span data-stu-id="70e0e-259">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="70e0e-260">Pour surveiller la progression de la migration, la même ligne de commande peut être exécutée sans-indicateur du programme d’installation :</span><span class="sxs-lookup"><span data-stu-id="70e0e-260">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="70e0e-261">Cette ligne de commande aboutira une fois que la migration est terminée.</span><span class="sxs-lookup"><span data-stu-id="70e0e-261">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="70e0e-262">Transaction synthétique XMPP</span><span class="sxs-lookup"><span data-stu-id="70e0e-262">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-263">La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) requiert que la fonctionnalité XMPP soit configurée avec un ou plusieurs domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="70e0e-263">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="70e0e-264">Pour activer la transaction synthétique XMPP, vous devez fournir un paramètre XmppTestReceiverMailAddress avec un compte d’utilisateur au niveau d’un domaine XMPP routable.</span><span class="sxs-lookup"><span data-stu-id="70e0e-264">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="70e0e-265">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="70e0e-265">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="70e0e-266">Dans cet exemple, un Skype pour règle Business Server devrez exister pour router les messages pour litwareinc.com vers une passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="70e0e-266">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="70e0e-267">XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70e0e-267">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="70e0e-268">Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="70e0e-268">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="70e0e-269">Transaction synthétique VIS (Serveur d’interopérabilité vidéo)</span><span class="sxs-lookup"><span data-stu-id="70e0e-269">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="70e0e-270">La transaction synthétique vidéo Interop Server (pouces) nécessite que vous téléchargez et installez les fichiers de prise en charge les transactions synthétiques ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="70e0e-270">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="70e0e-271">Pour installer VISSTSupportPackage.msi, assurez-vous que les dépendances (sous Configuration logicielle requise) du msi sont déjà installées.</span><span class="sxs-lookup"><span data-stu-id="70e0e-271">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="70e0e-272">Exécutez VISSTSupportPackage.msi pour effectuer une installation simple.</span><span class="sxs-lookup"><span data-stu-id="70e0e-272">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="70e0e-273">Le fichier .msi installe tous les fichiers dans le chemin d’accès suivant : « %ProgramFiles%\VIS Package de prise en charge des transactions synthétiques ».</span><span class="sxs-lookup"><span data-stu-id="70e0e-273">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="70e0e-274">Pour plus d’informations sur l’exécution de la Transaction synthétique VIS, reportez-vous à la documentation de l’applet de commande [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="70e0e-274">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="70e0e-275">Modification de la fréquence d’exécution des transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="70e0e-275">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="70e0e-276"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="70e0e-276"></span></span>

<span data-ttu-id="70e0e-277">Par défaut, les transactions synthétiques s’exécutent avec les utilisateurs configurés toutes les 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="70e0e-277">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="70e0e-278">Les transactions synthétiques sont exécutées en mode séquentiel dans un ensemble d’utilisateurs pour éviter tout conflit entre deux transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="70e0e-278">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="70e0e-279">Un intervalle plus long est nécessaire pour laisser à toutes les transactions synthétiques le temps de se terminer.</span><span class="sxs-lookup"><span data-stu-id="70e0e-279">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="70e0e-280">Si vous souhaitez exécuter les transactions synthétiques plus fréquemment, il est conseillé de réduire le nombre de transactions synthétiques exécutées avec un ensemble d’utilisateurs donné afin que les tests puissent se terminer dans le délai imparti en tenant compte de retards occasionnels liés au réseau.</span><span class="sxs-lookup"><span data-stu-id="70e0e-280">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="70e0e-281">Si vous exécutez plus de transactions synthétiques que recommandé, créez plusieurs ensembles d’utilisateurs pour exécuter davantage de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="70e0e-281">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="70e0e-282">Pour modifier la fréquence à laquelle les transactions synthétiques sont exécutées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="70e0e-282">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="70e0e-283">Ouvrir System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="70e0e-283">Open System Center Operations Manager.</span></span> <span data-ttu-id="70e0e-284">Cliquez sur Création.</span><span class="sxs-lookup"><span data-stu-id="70e0e-284">Click Authoring section.</span></span> <span data-ttu-id="70e0e-285">Cliquez sur règles section (création).</span><span class="sxs-lookup"><span data-stu-id="70e0e-285">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="70e0e-286">Dans la section règles, recherchez la règle avec le nom « Main synthétique règle de Collection performances de Transaction canal d’injection ».</span><span class="sxs-lookup"><span data-stu-id="70e0e-286">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="70e0e-287">Cliquez avec le bouton droit sur la règle et sélectionnez substitutions, sélectionnez Remplacer la règle, puis sélectionnez « pour tous les objets de classe : Observateur Pool ».</span><span class="sxs-lookup"><span data-stu-id="70e0e-287">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="70e0e-288">Dans la fenêtre Propriétés remplacer, sélectionnez le nom du paramètre « Fréquence » et définir la valeur Override à celui souhaité.</span><span class="sxs-lookup"><span data-stu-id="70e0e-288">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="70e0e-289">Dans la même fenêtre, sélectionnez le pack d’administration sur lequel cette substitution doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="70e0e-289">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="70e0e-290">Utilisation de la journalisation enrichie pour les transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="70e0e-290">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="70e0e-291"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="70e0e-291"></span></span>

<span data-ttu-id="70e0e-292">Les transactions synthétiques se sont révélées extrêmement utiles pour aider les administrateurs à identifier les problèmes du système.</span><span class="sxs-lookup"><span data-stu-id="70e0e-292">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="70e0e-293">Par exemple, l’applet de commande Test-Cs Registration pouvait alerter les administrateurs quand les utilisateurs rencontraient des problèmes pour s’inscrire à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="70e0e-293">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="70e0e-294">Cependant, d’autres détails peuvent être nécessaires pour déterminer la cause réelle d’une défaillance.</span><span class="sxs-lookup"><span data-stu-id="70e0e-294">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="70e0e-p132">Pour cette raison, les transactions synthétiques fournissent une journalisation enrichie. Avec cette journalisation enrichie, pour chaque activité qu’entreprend une transaction synthétique, les informations suivantes sont enregistrées :</span><span class="sxs-lookup"><span data-stu-id="70e0e-p132">For this reason, synthetic transactions provide rich logging. With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="70e0e-297">L’heure de début de l’activité.</span><span class="sxs-lookup"><span data-stu-id="70e0e-297">The time that the activity started.</span></span>
    
- <span data-ttu-id="70e0e-298">L’heure de fin de l’activité.</span><span class="sxs-lookup"><span data-stu-id="70e0e-298">The time that the activity finished.</span></span>
    
- <span data-ttu-id="70e0e-299">L’action effectuée (par exemple, création, participation ou fin de participation à une conférence, connexion à Skype Entreprise Server, envoi d’un message instantané).</span><span class="sxs-lookup"><span data-stu-id="70e0e-299">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="70e0e-300">Informatif, détaillé, avertissement ou messages d’erreur générés pendant l’exécution de l’activité.</span><span class="sxs-lookup"><span data-stu-id="70e0e-300">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="70e0e-301">Les messages d’inscription SIP.</span><span class="sxs-lookup"><span data-stu-id="70e0e-301">SIP registration messages.</span></span>
    
- <span data-ttu-id="70e0e-302">Les enregistrements d’exception ou codes de diagnostic générés pendant l’exécution de l’activité.</span><span class="sxs-lookup"><span data-stu-id="70e0e-302">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="70e0e-303">Le résultat net suite à l’exécution de l’activité.</span><span class="sxs-lookup"><span data-stu-id="70e0e-303">The net result of running the activity.</span></span>
    
<span data-ttu-id="70e0e-p133">Ces informations sont automatiquement générées à chaque exécution d’une transaction synthétique. Toutefois, elles ne sont pas automatiquement affichées ou enregistrées dans un fichier journal. Si vous exécutez manuellement une transaction synthétique, vous pouvez utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle seront stockées les informations. À partir de là, vous disposez de deux méthodes pour enregistrer et/ou afficher les messages d’erreur dans le journal enrichi au format XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="70e0e-p133">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file. If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored. From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="70e0e-307">Pour récupérer les informations de dépannage, spécifiez le paramètre OutLoggerVariable, suivi d’un nom de variable que vous choisissez :</span><span class="sxs-lookup"><span data-stu-id="70e0e-307">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="70e0e-308">Précéder pas le nom de la variable par le caractère $.</span><span class="sxs-lookup"><span data-stu-id="70e0e-308">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="70e0e-309">Utilisez un nom de variable comme RegistrationTest (et non $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="70e0e-309">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="70e0e-310">Lorsque vous exécutez cette commande, vous obtenez un résultat semblable à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="70e0e-310">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="70e0e-311">Nom de domaine complet cible : atl-cs-001 résultat : Échec de latence : 00:00:00 Message d’erreur : cet ordinateur ne dispose pas de tous les certificats affectés.</span><span class="sxs-lookup"><span data-stu-id="70e0e-311">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="70e0e-312">Diagnostic : vous pouvez accéder à des informations plus détaillées pour cette erreur que simplement le message d’erreur indiqué ici.</span><span class="sxs-lookup"><span data-stu-id="70e0e-312">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="70e0e-313">Pour obtenir ces informations au format HTML, utilisez une commande de ce type pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML :</span><span class="sxs-lookup"><span data-stu-id="70e0e-313">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="70e0e-314">Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :</span><span class="sxs-lookup"><span data-stu-id="70e0e-314">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="70e0e-315">Vous pouvez afficher ces fichiers à l’aide de Windows Internet Explorer, Microsoft Visual Studio ou toute autre application capable d’ouvrir des fichiers HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="70e0e-315">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="70e0e-316">Exécuter à partir de System Center Operations Manager à l’intérieur de transactions synthétiques génère automatiquement ces fichiers journaux pour les échecs.</span><span class="sxs-lookup"><span data-stu-id="70e0e-316">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="70e0e-317">Toutefois, ces journaux ne sont pas générés si l’exécution échoue avant que Skype Entreprise Server PowerShell n’ait pu charger et exécuter la transaction synthétique.</span><span class="sxs-lookup"><span data-stu-id="70e0e-317">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="70e0e-318">Par défaut, Skype pour Business Server enregistre les fichiers journaux dans un dossier qui n’est pas partagé.</span><span class="sxs-lookup"><span data-stu-id="70e0e-318">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="70e0e-319">Pour que ces journaux accessibles, vous devez partager ce dossier.</span><span class="sxs-lookup"><span data-stu-id="70e0e-319">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="70e0e-320">Par exemple : \\atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="70e0e-320">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
