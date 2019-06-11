---
title: Configuration d’un nœud FileSystemWatcher pour utiliser l’authentification de serveur approuvé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="4f060-102">Configuration d’un nœud FileSystemWatcher dans Lync Server 2013 de façon à utiliser l’authentification de serveur approuvé</span><span class="sxs-lookup"><span data-stu-id="4f060-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f060-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4f060-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4f060-104">Si votre ordinateur de nœud d’observateur se trouve à l’intérieur du réseau de périmètre, l’utilisation de l’authentification de serveur approuvé peut considérablement réduire les taxes d’administration pour gérer un seul certificat plutôt que de nombreux mots de passe de compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f060-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="4f060-105">La première étape de la configuration de l’authentification de serveur approuvé consiste à créer un pool d’applications approuvé pour héberger l’ordinateur de nœud d’observation.</span><span class="sxs-lookup"><span data-stu-id="4f060-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="4f060-106">Une fois le pool d’applications approuvé créé, vous devez configurer les transactions synthétiques sur le nœud de l’observateur pour qu’il s’exécute en tant qu’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="4f060-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4f060-107">Une application fiable est une application dotée d’un État approuvé à exécuter dans le cadre de Lync Server 2013, mais qui n’est pas une partie intégrante du produit.</span><span class="sxs-lookup"><span data-stu-id="4f060-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="4f060-108">Le statut approuvé signifie que l’application n’a pas à s’authentifier chaque fois qu’elle est exécutée.</span><span class="sxs-lookup"><span data-stu-id="4f060-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="4f060-109">Pour créer un pool d’applications approuvé, ouvrez Lync Server 2013 Management Shell et exécutez une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="4f060-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="4f060-110">Pour plus d’informations sur les paramètres utilisés dans la commande précédente, tapez ce qui suit à l’invite Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="4f060-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="4f060-111">Get-nouvelle-CsTrustedApplicationPool-complet | nombre</span><span class="sxs-lookup"><span data-stu-id="4f060-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="4f060-112">Après avoir créé le pool d’applications approuvé, configurez l’ordinateur de nœud d’observation pour qu’il exécute des transactions synthétiques en tant qu’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="4f060-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="4f060-113">Pour ce faire, vous pouvez utiliser l’applet **de commande New-CsTrustedApplication** et une commande similaire à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="4f060-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="4f060-114">Une fois la commande précédente terminée et l’application de confiance créée, exécutez Enable-CsTopology pour vous assurer que les modifications entrent en vigueur:</span><span class="sxs-lookup"><span data-stu-id="4f060-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="4f060-115">Après avoir exécuté enable-CsTopology, il est recommandé de redémarrer l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4f060-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="4f060-116">Pour vérifier que la nouvelle application fiable a été créée, tapez les informations suivantes à l’invite Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="4f060-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="4f060-117">Configuration d’un certificat par défaut sur le nœud d’observation</span><span class="sxs-lookup"><span data-stu-id="4f060-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="4f060-118">Un certificat par défaut doit être attribué à chaque nœud de l’observateur à l’aide de l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f060-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="4f060-119">**Pour attribuer un certificat par défaut**</span><span class="sxs-lookup"><span data-stu-id="4f060-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="4f060-120">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Lync Server**, puis sur **Assistant Déploiement de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f060-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="4f060-121">Dans l’Assistant Déploiement de Lync Server, cliquez sur **installer ou mettre à jour le système de serveur Lync** , puis cliquez sur **exécuter** sous le titre **demande, installer ou attribuer un certificat**.</span><span class="sxs-lookup"><span data-stu-id="4f060-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4f060-122">Si le bouton <STRONG>exécuter</STRONG> est désactivé, vous devrez peut-être cliquer d’abord sur <STRONG>exécuter</STRONG> sous installer le <STRONG>magasin de configuration local</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f060-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="4f060-123">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f060-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="4f060-124">Si vous disposez déjà d’un certificat qui peut être utilisé comme certificat par défaut, cliquez sur **par défaut** dans l’Assistant certificat, puis cliquez sur **affecter**.</span><span class="sxs-lookup"><span data-stu-id="4f060-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="4f060-125">Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.</span><span class="sxs-lookup"><span data-stu-id="4f060-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="4f060-126">Si vous avez besoin de demander un certificat pour utiliser le certificat par défaut, cliquez sur **demander** , puis suivez les étapes de l’Assistant demande de certificat pour demander ce certificat.</span><span class="sxs-lookup"><span data-stu-id="4f060-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="4f060-127">Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter comme certificat par défaut.</span><span class="sxs-lookup"><span data-stu-id="4f060-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="4f060-128">Installation et configuration d’un nœud FileSystemWatcher</span><span class="sxs-lookup"><span data-stu-id="4f060-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="4f060-129">Après avoir redémarré l’ordinateur du nœud d’observation et configuré un certificat, vous devez exécuter le fichier Watchernode. msi.</span><span class="sxs-lookup"><span data-stu-id="4f060-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="4f060-130">(Vous devez exécuter Watchernode. msi sur un ordinateur sur lequel sont installés les fichiers agent Operations Manager et les composants principaux de Lync Server 2013.)</span><span class="sxs-lookup"><span data-stu-id="4f060-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="4f060-131">**Pour installer et configurer un nœud FileSystemWatcher**</span><span class="sxs-lookup"><span data-stu-id="4f060-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="4f060-132">Ouvrez Lync Server Management Shell en cliquant sur **Démarrer**, puis sur **tous les programmes**, sur **Lync Server**et sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f060-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4f060-133">Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (spécifiez le chemin d’accès réel à votre copie de Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="4f060-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4f060-134">Vous pouvez également exécuter Watchernode. msi à partir d’une fenêtre de commande.</span><span class="sxs-lookup"><span data-stu-id="4f060-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="4f060-135">Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f060-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="4f060-136">Lorsque la fenêtre de commande s’ouvre, tapez la même commande précédente.</span><span class="sxs-lookup"><span data-stu-id="4f060-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="4f060-137">Notez que la paire nom/valeur dans l’authentification de commande précédente = TrustedServer est sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="4f060-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="4f060-138">Vous devez la taper exactement comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="4f060-138">You must type it exactly as shown.</span></span> <span data-ttu-id="4f060-139">La commande suivante échoue, car elle n’utilise pas la casse correcte pour les lettres:</span><span class="sxs-lookup"><span data-stu-id="4f060-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="4f060-140">C:\\outils\\Watchernode. msi d’authentification = Trustedserver</span><span class="sxs-lookup"><span data-stu-id="4f060-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="4f060-141">Vous pouvez utiliser le mode TrustedServer uniquement avec des ordinateurs situés dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="4f060-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="4f060-142">Lorsqu’un nœud d’observateur est en cours d’exécution en mode TrustedServer, les administrateurs n’ont pas besoin de mettre à jour les mots de passe des utilisateurs de tests sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4f060-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

