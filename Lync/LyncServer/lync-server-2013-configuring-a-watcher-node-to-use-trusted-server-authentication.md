---
title: Configuration d’un nœud observateur pour utiliser l’authentification de serveur approuvé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8272dc0097205749ca3c0e5d613bc3da853fc7ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="b13b5-102">Configuration d’un nœud observateur dans Lync Server 2013 pour utiliser l’authentification de serveur approuvé</span><span class="sxs-lookup"><span data-stu-id="b13b5-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b13b5-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b13b5-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b13b5-104">Si votre ordinateur de nœud observateur se trouve dans le réseau de périmètre, l’utilisation de l’authentification de type Serveur sécurisé permet de réduire considérablement les tâches d’administration à la gestion d’un certificat unique à la place des nombreux mots de passe de comptes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b13b5-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="b13b5-p101">La première étape de configuration de l’authentification de type Serveur sécurisé consiste à créer un pool d’applications approuvées afin d’héberger l’ordinateur de nœud observateur. Une fois le pool d’applications approuvées créé, vous devez configurer les transactions synthétiques de ce nœud observateur afin qu’elles s’exécutent sous forme d’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="b13b5-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b13b5-107">Une application approuvée est une application à laquelle est attribuée un État approuvé à exécuter dans le cadre de Lync Server 2013, mais ce n’est pas une partie intégrée du produit.</span><span class="sxs-lookup"><span data-stu-id="b13b5-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="b13b5-108">Le statut d’application approuvée signifie que l’application n’a pas à s’authentifier chaque fois qu’elle s’exécute.</span><span class="sxs-lookup"><span data-stu-id="b13b5-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="b13b5-109">Pour créer un pool d’applications approuvées, ouvrez Lync Server 2013 Management Shell et exécutez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b13b5-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="b13b5-110">Pour plus d’informations sur les paramètres utilisés dans la commande précédente, tapez ce qui suit à l’invite de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="b13b5-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="b13b5-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="b13b5-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="b13b5-112">Après avoir créé le pool d’applications approuvées, configurez l’ordinateur de nœud observateur afin qu’il exécute les transactions synthétiques sous forme d’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="b13b5-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="b13b5-113">Pour ce faire, utilisez l’applet de commande **New-CsTrustedApplication** et une commande similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b13b5-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="b13b5-114">Quand l’exécution de la commande précédente est terminée et que l’application approuvée a été créée, exécutez Enable-CsTopology pour vous assurer que les modifications sont appliquées :</span><span class="sxs-lookup"><span data-stu-id="b13b5-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="b13b5-115">Après l’exécution de l’applet de commande Enable-CsTopology, nous vous recommandons de redémarrer l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b13b5-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="b13b5-116">Pour vérifier que la nouvelle application approuvée a été créée, tapez ce qui suit à l’invite Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="b13b5-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="b13b5-117">Configuration d’un certificat par défaut sur le nœud observateur</span><span class="sxs-lookup"><span data-stu-id="b13b5-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="b13b5-118">Chaque nœud observateur doit avoir un certificat par défaut affecté à l’aide de l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b13b5-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="b13b5-119">**Pour affecter un certificat par défaut**</span><span class="sxs-lookup"><span data-stu-id="b13b5-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="b13b5-120">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Lync Server**, puis sur **Assistant Déploiement Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b13b5-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="b13b5-121">Dans l’Assistant Déploiement Lync Server, cliquez sur **installer ou mettre à jour le système Lync Server** , puis cliquez sur **exécuter** sous le titre **requête, installer ou assigner un certificat**.</span><span class="sxs-lookup"><span data-stu-id="b13b5-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b13b5-122">Si le bouton <STRONG>Exécuter</STRONG> est désactivé, vous devrez peut-être d’abord cliquer sur <STRONG>Exécuter</STRONG> sous <STRONG>Installer le magasin de configurations local</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b13b5-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="b13b5-123">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b13b5-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="b13b5-p104">Si vous avez déjà un certificat qui peut être utilisé comme certificat par défaut, cliquez sur **Par défaut** dans l’Assistant Certificat, puis cliquez sur **Attribuer**. Suivez les étapes de l’Assistant permettant d’affecter un certificat pour affecter ce certificat.</span><span class="sxs-lookup"><span data-stu-id="b13b5-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="b13b5-p105">Si vous devez demander un certificat à utiliser comme certificat par défaut, cliquez sur **Demander**, puis suivez les étapes de l’Assistant Demande de certificat pour demander ce certificat. Si vous utilisez les valeurs par défaut pour le certificat de serveur web, vous obtenez un certificat que vous pouvez affecter en tant que certificat par défaut.</span><span class="sxs-lookup"><span data-stu-id="b13b5-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="b13b5-128">Installation et configuration d’un nœud observateur</span><span class="sxs-lookup"><span data-stu-id="b13b5-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="b13b5-129">Après avoir redémarré l’ordinateur de nœud observateur et configuré un certificat, vous devez exécuter le fichier Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="b13b5-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="b13b5-130">(Vous devez exécuter Watchernode. msi sur un ordinateur sur lequel les fichiers de l’agent Operations Manager et les composants principaux de Lync Server 2013 sont installés.)</span><span class="sxs-lookup"><span data-stu-id="b13b5-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="b13b5-131">**Pour installer et configurer un nœud observateur**</span><span class="sxs-lookup"><span data-stu-id="b13b5-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="b13b5-132">Ouvrez Lync Server Management Shell en cliquant sur **Démarrer**, sur **tous les programmes**, sur **Lync Server**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b13b5-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b13b5-133">Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (spécifiez le chemin d’accès réel à votre copie de Watchernode. msi) :</span><span class="sxs-lookup"><span data-stu-id="b13b5-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b13b5-p107">Vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>. Quand la fenêtre de commande s’ouvre, tapez la même commande que celle indiquée précédemment.</span><span class="sxs-lookup"><span data-stu-id="b13b5-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="b13b5-p108">Notez que la paire nom/valeur de la commande précédente Authentication=TrustedServer respecte l’emploi des majuscules et minuscules. Vous devez la taper exactement telle qu’elle est indiquée. La commande suivante échoue, car elle ne respecte pas l’emploi des majuscules et minuscules :</span><span class="sxs-lookup"><span data-stu-id="b13b5-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="b13b5-140">C :\\Tools\\Watchernode. msi Authentication = Trustedserver</span><span class="sxs-lookup"><span data-stu-id="b13b5-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="b13b5-p109">Vous pouvez utiliser le mode TrustedServer uniquement avec les ordinateurs situés dans le réseau de périmètre. Quand un nœud observateur est exécuté en mode TrustedServer, les administrateurs n’ont pas à gérer les mots de passe d’utilisateurs de test sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b13b5-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

