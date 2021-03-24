---
title: Configurer une application SNMP dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurez une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103630"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="ed2b1-103">Configurer une application SNMP dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ed2b1-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="ed2b1-104">Configurez une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ed2b1-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ed2b1-105">Skype Entreprise Server inclut une interface de service web standard que vous pouvez utiliser pour connecter le service Informations d’emplacement aux applications SNMP (Simple Network Management Protocol) qui correspondent aux adresses MAC avec les informations de port et de commutateur.</span><span class="sxs-lookup"><span data-stu-id="ed2b1-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="ed2b1-106">Si une application SNMP est installée et que le service Informations d’emplacement ne parvient pas à trouver de correspondance dans la base de données d’emplacements, le service Informations d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="ed2b1-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="ed2b1-107">Le service Informations d’emplacement utilise ensuite les informations de port et de commutateur renvoyées par l’application SNMP pour interroger à nouveau la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="ed2b1-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed2b1-108">Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8.</span><span class="sxs-lookup"><span data-stu-id="ed2b1-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="ed2b1-109">Pour configurer l’URL de l’application SNMP</span><span class="sxs-lookup"><span data-stu-id="ed2b1-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="ed2b1-110">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="ed2b1-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ed2b1-111">Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.</span><span class="sxs-lookup"><span data-stu-id="ed2b1-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="ed2b1-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed2b1-112">See also</span></span>

[<span data-ttu-id="ed2b1-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed2b1-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)