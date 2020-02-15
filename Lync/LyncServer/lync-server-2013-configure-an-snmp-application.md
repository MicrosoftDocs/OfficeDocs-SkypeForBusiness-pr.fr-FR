---
title: 'Lync Server 2013 : configuration d’une application SNMP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e7dafe07796f6d93e6357a5bff9aa058fe29b85
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="7704a-102">Configurer une application SNMP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7704a-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7704a-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="7704a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="7704a-104">Lync Server 2013 inclut une interface de service Web standard que vous pouvez utiliser pour connecter le service informations d’emplacement aux applications SNMP (simple Network Management Protocol) qui correspondent à des adresses MAC avec des informations sur les ports et les commutateurs.</span><span class="sxs-lookup"><span data-stu-id="7704a-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="7704a-105">Si une application SNMP est installée et que le service d’informations d’emplacement ne parvient pas à trouver une correspondance dans la base de données d’emplacements, le service d’informations d’emplacement interroge automatiquement l’application en utilisant l’adresse MAC fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="7704a-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="7704a-106">Le service d’informations d’emplacement utilise ensuite le port et les informations de commutateur renvoyées par l’application SNMP pour interroger à nouveau la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="7704a-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="7704a-107">Pour plus d’informations, consultez la rubrique [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7704a-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7704a-108">Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8.</span><span class="sxs-lookup"><span data-stu-id="7704a-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="7704a-109">Pour configurer l’URL de l’application SNMP</span><span class="sxs-lookup"><span data-stu-id="7704a-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="7704a-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7704a-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7704a-111">Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.</span><span class="sxs-lookup"><span data-stu-id="7704a-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

