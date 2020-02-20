---
title: Réactiver le serveur après la fermeture des ports par l’Assistant Configuration de sécurité dans les services Internet (IIS)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 064a21e5ec5a324dedae29aab2fb83d16c49b258
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="3a060-102">Réactiver le serveur après la fermeture des ports par l’Assistant Configuration de sécurité dans les services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="3a060-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a060-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3a060-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3a060-104">Certains rôles Lync Server 2013 exécutent des services Web sur le port 4443 des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="3a060-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="3a060-105">L’exécution de l’Assistant Déploiement de Lync Server, Bootstrapper. exe ou l’utilisation de l’applet de commande **Enable-CsComputer** crée une exception dans le pare-feu et ouvre le port.</span><span class="sxs-lookup"><span data-stu-id="3a060-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="3a060-106">Si vous exécutez ensuite l’Assistant Configuration de la sécurité Windows Server 2008 R2 (ou d’autres scripts de renforcement de la protection), le port 4443 sera bloqué et les clients externes ne pourront pas contacter les services Web.</span><span class="sxs-lookup"><span data-stu-id="3a060-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="3a060-107">Pour rouvrir le port, vous pouvez modifier directement l’exception de pare-feu ou réactiver le serveur.</span><span class="sxs-lookup"><span data-stu-id="3a060-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="3a060-108">Pour réactiver le serveur à l’aide de l’Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="3a060-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="3a060-109">Sur la page Assistant Déploiement Lync Server, cliquez sur **exécuter** à côté de **étape 2 : installer ou supprimer des composants Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3a060-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="3a060-110">Sur la page **Installer les composants Lync Server**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3a060-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="3a060-111">Sur la page **Exécution de commandes**, lorsque l’état indique que la tâche est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3a060-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3a060-112">Vous pouvez également utiliser Bootstrapper. exe ou <STRONG>Enable-CsComputer</STRONG> pour réactiver le serveur.</span><span class="sxs-lookup"><span data-stu-id="3a060-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

