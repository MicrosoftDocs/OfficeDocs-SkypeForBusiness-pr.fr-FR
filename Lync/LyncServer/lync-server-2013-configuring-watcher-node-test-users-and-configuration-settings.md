---
title: Configuration des utilisateurs et des paramètres de configuration du nœud FileSystemWatcher
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d446934e8d84a12a6eecd84fbc94a956d8ae95e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6f8dd-102">Configuration des utilisateurs et des paramètres de configuration du nœud FileSystemWatcher dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f8dd-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f8dd-103">_**Dernière modification de la rubrique:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="6f8dd-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="6f8dd-104">Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="6f8dd-105">Créez les comptes de test à utiliser par ces nœuds d’observation.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="6f8dd-106">Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) pour activer ces comptes pour une utilisation sur le nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="6f8dd-107">Mettre à jour les paramètres de configuration du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="6f8dd-108">Cette section comprend les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-108">This section covers:</span></span>

  - <span data-ttu-id="6f8dd-109">Configuration des comptes d’utilisateurs test</span><span class="sxs-lookup"><span data-stu-id="6f8dd-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="6f8dd-110">Configuration d’un nœud d’observateur de base avec les transactions synthétiques par défaut</span><span class="sxs-lookup"><span data-stu-id="6f8dd-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="6f8dd-111">Configuration de tests étendus</span><span class="sxs-lookup"><span data-stu-id="6f8dd-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="6f8dd-112">Ajout et suppression de transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="6f8dd-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="6f8dd-113">Affichage et test de la configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="6f8dd-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="6f8dd-114">Configuration des comptes d’utilisateurs test</span><span class="sxs-lookup"><span data-stu-id="6f8dd-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="6f8dd-115">Les utilisateurs test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes de services de domaine Active Directory valides. de plus, ces comptes doivent être activés pour Lync Server 2013, ils doivent disposer d’adresses SIP valides, et ils doivent être activés pour Enterprise Voice (pour utiliser la transaction synthétique test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="6f8dd-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="6f8dd-116">Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vérifier qu’il existe des comptes et qu’ils ont été configurés comme indiqué ici.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="6f8dd-117">Vous devez assigner au moins trois utilisateurs tests pour chaque pool que vous souhaitez tester.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="6f8dd-118">Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de contrôle **Set-CsTestUserCredential** et Lync Server Management Shell pour permettre à ces comptes de test d’utiliser les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="6f8dd-119">Pour cela, vous pouvez exécuter une commande semblable à la suivante.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="6f8dd-120">(Ces commandes présupposent que les trois comptes d’utilisateurs Active Directory ont déjà été créés et que ces comptes ont été activés pour Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="6f8dd-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="6f8dd-121">Notez que vous devez inclure la seule adresse SIP mais également le nom d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="6f8dd-122">Si vous n’incluez pas le mot de passe jeu-CsTestUserCredential vous invite à entrer ces informations.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="6f8dd-123">Le nom d’utilisateur peut être spécifié en utilisant le\\format de nom d’utilisateur nom de domaine indiqué ci-dessus ou en utilisant le nom d’utilisateur @ nom de domaine. par exemple:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="6f8dd-124">Pour vérifier que les informations d’identification de l’utilisateur ont été créées, exécutez les commandes suivantes dans Lync Server Management Shell, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="6f8dd-125">Des informations similaires doivent être renvoyées pour chaque utilisateur:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="6f8dd-126">Configuration d’un nœud d’observateur de base avec les transactions synthétiques par défaut</span><span class="sxs-lookup"><span data-stu-id="6f8dd-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="6f8dd-127">Après la création des utilisateurs de test, vous pouvez créer un nœud FileSystemWatcher à l’aide d’une commande similaire à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="6f8dd-128">Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="6f8dd-129">Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="6f8dd-130">Si le nœud de l’observateur d’observation utilise l’authentification TrustedServer, les trois comptes de test peuvent être tout compte d’utilisateur valide activé pour Active Directory et Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="6f8dd-131">Si le nœud d’observation utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud de l’observateur à l’aide de l’applet de passe **Set-CsTestUserCredential** .</span><span class="sxs-lookup"><span data-stu-id="6f8dd-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="6f8dd-132">Configuration de tests étendus</span><span class="sxs-lookup"><span data-stu-id="6f8dd-132">Configuring Extended Tests</span></span>

<span data-ttu-id="6f8dd-133">Si vous voulez activer le réseau téléphonique commuté (RTC) qui vérifie la connectivité avec le réseau téléphonique public commuté, vous devez effectuer une configuration supplémentaire lors de la configuration du nœud d’observation.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="6f8dd-134">Tout d’abord, vous devez associer vos utilisateurs de test au type de test PSTN.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="6f8dd-135">Pour cela, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="6f8dd-136">Notez que les résultats de cette commande doivent être stockés dans une variable.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="6f8dd-137">Dans cet exemple, il s’agit d’une variable nommée $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="6f8dd-138">À ce stade, vous pouvez utiliser l’applet de contrôle **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans le $pstnTest variable) à un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="6f8dd-139">Par exemple, la commande suivante crée une nouvelle configuration de nœud d’observation pour le pool atl-cs-001.litwareinc.com, en ajoutant les trois utilisateurs de test précédemment créés et en ajoutant également le type de test PSTN:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="6f8dd-140">Notez que la commande précédente échoue si vous n’avez pas installé les fichiers principaux de Lync Server et la base de données RTCLocal sur l’ordinateur de nœud d’observation.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="6f8dd-141">Pour tester plusieurs stratégies vocales, vous devez créer un test étendu pour chaque stratégie à l’aide de l’applet **de contrôle New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="6f8dd-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="6f8dd-142">Les utilisateurs affectés à ce test doivent être configurés avec les politiques vocales désirées.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="6f8dd-143">Les tests étendus sont ensuite passés à l’applet **de commande New-CsWatcherNodeConfiguration** à l’aide d’une commande similaire à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="6f8dd-144">Si New-CsWatcherNodeConfiguration est appelé sans utiliser le paramètre tests, cela signifie que seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud d’observation.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="6f8dd-145">Cela signifie que le nœud Watcher testera les composants suivants:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="6f8dd-146">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="6f8dd-146">Registration</span></span>

  - <span data-ttu-id="6f8dd-147">IM</span><span class="sxs-lookup"><span data-stu-id="6f8dd-147">IM</span></span>

  - <span data-ttu-id="6f8dd-148">GroupIM (messagerie instantanée de groupe)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-148">GroupIM</span></span>

  - <span data-ttu-id="6f8dd-149">P2PAV (sessions audio/vidéo d’égal à égal)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="6f8dd-150">AvConference (audioconférence)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="6f8dd-151">Presence</span><span class="sxs-lookup"><span data-stu-id="6f8dd-151">Presence</span></span>

  - <span data-ttu-id="6f8dd-152">ABS (Service de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="6f8dd-153">ABWQ (Service web de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="6f8dd-154">Appels RTC (RTC passerelle), spécifiés en tant que test étendu.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="6f8dd-155">Par défaut, le RTC est désactivé.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="6f8dd-156">Le test est activé uniquement dans ce cas, car la commande a activé PSTN à l’aide du paramètre ExtendedTests.)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="6f8dd-157">Cela signifie également que les composants suivants ne seront pas testés par défaut:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="6f8dd-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="6f8dd-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="6f8dd-159">MCXP2PIM (messagerie instantanée d’appareils mobiles)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="6f8dd-160">ExumConnectivity (Messagerie unifiée Exchange)</span><span class="sxs-lookup"><span data-stu-id="6f8dd-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="6f8dd-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="6f8dd-161">JoinLauncher</span></span>

  - <span data-ttu-id="6f8dd-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="6f8dd-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="6f8dd-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="6f8dd-163">DataConference</span></span>

  - <span data-ttu-id="6f8dd-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="6f8dd-164">XmppIM</span></span>

  - <span data-ttu-id="6f8dd-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="6f8dd-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="6f8dd-166">Ajout et suppression de transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="6f8dd-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="6f8dd-167">Après avoir configuré un nœud FileSystemWatcher, vous pouvez utiliser l’applet de cmdlet **Set-CsWatcherNodeConfiguration** pour ajouter ou supprimer des transactions synthétiques du nœud.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="6f8dd-168">Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="6f8dd-169">Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="6f8dd-170">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="6f8dd-171">Notez qu’une erreur se produit lorsqu’un ou plusieurs de ces tests (par exemple, DataConference) ont déjà été activés sur le nœud d’observateur.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="6f8dd-172">Dans ce cas, vous recevez un message d’erreur semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="6f8dd-173">Lorsque cette erreur se produit, aucune modification n’est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="6f8dd-174">La commande doit être réexécutée avec le test dupliqué supprimé.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="6f8dd-175">Pour supprimer une transaction synthétique d’un nœud d’observation, utilisez la méthode Remove à la place de la méthode Add.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="6f8dd-176">Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="6f8dd-177">Vous pouvez également utiliser la méthode Replace pour remplacer tous les tests actuellement activés par un ou plusieurs nouveaux tests.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="6f8dd-178">Par exemple, si vous souhaitez qu’un nœud d’observation ne exécute que le test de messagerie instantanée, vous pouvez le configurer en utilisant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="6f8dd-179">Lors de l’exécution de la commande ci-dessus, toutes les transactions synthétiques sur le nœud d’observateur spécifié seront désactivées sauf pour les messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="6f8dd-180">Affichage et test de la configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="6f8dd-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="6f8dd-181">Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="6f8dd-182">La commande précédente renverra des informations similaires à ce qui suit, en fonction des transactions de synthèse affectées au nœud:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="6f8dd-183">Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f8dd-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="6f8dd-184">Get-CsWatcherNodeConfiguration-Identity "atl-cs-001.litwareinc.com" | Select-Object-tests ExpandProperty | Objet de tri</span><span class="sxs-lookup"><span data-stu-id="6f8dd-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="6f8dd-185">Pour vérifier qu’un nœud d’observateur a été créé, tapez la commande suivante à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="6f8dd-186">Vous recevrez des informations similaires à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="6f8dd-187">Pour vérifier que le nœud d’observateur a été correctement configuré, tapez la commande suivante à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="6f8dd-188">La commande précédente testera chaque nœud d’observateur dans votre déploiement et vous fournira les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="6f8dd-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="6f8dd-189">Le rôle de bureau d’enregistrement requis a été installé.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="6f8dd-190">La clé de registre requise a été créée pour vous lorsque vous avez exécuté Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="6f8dd-191">Vos serveurs exécutent la version appropriée de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="6f8dd-192">Vos ports sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="6f8dd-193">Les informations d’identification requises pour vos utilisateurs de tests sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="6f8dd-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

