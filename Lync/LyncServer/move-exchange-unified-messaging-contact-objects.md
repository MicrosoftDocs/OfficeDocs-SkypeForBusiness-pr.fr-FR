---
title: Déplacer des objets contact de la messagerie unifiée Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c9a16251ca49d4d5179ed3ad72e4d0307beb4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="3bd1b-102">Déplacer des objets contact de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="3bd1b-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bd1b-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3bd1b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3bd1b-104">Pour migrer les objets de contact de standard automatique (AA) et d’accès abonné (SA) vers le nouveau déploiement Lync Server 2013, vous devez d’abord déplacer les objets depuis le déploiement hérité d’Office Communications Server 2007 R2 vers le nouveau déploiement Lync Server 2013 à l’aide des cmdlets **Get-CsExUmContact** et **Move-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="3bd1b-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="3bd1b-105">Sur le serveur Exchange, exécutez le script Windows PowerShell **exchucutil** pour effectuer les opérations suivantes pour le pool Lync nouvellement déployé :</span><span class="sxs-lookup"><span data-stu-id="3bd1b-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="3bd1b-106">Ajoutez-le aux passerelles IP de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="3bd1b-107">l’ajouter aux groupes de recherche.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3bd1b-p102">Afin d’utiliser les applets de commande <STRONG>Get-CsExUmContact</STRONG> et <STRONG>Move-CsExUmContact</STRONG>, vous devez être membre du groupe RTCUniversalUserAdmins et disposer d’une autorisation de l’unité d’organisation dans laquelle les objets contact sont stockés. L’autorisation de l’unité d’organisation peut être accordée à l’aide de l’applet de commande <STRONG>Grant-OUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="3bd1b-110">Pour déplacer des objets contact à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3bd1b-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="3bd1b-111">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3bd1b-112">Pour chaque pool enregistré avec la messagerie unifiée Exchange (où pool1.contoso.net est un pool du déploiement d’Office Communications Server 2007 R2 et pool2.contoso.net est le pool du déploiement de Lync Server 2013), tapez ce qui suit dans la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="3bd1b-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="3bd1b-113">Pour vérifier que les objets contact sont déplacés, exécutez la cmdlet **Get-CsExumContact** et assurez-vous que **RegistrarPool** pointe maintenant vers le nouveau pool.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="3bd1b-114">Pour exécuter le script Windows PowerShell ExchUCUtilscript</span><span class="sxs-lookup"><span data-stu-id="3bd1b-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="3bd1b-115">Ouvrez une session sur le serveur de messagerie unifiée Exchange en tant qu’utilisateur disposant des autorisations d’administrateur d’organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="3bd1b-116">Naviguez jusqu’au script Windows PowerShell ExchUCUtil.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="3bd1b-117">Dans Exchange 2007, ExchUCUtil. ps1 se trouve à l’emplacement suivant : **%\\Program\\Files%\\Microsoft\\Exchange Server scripts exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="3bd1b-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="3bd1b-118">Dans Exchange 2010, ExchUCUtil. ps1 se trouve à l’emplacement suivant : **%\\Program\\Files%\\Microsoft\\Exchange\\Server v14 scripts exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="3bd1b-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="3bd1b-119">Si Exchange est déployé dans une forêt unique, tapez ceci :</span><span class="sxs-lookup"><span data-stu-id="3bd1b-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="3bd1b-120">Ou, si Exchange est déployé dans plusieurs forêts, tapez ceci :</span><span class="sxs-lookup"><span data-stu-id="3bd1b-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="3bd1b-121">où Forest FQDN indique la forêt dans laquelle Lync Server 2013 est déployé.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3bd1b-122">Redémarrez le service <STRONG>frontal Lync Server</STRONG> (rtcsrv.exe) <EM>après</EM> avoir exécuté exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="3bd1b-123">Dans le cas contraire, Lync Server 2013 ne détecte pas la messagerie unifiée dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="3bd1b-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

