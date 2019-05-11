---
title: Configurer une application SNMP dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurer une application SNMP pour fonctionner avec E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 7903163d6cf1cd78d7689557f4906966c2c67a2c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893083"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="c44cb-103">Configurer une application SNMP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c44cb-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="c44cb-104">Configurer une application SNMP pour fonctionner avec E9-1-1 dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c44cb-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c44cb-105">Skype pour Business Server inclut une interface de service web standard que vous pouvez utiliser pour se connecter le service informations d’emplacement aux applications SNMP Simple Network Management Protocol () qui correspondent à des adresses MAC aux ports et commutateurs.</span><span class="sxs-lookup"><span data-stu-id="c44cb-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="c44cb-106">Si une application SNMP est installée et le service informations d’emplacement ne parvient pas à trouver une correspondance dans la base de données d’emplacement, le service informations d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="c44cb-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="c44cb-107">Le service informations d’emplacement utilise ensuite les informations de port et de commutateur renvoyées par l’application SNMP pour interroger la base de données d’emplacement à nouveau.</span><span class="sxs-lookup"><span data-stu-id="c44cb-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c44cb-108">Adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8.</span><span class="sxs-lookup"><span data-stu-id="c44cb-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="c44cb-109">Pour configurer l’URL de l’application SNMP</span><span class="sxs-lookup"><span data-stu-id="c44cb-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="c44cb-110">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c44cb-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c44cb-111">Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.</span><span class="sxs-lookup"><span data-stu-id="c44cb-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="c44cb-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c44cb-112">See also</span></span>

[<span data-ttu-id="c44cb-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c44cb-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

