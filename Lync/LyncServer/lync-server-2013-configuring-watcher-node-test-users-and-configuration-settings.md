---
title: Configuration des utilisateurs et des paramètres de configuration du nœud observateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d66eb347fbd26f2d50828924d41075680fdcc09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a64ea-102">Configuration des utilisateurs test de nœud observateur et des paramètres de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a64ea-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a64ea-103">_**Dernière modification de la rubrique :** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="a64ea-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="a64ea-104">Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :</span><span class="sxs-lookup"><span data-stu-id="a64ea-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="a64ea-105">créer les comptes tests devant être utilisés par ces nœuds observateurs.</span><span class="sxs-lookup"><span data-stu-id="a64ea-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="a64ea-106">SI vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) pour activer ces comptes pour une utilisation sur le nœud observateur ;</span><span class="sxs-lookup"><span data-stu-id="a64ea-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="a64ea-107">mettre à jour les paramètres de configuration du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="a64ea-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="a64ea-108">Cette section traite des sujets suivants :</span><span class="sxs-lookup"><span data-stu-id="a64ea-108">This section covers:</span></span>

  - <span data-ttu-id="a64ea-109">Configuration de comptes d’utilisateurs tests</span><span class="sxs-lookup"><span data-stu-id="a64ea-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="a64ea-110">Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut</span><span class="sxs-lookup"><span data-stu-id="a64ea-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="a64ea-111">Configuration de tests étendus</span><span class="sxs-lookup"><span data-stu-id="a64ea-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="a64ea-112">Ajout et suppression de transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="a64ea-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="a64ea-113">Affichage et test de la configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="a64ea-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="a64ea-114">Configuration de comptes d’utilisateurs tests</span><span class="sxs-lookup"><span data-stu-id="a64ea-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="a64ea-115">Les utilisateurs test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes de services de domaine Active Directory valides ; en outre, ces comptes doivent être activés pour Lync Server 2013, ils doivent avoir des adresses SIP valides, et ils doivent être activés pour voix entreprise (pour utiliser la transaction synthétique test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="a64ea-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="a64ea-116">Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et ont été configurés comme indiqué dans cet article.</span><span class="sxs-lookup"><span data-stu-id="a64ea-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="a64ea-117">Vous devez assigner au moins trois utilisateurs tests pour chaque pool que vous souhaitez tester.</span><span class="sxs-lookup"><span data-stu-id="a64ea-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="a64ea-118">Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser la cmdlet **Set-applet cstestusercredential** et Lync Server Management Shell pour permettre à ces comptes de test de fonctionner avec les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="a64ea-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="a64ea-119">Pour ce faire, vous pouvez exécuter une commande semblable à la suivante.</span><span class="sxs-lookup"><span data-stu-id="a64ea-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="a64ea-120">(Ces commandes partent du principe que les trois comptes d’utilisateur Active Directory ont déjà été créés et que ces comptes ont été activés pour Lync Server 2013.) :</span><span class="sxs-lookup"><span data-stu-id="a64ea-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="a64ea-121">Notez que vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a64ea-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="a64ea-122">Si vous omettez le mot de passe, Set-CsTestUserCredential vous invitera à entrer ces informations.</span><span class="sxs-lookup"><span data-stu-id="a64ea-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="a64ea-123">Le nom d’utilisateur peut être spécifié à l’aide\\du format nom d’utilisateur du nom de domaine indiqué ci-dessus ou en utilisant le format utilisateur Name@domain nom ; par exemple :</span><span class="sxs-lookup"><span data-stu-id="a64ea-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="a64ea-124">Pour vérifier que les informations d’identification de l’utilisateur de test ont été créées, exécutez les commandes suivantes à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a64ea-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="a64ea-125">Des informations semblables aux suivantes doivent être renvoyées pour chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a64ea-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="a64ea-126">Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut</span><span class="sxs-lookup"><span data-stu-id="a64ea-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="a64ea-127">Une fois les utilisateurs tests créés, vous pouvez créer un nœud observateur en exécutant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="a64ea-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="a64ea-128">Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut.</span><span class="sxs-lookup"><span data-stu-id="a64ea-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="a64ea-129">Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a64ea-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="a64ea-130">Si le nœud observateur utilise l’authentification TrustedServer, les trois comptes de test peuvent être des comptes d’utilisateurs valides activés pour Active Directory et Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a64ea-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="a64ea-131">Si le nœud observateur utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud observateur à l’aide de l’applet de commande **Set-CsTestUserCredential**.</span><span class="sxs-lookup"><span data-stu-id="a64ea-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="a64ea-132">Configuration de tests étendus</span><span class="sxs-lookup"><span data-stu-id="a64ea-132">Configuring Extended Tests</span></span>

<span data-ttu-id="a64ea-133">Si vous souhaitez activer le test PSTN (Public Switched Telephone Network), qui vérifie la connectivité avec le réseau téléphonique commuté, vous devez effectuer certaines tâches de configuration supplémentaires lors de la configuration du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="a64ea-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="a64ea-134">Tout d’abord, vous devez associer vos utilisateurs tests au type de test PSTN.</span><span class="sxs-lookup"><span data-stu-id="a64ea-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="a64ea-135">Pour ce faire, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a64ea-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="a64ea-136">Notez que les résultats de cette commande doivent être stockés dans une variable.</span><span class="sxs-lookup"><span data-stu-id="a64ea-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="a64ea-137">Dans cet exemple, il s’agit de la variable nommée $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="a64ea-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="a64ea-138">À ce stade, vous pouvez utiliser la cmdlet **New-applet cswatchernodeconfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a64ea-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="a64ea-139">Par exemple, la commande suivante crée une configuration de nœud observateur pour le pool atl-cs-001.litwareinc.com, ajoute les trois utilisateurs tests créés précédemment et ajoute également le type de test PSTN :</span><span class="sxs-lookup"><span data-stu-id="a64ea-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="a64ea-140">Notez que la commande précédente échoue si vous n’avez pas installé les fichiers Core de Lync Server et la base de données RTCLocal sur l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="a64ea-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="a64ea-141">Pour tester plusieurs stratégies de voix, vous devez créer un test étendu pour chaque stratégie à l’aide de l’applet de commande **New-CsExtendedTest**.</span><span class="sxs-lookup"><span data-stu-id="a64ea-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="a64ea-142">Les utilisateurs assignés à ce test doivent être configurés avec les stratégies de voix souhaitées.</span><span class="sxs-lookup"><span data-stu-id="a64ea-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="a64ea-143">Les tests étendus sont ensuite passés à l’applet de commande **New-CsWatcherNodeConfiguration** à l’aide d’une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="a64ea-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="a64ea-p110">Si New-CsWatcherNodeConfiguration est appelée sans utiliser le paramètre Tests, cela signifie que seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Dans ce cas, le nœud observateur testera les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="a64ea-p110">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="a64ea-146">Son</span><span class="sxs-lookup"><span data-stu-id="a64ea-146">Registration</span></span>

  - <span data-ttu-id="a64ea-147">IM (Messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="a64ea-147">IM</span></span>

  - <span data-ttu-id="a64ea-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="a64ea-148">GroupIM</span></span>

  - <span data-ttu-id="a64ea-149">P2PAV (sessions audio/vidéo d’égal à égal)</span><span class="sxs-lookup"><span data-stu-id="a64ea-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="a64ea-150">AvConference (audioconférence)</span><span class="sxs-lookup"><span data-stu-id="a64ea-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="a64ea-151">Présence</span><span class="sxs-lookup"><span data-stu-id="a64ea-151">Presence</span></span>

  - <span data-ttu-id="a64ea-152">ABS (Service de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="a64ea-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="a64ea-153">ABWQ (Service web de carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="a64ea-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="a64ea-p111">PSTN (appels de passerelle PSTN, spécifiés comme test étendu. Par défaut, le test PSTN est désactivé. Il est activé dans ce cas uniquement car la commande a activé PSTN à l’aide du paramètre ExtendedTests.)</span><span class="sxs-lookup"><span data-stu-id="a64ea-p111">PSTN (PSTN gateway calls, specified as an extended test. By default, PSTN is disabled. The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="a64ea-157">Cela signifie également que les composants suivants ne seront pas testés par défaut :</span><span class="sxs-lookup"><span data-stu-id="a64ea-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="a64ea-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="a64ea-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="a64ea-159">MCXP2PIM (messagerie instantanée d’appareils mobiles)</span><span class="sxs-lookup"><span data-stu-id="a64ea-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="a64ea-160">ExumConnectivity (Messagerie unifiée Exchange)</span><span class="sxs-lookup"><span data-stu-id="a64ea-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="a64ea-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="a64ea-161">JoinLauncher</span></span>

  - <span data-ttu-id="a64ea-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="a64ea-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="a64ea-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="a64ea-163">DataConference</span></span>

  - <span data-ttu-id="a64ea-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="a64ea-164">XmppIM</span></span>

  - <span data-ttu-id="a64ea-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="a64ea-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="a64ea-166">Ajout et suppression de transactions synthétiques</span><span class="sxs-lookup"><span data-stu-id="a64ea-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="a64ea-167">Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour ajouter ou supprimer des transactions synthétiques du nœud.</span><span class="sxs-lookup"><span data-stu-id="a64ea-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="a64ea-168">Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="a64ea-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="a64ea-p113">Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a64ea-p113">Multiple tests can be added by separating the test names by using commas. For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="a64ea-p114">Notez qu’une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) a déjà été activé sur le nœud observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="a64ea-p114">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="a64ea-173">Lorsque cette erreur se produit, aucune modification n’est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a64ea-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="a64ea-174">La commande doit être réexécutée en supprimant le test dupliqué.</span><span class="sxs-lookup"><span data-stu-id="a64ea-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="a64ea-p116">Pour supprimer une transaction synthétique d’un nœud observateur, utilisez la méthode Remove plutôt que la méthode Add. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="a64ea-p116">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method. For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="a64ea-p117">Vous pouvez aussi utiliser la méthode Replace pour remplacer tous les tests activés actuellement par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez que le nœud observateur exécute seulement le test de messagerie instantanée, vous pouvez exécuter la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a64ea-p117">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="a64ea-179">Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud observateur spécifié sont désactivées, à l’exception de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="a64ea-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="a64ea-180">Affichage et test de la configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="a64ea-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="a64ea-181">Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="a64ea-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="a64ea-182">Cette commande renvoie des informations semblables aux suivantes, en fonction des transactions synthétiques qui ont été assignées au nœud :</span><span class="sxs-lookup"><span data-stu-id="a64ea-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="a64ea-183">Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a64ea-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="a64ea-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="a64ea-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="a64ea-185">Pour vérifier qu’un nœud observateur a été créé, tapez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a64ea-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="a64ea-186">Des informations analogues aux suivantes seront retournées :</span><span class="sxs-lookup"><span data-stu-id="a64ea-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="a64ea-187">Pour vérifier que le nœud observateur a été correctement configuré, tapez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a64ea-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="a64ea-188">Cette commande teste chaque nœud observateur de votre déploiement et indique notamment :</span><span class="sxs-lookup"><span data-stu-id="a64ea-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="a64ea-189">si le rôle de serveur d’inscriptions requis a été installé ;</span><span class="sxs-lookup"><span data-stu-id="a64ea-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="a64ea-190">si la clé de Registre nécessaire a été créée pour vous lors de l’exécution de Set-CsWatcherNodeConfiguration ;</span><span class="sxs-lookup"><span data-stu-id="a64ea-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="a64ea-191">Vos serveurs exécutent la version correcte de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a64ea-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="a64ea-192">si vos ports ont été configurés correctement ;</span><span class="sxs-lookup"><span data-stu-id="a64ea-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="a64ea-193">si vos utilisateurs de test assignés disposent des informations d’identification requises.</span><span class="sxs-lookup"><span data-stu-id="a64ea-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

